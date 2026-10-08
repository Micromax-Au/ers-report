I tested the emergency communication workflow. The personal emergency function can prioritise LoRa for sending alerts, but the mass emergency function is still unable to execute through LoRa and is consistently forced to send via Wi-Fi instead. 

Based on testing, I think the most likely cause is that GPIO15 is being used by both the emergency button and the LoRa module reset pin. Since the mass emergency function requires the button to be pressed rapidly five times, GPIO15 is repeatedly pulled low and released, which may repeatedly reset the LoRa module. As a result, the LoRa module becomes unstable, causing LoRa transmission to fail and the system to fall back to WiFi. 

I completed the configuration of area names for the map. On the Raspberry Pi side, I tested the SMS response process by sending the emergency type field, which confirmed that the SMS response workflow is functioning correctly. However, the HAT is currently not working. As a result, it is unable to receive heartbeat messages or LoRaWAN information. 

Page 6-7 fuzzy logic 

Page 4-5 distance and position estimation 

Page 2-3 RSSI filtering 

Page 1 3 channels 

Today, I mainly completed the initial design and implementation of the map-based location and room identification features in the ERS system. 

First, I tested and confirmed that the backend server.py can successfully receive emergency payloads and call the trilateration algorithm to estimate the device coordinates based on gateway RSSI values. The estimated location is then written into the system logs and the SQLite database. To make the alert location more intuitive, I also designed a web-based Room Zone configuration method. Users can upload a floor plan in the Configuration page, click two corner points of a room, and enter a room name such as Office, Boardroom, or Kitchen. This allows room areas to be configured directly through the web interface without manually defining coordinates in the code. 

Several room zones have now been successfully saved into the database, and the backend logic has been partially extended so that the system can match the estimated x/y coordinates with the corresponding room name. This will support clearer location descriptions in future SMS messages and dashboard displays, such as Location: Office 1. 

The email notification design has not yet been completed. The next step is to improve the email alert format so that it includes the event time, event type, device name, and a map image or location marker, allowing recipients to understand the exact emergency location more intuitively. 

I completed the configuration of the LW003-B and the SX1303 gateway on TTN, and I also finished configuring the LW003-B in MKLoRa. The next step is to ensure the connection between the two devices, then use a mobile phone to simulate Beacon transmission and check the Live Data in TTN. 

# SX1303 915M LoRaWAN Gateway(B): 

Instruction: 

<u>https://www.waveshare.com/wiki/SX1302_LoRaWAN_Gateway_HAT? utm_source=chatgpt.com</u> 

The things network (TTN) 

https://au1.cloud.thethings.network/console/ 

Account: dashboard-dev@micromax.com.au 

Password: SeeYouSkylarIn2027! 

Terminal: ./lora_pkt_fwd -c test_conf.json 

Lorawan gateway EUI: 0x0016c001f15d0930 

Lorawan gateway ID: macromax-raseberry-transmitting 



<!-- Start of picture text -->
Applications > sx1303_test > End devices > lw003-b > Device overview<br>IwO0O3-b = + Add label<br>ID: 1w003-b<br>General information<br>End device ID 1w003-b<br>Frequency Australia 915-928 MHz, FSB 2<br>plan (used by TTN)<br>LoRaWAN version LoRaWAN Specification 1.0.3<br>Regional. Parameters version . RPOO1 Regional Parameters<br>1.0.3 revision~~ A<br>Created at Apr 20, 2026 16:04:34<br>Activation information<br>AppEUI 70 B3 D5 7E DO 02 6B 87<br>DevEUI EB 3A 02 FF FF 11 49 D3<br>AppKey ee ee ee we we we oe oe oe GS<br><!-- End of picture text -->

#### DevAddr: 021149d3 

AppSkey: 2b7e151628aed2a6abf7158809cf4f3c NwkSkey: 2b7e151628aed2a6abf7158809cf4f3c 

If both LoRaWAN and Wi-Fi is down, make a system alert immediately until a 

### user or admin responds. 

A design limitation still exists in the communication switching logic. When lora_pkt_fwd on the Raspberry Pi side is turned off, the LoRaWAN receiving path is actually unavailable. However, the Pico cannot receive a clear transmission failure signal, so it still assumes that the LoRaWAN transmission succeeded. Because no failure is detected, the system does not switch to Wi-Fi as intended. As a result, the server eventually interprets the missing heartbeat as both LoRaWAN and Wi-Fi being down, triggers an offline alert, and turns the dashboard status red. In reality, Wi-Fi may still be available, but the Pico has not switched over to it. Therefore, the current design still has an inconsistency between link-failure detection and communication channel switching judgment. 

ssh <u>micromax@192.168.115.49</u> 

cd ~/emergency-response-system source venv/bin/activate cd ~/emergency-response-system/server python3 server.py 

cd /home/micromax/sx1302_hal_rpi5-master/packet_forwarder sudo ./lora_pkt_fwd 

On the Pico client device side, I adjusted the communication strategy in ClientDeviceV2.py by introducing a switch structure. The current logic is that when the device detects either of the two button states (personal emergency / mass emergency) or a fall detection event, it will first attempt to transmit the data via LoRaWAN, with up to two retry attempts. If both LoRaWAN transmission attempts fail, the program will automatically switch to Wi-Fi and print the current communication status through the serial output for debugging and later verification. 

For the LoRaWAN payload design, I compressed the original information into a compact 4- byte packet. In other words, the device first sends a machine-readable compact event code rather than a full human-readable message. Then, on the Raspberry Pi 5 side, this code is translated and reconstructed so that the specific event type can be identified and the corresponding alert can be triggered. 

In addition, I designed and introduced the lora_pkt_fwd module. Its role is to receive the raw data packets coming from the LoRa module, and then either perform basic forwarding of the received payload or pass it to a later-stage parser for further processing. This allows the LoRareceived data to enter the server-side processing pipeline more smoothly, providing support for subsequent event recognition and alert triggering. 

In addition, I have now integrated the local_lora_udp_server.py module into the server.py module, so that the LoRa data reception process is more unified with the main server-side processing flow. Based on the current log output, the system is already able to successfully display all three emergency cases, which indicates that the chain from LoRa reception to basic parsing and event recognition has been initially established. 

However, there are still some issues on the alert output side. At the moment, only the personal emergency has been successfully received via SMS. Although the other emergency types can already be shown correctly in the logs, their SMS alerts have not yet been delivered as expected. In addition, I updated the recipient phone number through the web interface, but the new number still did not receive the messages. 

Therefore, at this stage, I cannot yet confirm whether the issue lies in the backend code logic or in the web interface / parameter update process. Further debugging is still needed, especially to verify whether the updated phone number from the web page is actually being written into the database or configuration file, and whether the server is correctly invoking the SMS sending workflow for all emergency types. 

### **Questions for Lorawan vs wifi** 

Can LoRaWAN on the Pi 5 Server be ALWAYS listening for all the client devices? 

Yes, for uplinks it is designed to listen continuously and forward packets from end devices. Gateways are multi-channel RF devices for LoRaWAN star networks. But most LoRaWAN gateways are half-duplex by default, which means they cannot receive while they are transmitting a downlink. Also, their reception is limited by the configured channels/sub-band and concentrator hardware capability. 

Can LoRaWAN on the Pi 5 Server be ALWAYS sending to all the client devices? Depend on which mode client devices choose. 

**Class A:** Lowest power consumption. Devices can transmit uplinks at any time, but after each uplink they only open two short receive windows, RX1 and RX2, for possible downlinks. If both are missed, the network must wait until the next uplink. This makes Class A ideal for battery-powered sensors with low downlink requirements. 

**Class B:** A balance between power saving and downlink responsiveness. It keeps the Class A behavior but also opens additional scheduled receive slots, called ping slots. These are synchronized by network beacons, allowing the server to deliver downlinks with lower latency than Class A, at the cost of higher power consumption. 

**Class C:** Lowest downlink latency but highest power consumption. It also includes the Class A mechanism, but unlike A and B, the device keeps its receive window open almost continuously whenever it is not transmitting. This allows the server to send downlinks almost at any time, making Class C suitable for mains-powered devices that need fast response. 

= <u>(https://www.thethingsnetwork.org/docs/lorawan/classes/?utm_source chatgpt.com)</u> 

LoRaWAN employs an ALOHA-based random access mechanism rather than assigning a dedicated channel to each device. Consequently, when two or more uplink packets arrive at the same gateway on the same channel with the same spreading factor (SF) at nearly the same time, collisions may occur, leading to packet loss. In practical deployments, a certain level (10%) of packet loss should therefore be expected. - <u>https://www.thethingsindustries.com/docs/hardware/devices/concepts/best practices/</u> 

To verify whether an uplink packet has been successfully delivered, Confirmed Uplink can be enabled so that the end device requests an acknowledgment (ACK) from the network. However, this should be used selectively, as excessive confirmed traffic may increase network load and reduce overall capacity. 

To further mitigate collisions and improve network capacity and reception probability, the system can be optimized by using more uplink channels where supported. For example, the SX1302 LoRaWAN Gateway HAT supports up to eight uplink channels, allowing traffic to be distributed across multiple frequencies rather than concentrated on a single channel. 

In addition, Forward Error Correction (FEC) can be considered as an extra reliability mechanism to improve tolerance to transmission errors and partial packet loss, particularly in noisy or congested environments. 

In terms of the payload and the transmission what are the pros and cons of both Lorawan and wifi. 

LoRaWAN is optimized for low-power, long-range delivery of small payloads at low data rates, whereas Wi-Fi is optimized for high-throughput, low-latency transmission of larger payloads over shorter distances. 

Can both be used at the same time? If not, can just the server listen to both lorawan and wifi (probably yes on the server but no on the pico) 

What happens if some Pico client devices lose LoRaWAN connection and some are still connected? What if we have a mix of WiFi and Lorawan connected devices? Is this realistically possible? 

The official white paper published by the LoRa Alliance and the Wireless Broadband Alliance <u>https://lora-alliance.org/wp-content/uploads/2020/11/wi-fi-and-lorawanr-</u> - <u>deployment synergies.pdf point that Wi-Fi and LoRaWAN are not mutually exclusive</u> communication technologies, but rather complementary connectivity solutions that can be deployed collaboratively within the same system to meet the communication requirements of different types of devices. 

In terms of device status management, LoRaWAN end devices typically do not maintain a continuous session, and their operational status is usually inferred indirectly from their most recent uplink activity. Therefore, to monitor whether a device is functioning properly, the system generally needs to transmit periodic status packets at predefined intervals, rather than relying solely on event-triggered uplinks. 

Wi-Fi devices usually behave as continuously connected IP nodes, allowing the server to more directly determine whether they are currently online or have lost connectivity based on network connection status. 

**Goal:** Should we use Lorawan or Wifi as our primary comms method? Why? 

### **1. pros and cons of LoRaWAN and Wi-Fi for indoor communication** 

#### LoRaWAN: 

1. A substantial body of measurement and modelling work indicates that LoRaWAN has strong potential for signal penetration and indoor coverage within buildings. 

2. The ultra-low-power Class A mode can be adopted. However, it imposes constraints on downlink reception. A Class A device only opens two short receive windows after each uplink transmission, and if those windows are missed, the downlink must wait until the device’s next uplink to be delivered. 

#### Wi-Fi: 

1. As a high-speed LAN technology, Wi-Fi typically delivers low latency with 

millisecond-level data exchanges. However, it uses contention-based channel access. When device density becomes high, co-channel interference increases and latency becomes less stable (Wi-Fi 6 can be considered to mitigate this). 

```
Pico side:
```

```
Step1. Download the .uf2 from the https://micropython.org/download/RPI_PICO2_W/ for
the RPI Pico 2 W, flash it to the Pico, and configure the MicroPython environment
to prepare the board for running Python through Thonny.
Step2. Since the chip currently in use is the Pico-LoRa-SX126x,
https://www.waveshare.net/wiki/Pico-LoRa-SX1262, I downloaded the driver files from
https://github.com/ehong-tl/micropySX126X/tree/master and executed _sx126x.py,
sx126x.py, and sx1262.py to perform the initial configuration. This allows the Pico
to interface with and control the LoRa chip, enabling the hardware to transmit
wireless signals.
```

```
Pico and Raspberry communicate in the frequency: AU915, FSB2(can be used in TTS),
917.2MHZ
```

```
This is main.py work in pico now
```

```
# main.py
from SX1262 import SX1262
import time
# Waveshare Pico-LoRa-SX1262-915M pin mapping
sx = SX1262(spi_bus=1,
            clk=10,
            mosi=11,
            miso=12,
            cs=3,
            irq=20,
            rst=15,
            gpio=2)
# AU915 FSB2 — 917.2 MHz is channel 10, dead centre of FSB2
sx.begin(freq=917.2,
         bw=125.0,
         sf=7,
         cr=5,
         syncWord=0x34,
         power=14,
         currentLimit=60.0,
         preambleLength=8,
         implicit=False,
         crcOn=True,
```

```
         txIq=False,
         rxIq=False,
         tcxoVoltage=1.7,
         useRegulatorLDO=False,
         blocking=True)
```

```
print("SX1262 ready, sending packets...")
```

```
count = 0
while True:
    msg = "Hello from Pico #{}".format(count)
    print("Sending: " + msg)
    sx.send(bytes(msg, 'utf-8'))
    print("Sent OK")
    count += 1
    time.sleep(5)
```

gateEUI: 0x0016c001f15d0930 

cd ~/sx1302_hal_rpi5-master/packet_forwarder/ sudo ./lora_pkt_fwd -c global_conf.json.sx1250.AU915 

TTS: 

https://au1.cloud.thethings.network/console/ account: 3218235207@qq.com password: SeeYouSkylarIn2027! 

Lorawan gateway EUI: 0x0016c001f15d0930 

End device: micromax-pico-receiving 

AppEUI: 0000000000000000 

DevEUI: 70B3D57ED00767BC 

AppKey: 81C7B9BBB0595DE5BB6D286A7BA275EE 

ERS Server Raspberry Pi 5 username: micromax password: pico 

# Structural refactor 

- **Modular Architecture Refactoring** : Successfully refactored the project from a flat, single-tier structure into a modular architecture, significantly improving code maintainability and scalability. 

- **Absolute Path Mapping Logic** : Implemented dynamic absolute path anchoring for all file references. This effectively eliminates the "File Not Found" issues previously caused by directory migration or environment changes. 

- **Standardized Dependency Management** : Compiled a comprehensive requirements.txt file, ensuring seamless environment replication and consistent performance across different hardware platforms. 

- **Comprehensive Documentation** : Completed the system's operational guide in README.md, providing clear instructions for setup, deployment, and troubleshooting 

# Map 

Completed the development of the map-related functionality in the Configuration module. The following features have been implemented: 

- Support for uploading office floor maps directly via the web interface 

- Ability to define real-world dimensions (in meters) of the office space 

- Flexible configuration of BLE gateways, including: Custom number of gateways; Manual placement using coordinate inputs (x, y) 

- Visualization of the uploaded map in the dashboard 

# Structural refactor 

Separated code files from non-code resources (e.g., maps, audio). Physical separation of code and assets has been completed. Refactoring of internal code references (imports) is still in progress 

Looking details in /home/micromax/emergency-response-system 

# Pico-lorawan test 

1. I have followed the instructions step by step in this webpage to test pico-lorawan: <u>https://www.waveshare.net/wiki/Pico-LoRa-SX1262</u> 

2. I have followed the instructions step by step in this webpage to download pico-sdk and 

test “say HELLO WORLD” (for skipping the lorawan to test RP2350 function): https://www.raspberrypi.com/documentation/microcontrollers/c_sdk.html 

# Objective 

1. Provide a “second-person” safety capability for staff working alone or away from others, ensuring emergencies are detected and escalated even when no one is nearby. 

2. Reduce the time between incident occurrence and response by automating alert initiation and notifying the right people immediately. 

3. Deliver reliable, multi-channel notifications (SMS, email, and on-site audio alarms) to minimise single points of failure and maximise the chance an alert is noticed. 

4. Support two distinct alert types with clear differentiation and workflows: Personal Assistance Alerts (individual needs help) and Mass Emergency Alerts (site-wide events such as fire or security threats). 

5. Improve coordination and decision-making during emergencies by providing actionable alert information (who/what/where/when) to enable timely and appropriate actions. 

6. Maintain auditable incident logs and notification records to support compliance, reporting, and continuous improvement of workplace safety processes. 

## **Research** 

### **2.  BLE modules and indoor positioning technology options** 

UWB: Install UWB anchors on ceilings or walls. Integrate a UWB tag into the wearable device. Estimate the tag’s position by measuring distances from multiple anchors and applying trilateration. UWB offers higher accuracy, delivers better results—always within 1 meter, but comes with higher hardware costs (anchors + tags) and higher power consumption. 

BLE: Install BLE beacons across indoor areas. Integrate a BLE module into the wearable device to periodically scan nearby beacons. Estimate the wearer’s indoor location using (i) proximity (zone) detection—assigning the user to the area where the strongest beacon/receiver is detected, or (ii) RSSI-based trilateration—using signal strength patterns from multiple beacons/receivers to infer position. BLE is low-cost and lowpower, widely supported and easy to deploy at scale, making it suitable for zone-level 

tracking and emergency alerts. However, its accuracy is highly sensitive to multipath, human body blocking, and environmental changes; RSSI fluctuates significantly indoors, so practical accuracy is often a few meters (and can degrade to 5–10+ meters in complex environments), requiring careful beacon placement and ongoing calibration if higher accuracy is needed. 

Currently, most products on the market use BLE for indoor positioning. 

|Name|Functon|Link|Cost|
|---|---|---|---|
|ED20W|<br>Connectvity<br>via<br>LoRa:communicaton<br>range up to 1.5KM line-<br>of-sight, 500~1000M in<br>dense<br>urban,<br>compatble with any<br>LoRaWANTM<br><br>Indoor &outdoor real-<br>tme tracking<br><br>Heart rate, body<br>temperature, blood<br>pressure,<br>and<br>Pedometer<br><br>SOS in emergency<br><br>Long Batery Life:<br>Batery life as long as 7<br>days @ 15mins uplink|htps://www.lpwanspace.com/collectons/devices-<br>health-monitoring/products/smart-wristband-<br>based-on-lorawan|$158.00|
||duty cycle|||
||<br>Support<br>dual|htps://www.mokosmart.com/lw014-lorawan-||
|LW014|independent alarm|wearable-panic-buton/?utm_source=chatgpt.com||
||triggers for diferent<br>emergency<br>types<br>(Customizable<br>SOS<br>alert buton and Side-|||
||mounted<br>physical<br>switch buton)<br><br>LoRaWAN V1.0.3<br>compliant, long-range<br>communicaton up to<br>5km in urban open<br>spaces<br><br>GPS and Bluetooth<br>positoning to address<br>indoor and outdoor|||



||emergency scenarios<br>efectvely<br><br>300mAh<br>magnetc<br>rechargeable batery||
|---|---|---|
||<br>Heart rate informaton|htps://www.globalsat.com.tw/en/|
|LW-360H|(Built-in optcal heart|product-259256/LoRa-GPS-Tracker-Watch-with-|
|R|rate monitor module)<br><br>Support GPS and BLE<br>functon<br><br>LoRa®<br>transmit<br>distance (Open space:<br>10km, City: 1km)<br><br>With built-in 250 mAh<br>lithium batery (<br>Batery life is 4 days by<br>user scenario)<br><br>Record daily actvites<br>as actvity tracking data<br>(track steps, calories<br>burned and distance)<br>for health status<br><br>Alarm with vibrator<br>and buzzer|Heart-Rate-Monitor-for-Senior-Health-Care-<br>LW-360HR.html|



### **3. Determine whether to rely on customer's Wi-Fi or provide independent** 

### **Wi-Fi network** 

Rely on the customer’s Wi-Fi: 

1. We cannot control their network load, channel planning, AP density, or roaming policies, so SOS latency and packet loss are not fully under your control. 

2. Customers often have mature security frameworks, but the onboarding process can be complex (e.g., certificate provisioning, network access control/NAC, MAC whitelisting, port restrictions). If issues occur, responsibility can also be difficult to clearly assign. 

3. Lower hardware cost. 

Provide an independent Wi-Fi network: 

1. Capacity can be designed and planned according to customer requirements, without being constrained by the customer’s existing network conditions. 

2. Faster troubleshooting with full observability: if device logs look normal but packets are being lost on the network, we don’t need to wait for the customer’s IT team to investigate APs, switches, or authentication servers. 

3. Enables a repeatable productised delivery model (reducing the effort of “network adaptation” for each customer deployment). 

