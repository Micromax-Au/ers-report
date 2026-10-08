

<!-- Start of picture text -->
aC3*)<br>+<br>aa<br><!-- End of picture text -->

Worked on fuzzy _logic.py and fuzzy_ t2.py. fuzzy_logic imports the other file and uses 3 fuzzy inference systems, 1 for getting a more accurate value of RSSI to distance, one for differentiating between adjacent rooms, and one for determining the weighting of trilateration vs centroid algorithms. This didn't work as well as hoped, as the paper on fuzzy logic in ble location had used a much more favorable setup using 6 gateways per room, no objects which can absorb or reflect signals, and used a fingerprinting technique rather than true trilateration. This technique requires much more setup and does not transfer to a new environment. 

BLE papers 

<u>https://www.sciencedirect.com/science/article/pii/S1570870525001866#sec6</u> 

Today I implemented a Kalman Filter into the code and set up the fourth gateway. To find code, the file is emergency_ response_system/ system/ble_ positioning _4gw.py. 

Minew G1 Gateway 1,2,3 Setup 

|Gateway|MAC|IP|
|---|---|---|
|1|AC:23:3F:C2:59:32|198.162.115.240|
|2|AC:23:3F:C2:6E:CB|198.162.115.241|
|3|AC:23:3F:C2:6E:CC|198.162.115.242|



MQTT broker running on raspberry pi at 192.168.115.49:1883 

All Gateway Password is Micromax1 

MAC must be filtered in server code rather than gateway for ease when setting up 



Access my trilateration attempt at 

emergency_response_system/server/ble_gateway_calibrate 

Use the ble transmitter on the desk 

Raspberry Pi 5 Debugging 

- UART to USB 

- Download and install drivers for USB connecter via 

<u>https://learn.adafruit.com/adafruits-raspberry-pi-lesson-5-using-a-consolecable/software-installation-windows</u> 

   - Open PuTTy and read outputs 

- 0.97 RPi: BOOTSYS release VERSION:2226a853 DATE: 2025/12/08 TIME: 19:29:54 

0.97 BOOTMODE: 0x06 partition 0 build-ts BUILD_TIMESTAMP=1765222194 serial b9f5ca8a boardrev d04171 stc 976650 

- 0.98 AON_RESET: 00000003 PM_RSTS 00001000 

- 0.99 POWER_OFF_ON_HALT: 0 WAIT_FOR_POWER_BUTTON 0 power-on-reset 1 

- 0.99 RP1_BOOT chip ID: 0x0000cf00 

- 1.00 I2C error @ 800058a2 

   - RP1_BOOT chip ID is wrong – must be `RP1_BOOT chip ID: 0x20001927` 

   - Error is not recoverable 

   - Could potentially be caused by UPS hat if I2C lines are being held high by an external device **before** the Pi's 3.3V regulator starts up, the PMIC gives up and won't power on the board. Repetition puts stress on RP1 chip over time 

|UPS...............................................................................................................................26|
|---|
|RTLS..............................................................................................................................27|



||Minew G1|Mokosmart MKGW3|Mokosmart LW003|
|---|---|---|---|
|0|-30db|-60db||
|1|-50db|-75db||
|2|-65db|-80db||
|3|-70db|-85db||
|4|-70db|-85db||
|5|-65db|-80db||
|6|-55db|-75db||
|7|-50db|-75db||



### Static IP of Minew G1 

- 

   - Now on Ethernet 

- Pi is on ethernet so that the G1 can connect to the MQTT broker now running on Pi 

- 

   - Config Page found at 192.168.100.34 

- Password is Micromax1 

### Gateway Comparison Chart 

|**Minew G1**|**MokoSmart mkgw3**|**Mokosmart LW003 - B**|
|---|---|---|
|**-**|**-**<br>**Easiest to setup**||



### **MKGW3 MokoSmart BLE – Wifi gateway** 

## **<mark>Step-by-Step Setup</mark>** 

1. **Power On:** Connect the MKGW3 via PoE or Micro USB (5V/1A). 

2. **App Installation:** Download the **<u>MKScannerPro app</u>** from the App Store or Google Play. 

3. **Connect to Gateway:** Power on the gateway, wait for the network LED to flash blue, and connect the app to the gateway's bluetooth signal. 

4. **Network Configuration:** Open the app and navigate to "Internet Access" to set up either Ethernet or WiFi (SSID and password). 

5. **MQTT Settings:** Configure the MQTT broker parameters (URL/IP, Port, Username, Password) in the app's server access section to connect to your cloud platform. 

6. **Scan Filters:** Customize scanning filters (RSSI, MAC Address, Raw Data) for BLE beaconing devices. 

### **UPS Battery Safe Shutdown** 

Set at 3.2V running as service ups-shutdown.service 

To check service log check file battery_log.txt in home folder on pi 

The timestamp associated with the latest “Executing Safe Shutdown” is the time the Pi power went down 

### **Battery Check** 

Time Unplugged - 4:10pm 9/04/26 

Shutdown Time – 2:02am 10/04/26 

Total Runtime (Running Server and Webpage) – 9h 52m 

Time Text Received @ 3.3V – 1:34am 10/04/26 

Battery Percentage @ Shutdown – 0.0 % 

#### **Battery Differences** 

#### **600mAh** 

Start – 9:30am Died – 3:15pm Total – 5h 45m Cutoff Voltage – 3.4V Cutoff Percentage – 35% 

#### **1100mAh** 

Start – 5:00pm Died – 3:30am Total – 10h 30m Cutoff Voltage – 3.55V Cutoff Percentage – 46.3% 



<!-- Start of picture text -->
USB power output<br>(maximum 5V, 2.44)<br>eo 44 @<br>USB type A 5V z'o! —a-eeie — fe Ri weve<br>power output switch woefj: ao Be. ES© o&. || @@—OM3 maMN<br>5V output enable ES) cee OH tk hg © 5v Full function<br>indicator Call | Ge Sta © GNo peader<br>Battery ak » Eee ia} © BAT<br>level indicator lar ‘= @ le — ie 4 USB<br>Chargestatus indicator + Tr at i<br>oni7) iadho ot<br>r J 4 USB TYPE C<br>JST2.0 Battery Port<br><!-- End of picture text -->



<!-- Start of picture text -->
USB<br>|<br>wl<br>2 bee<br>Ey __vsvs__|<br>3 : 38<br>4 if 3V3_EN|<br>5 36<br>6 35<br>Lc 89 | ; 32<br>-a 7|10 ; 31$0<br>12 - 29<br>3 ay GND<br>14 27<br>15 26<br>16 25<br>17 24<br>8 23<br>2019 20 : a1 2221<br>_Z& ups Boot<br><!-- End of picture text -->

VBUS Charger power input VSYS Battery power output 3V3(OUT) 3.3V power output | GPE | | SDA Voltage/Current monitor SDA pin ScoSCL Voltage/Current monitor: SCL pin: 

#### **Pi 5 UPS Hat** 

#### **GPIO Used** 

**GPIO2, GPIO3, GPIO6, GPIO16** 

**Followed Guide at :** 

**-** **<u>https://suptronics.com/Raspberrypi/Power_mgmt/x1202 v1.1_hardware.html</u>** 

**Batteries stops charging at 90%, continues charging if it drops below: Change in file qtx120xTerminal.py.** 

On-board LEDs indicate battery charging and discharging levels of 25%, 50%, 75%, and 100% 

#### **MPU6050 Testing MPU6050 testing included connecting to pi pico and running the following code** 

#### **This checks that values are beings sent via i2c and confirms that the acceleration is approximately 1 when flat and still.** 

""" MPU-6050 Test Script for Raspberry Pi Pico 

------------------------------------------Wiring: MPU-6050 VCC  -> Pico 3.3V (pin 36) MPU-6050 GND  -> Pico GND  (pin 38) MPU-6050 SDA  -> Pico GP4  (pin 6) MPU-6050 SCL  -> Pico GP5  (pin 7) MPU-6050 AD0  -> GND       (I2C address = 0x68) or 3.3V   (I2C address = 0x69) """ 

import machine import time 

# ── I2C & MPU-6050 setup 

────────────────────────────────────────────────────── 

I2C_SDA_PIN = 4 I2C_SCL_PIN = 5 I2C_FREQ    = 400_000 MPU_ADDR_LOW  = 0x68   # AD0 tied to GND MPU_ADDR_HIGH = 0x69   # AD0 tied to 3.3V # Registers REG_PWR_MGMT_1 = 0x6B REG_WHO_AM_I   = 0x75 REG_ACCEL_XOUT = 0x3B  # 6 bytes: AX_H AX_L AY_H AY_L AZ_H AZ_L REG_GYRO_XOUT  = 0x43  # 6 bytes: GX_H GX_L GY_H GY_L GZ_H GZ_L REG_TEMP_OUT   = 0x41  # 2 bytes: T_H T_L ACCEL_SCALE = 16384.0   # ±2 g  (default) GYRO_SCALE  = 131.0     # ±250 °/s (default) 

# ── Helpers 

──────────────────────────────────────────────────────────── 

─────── 

def to_signed(value): """Convert unsigned 16-bit to signed.""" return value - 65536 if value > 32767 else value 

def read_word(i2c, addr, reg): 

data = i2c.readfrom_mem(addr, reg, 2) return to_signed((data[0] << 8) | data[1]) 

def wake_sensor(i2c, addr): """Clear the SLEEP bit so the sensor starts sampling.""" i2c.writeto_mem(addr, REG_PWR_MGMT_1, bytes([0x00])) 

def read_all(i2c, addr): raw = i2c.readfrom_mem(addr, REG_ACCEL_XOUT, 6) ax = to_signed((raw[0] << 8) | raw[1]) / ACCEL_SCALE ay = to_signed((raw[2] << 8) | raw[3]) / ACCEL_SCALE az = to_signed((raw[4] << 8) | raw[5]) / ACCEL_SCALE 

raw = i2c.readfrom_mem(addr, REG_GYRO_XOUT, 6) gx = to_signed((raw[0] << 8) | raw[1]) / GYRO_SCALE gy = to_signed((raw[2] << 8) | raw[3]) / GYRO_SCALE gz = to_signed((raw[4] << 8) | raw[5]) / GYRO_SCALE 

raw_t = i2c.readfrom_mem(addr, REG_TEMP_OUT, 2) temp_raw = to_signed((raw_t[0] << 8) | raw_t[1]) temp_c = temp_raw / 340.0 + 36.53 

return ax, ay, az, gx, gy, gz, temp_c 

# ── Test routine 

──────────────────────────────────────────────────────────── 

── 

def test_sensor(i2c, addr, label): print(f"\n{'='*50}") print(f"  Testing: {label}  (address 0x{addr:02X})") print(f"{'='*50}") # 1. Check WHO_AM_I try: who = i2c.readfrom_mem(addr, REG_WHO_AM_I, 1)[0] except OSError: print(f"  [FAIL] No response at 0x{addr:02X} — check wiring / AD0 pin") return False expected = 0x68 if who != expected: print(f"  [FAIL] WHO_AM_I = 0x{who:02X}, expected 0x{expected:02X}") return False print(f"  [PASS] WHO_AM_I = 0x{who:02X}") # 2. Wake the sensor wake_sensor(i2c, addr) 

time.sleep_ms(100) 

# 3. Take 5 samples and print them print(f"\n  {'Sample':<8} {'Ax(g)':>8} {'Ay(g)':>8} {'Az(g)':>8}" f"  {'Gx(°/s)':>9} {'Gy(°/s)':>9} {'Gz(°/s)':>9}  {'Temp(°C)':>9}") print(f"  {'-'*80}") 

samples = [] for i in range(5): ax, ay, az, gx, gy, gz, temp = read_all(i2c, addr) samples.append((ax, ay, az, gx, gy, gz, temp)) print(f"  {i+1:<8} {ax:>8.3f} {ay:>8.3f} {az:>8.3f}" f"  {gx:>9.2f} {gy:>9.2f} {gz:>9.2f}  {temp:>9.2f}") time.sleep_ms(200) 

# 4. Sanity checks print() avg_az = sum(s[2] for s in samples) / len(samples) avg_temp = sum(s[6] for s in samples) / len(samples) 

issues = [] 

# Flat sensor: Az should be close to ±1 g if not (0.8 < abs(avg_az) < 1.2): issues.append(f"Az avg = {avg_az:.3f} g  (expected ~±1.0 g when flat)") 

# Temperature should be in a sensible range if not (10 < avg_temp < 85): issues.append(f"Temperature = {avg_temp:.1f} °C  (out of plausible range)") 

if issues: for issue in issues: print(f"  [WARN] {issue}") else: print(f"  [PASS] Accel Z ≈ {avg_az:.3f} g  (gravity looks correct)") print(f"  [PASS] Temperature ≈ {avg_temp:.1f} °C") 

overall = len(issues) == 0 print(f"\n  Result: {'✓ SENSOR OK' if overall else '✗ CHECK WARNINGS ABOVE'}") return overall 

# ── Main 

──────────────────────────────────────────────────────────── 

────────── 

def main(): i2c = machine.I2C(0, sda=machine.Pin(I2C_SDA_PIN), scl=machine.Pin(I2C_SCL_PIN), freq=I2C_FREQ) 

print("\nMPU-6050 SENSOR TESTER") print("Keep the sensor flat and still during the test.\n") 

# Scan to show what's on the bus devices = i2c.scan() if devices: print("I2C devices found:", [hex(d) for d in devices]) else: print("[ERROR] No I2C devices found — check wiring and power.") return 

# Test whichever address responds results = {} if MPU_ADDR_LOW in devices: results["AD0=GND (0x68)"] = test_sensor(i2c, MPU_ADDR_LOW,  "AD0=GND (0x68)") if MPU_ADDR_HIGH in devices: 

results["AD0=3V3 (0x69)"] = test_sensor(i2c, MPU_ADDR_HIGH, "AD0=3V3 (0x69)") 

# Summary print(f"\n{'='*50}") print("  SUMMARY") print(f"{'='*50}") for label, ok in results.items(): status = "✓ PASS" if ok else "✗ FAIL" print(f"  {status}  {label}") print() 

main() 

#### **Pico Controlling Seeed** 

#### **Lowest seen rssi value –77db** 

#### **Wiring** 

#### **Pico – Seeed** 

GP0 -  RX GP1 – TX GND – GND 

#### **Pico – Button** 

GP15 – Button GND – GND 

**Pico code from machine import UART, Pin import time** 

**uart = UART(0, baudrate=9600, tx=Pin(0), rx=Pin(1)) button = Pin(15, Pin.IN, Pin.PULL_UP)** 

#### **print("Waiting for button press...")** 

**while True:** 

**if button.value() == 0: print("Button pressed - telling XIAO to advertise!") uart.write("START\n") time.sleep(1) time.sleep(0.05)** 

#### **Seeed Code** 

<mark>#include <bluefruit.h></mark> 

bool advertising = false; unsigned long adStartTime = 0; const unsigned long AD_DURATION = 5000; 

void setup() { Serial.begin(115200); Serial1.begin(9600); Bluefruit.begin(); Bluefruit.setTxPower(4); 

<mark>Bluefruit.setName("XIAOBeacon");</mark> 

Bluefruit.Advertising.addFlags(BLE_GAP_ADV_FLAGS_LE_ONLY_GENERAL_DISC_MODE); Bluefruit.Advertising.addName(); 

Bluefruit.Advertising.setInterval(80, 80); 

Bluefruit.Advertising.setFastTimeout(0); 

Serial.println("Ready - waiting for signal from Pi..."); 

} 

void loop() { 

if (Serial1.available()) { 

String msg = Serial1.readStringUntil('\n'); 

msg.trim(); 

if (msg == "START") { 

Serial.println("Received START - advertising for 30 seconds..."); Bluefruit.Advertising.start(0); 

advertising = true; 

adStartTime = millis(); 

} 

} 

if (advertising && millis() - adStartTime >= AD_DURATION) { Bluefruit.Advertising.stop(); 

advertising = false; 

Serial.println("30 seconds done - stopped advertising."); 

} 

} 

#### **Minew G1 Ble to Wifi with Seeed** 

Followed setup at https://wiki.seeedstudio.com/XIAO_BLE/ 

**Find mac by running** 

**Change gateway config to filter by the new mac Advertise Ble** 

**#include <bluefruit.h>** 

**void setup() { Serial.begin(115200);** 

**Bluefruit.begin(); Bluefruit.setTxPower(4); Bluefruit.setName("XIAOBeacon");** 

**Bluefruit.Advertising.addFlags(BLE_GAP_ADV_FLAGS_LE_ONLY_GENERAL_DISC_MO DE);** 

**Bluefruit.Advertising.addName(); Bluefruit.Advertising.setInterval(160, 160); Bluefruit.Advertising.setFastTimeout(0); Bluefruit.Advertising.start(0);** 

**Serial.println("Advertising as 'XIAOBeacon'");** 

**}** 

**void loop() { delay(5000); Serial.println("Still advertising...");** 

**}** 

#### **Minew G1 Ble to Wifi with Pico** 

Connected to g1 via AP. Connect to network GW-MACADRESS. Access config portal at 192.168.99.1. Set network settings to connect to Micromax Wifi. 

Run “for /l %i in (1,1,254) do ping 192.168.115.%i -n 1 -w 50 >nul” followed by arp –a to find the ip the dashboard will now be found at and match the mac address 

Then access config page via that ip  Config to mqtt and filter by pi mac address 

Find by running on pi : import bluetooth ble = bluetooth.BLE() ble.active(True) mac = ble.config("mac") print("MAC:", bytes(mac[1]).hex(":")) 

Advertise BLE from pico using : 

import bluetooth import struct import time from micropython import const 

_ADV_TYPE_FLAGS = const(0x01) _ADV_TYPE_NAME = const(0x09) _ADV_TYPE_MANUFACTURER = const(0xFF) 

DEVICE_NAME = "PicoBeacon" # Name the G1 will see ADV_INTERVAL = 100 # Advertising interval in ms (100ms is standard) COMPANY_ID = 0xFFFF # Fake company ID for manufacturer data DEVICE_ID = 0x0001 # Custom ID to identify this specific Pico PICO_SIGNATURE = "88a29e1231b5" 

def build_adv_payload(name: str, device_id: int) -> bytes: """ Build a BLE advertisement payload with: - Flags (LE general discoverable, no BR/EDR) - Complete local name - Manufacturer specific data (company_id + device_id for easy filtering) """ payload = bytearray() 

def append_field(adv_type: int, data: bytes): payload.extend(struct.pack("BB", len(data) + 1, adv_type)) payload.extend(data) 

# Flags: LE General Discoverable Mode, BR/EDR Not Supported append_field(_ADV_TYPE_FLAGS, struct.pack("B", 0x06)) 

# Complete Local Name 

name_bytes = name.encode("utf-8") append_field(_ADV_TYPE_NAME, name_bytes) 

# Manufacturer Specific Data: [company_id LE 2B] + [device_id LE 2B] mfr_data = struct.pack("<HH", COMPANY_ID, device_id) append_field(_ADV_TYPE_MANUFACTURER, mfr_data) 

return bytes(payload) 

def run(): print("Initialising BLE...") ble = bluetooth.BLE() ble.active(True) 

# Optional: set a fixed name visible to central devices ble.config(gap_name=DEVICE_NAME) 

payload = build_adv_payload(DEVICE_NAME, DEVICE_ID) 

# interval_us = ADV_INTERVAL * 1000 (microseconds) 

ble.gap_advertise(ADV_INTERVAL * 1000, adv_data=payload) 

print(f"Advertising as '{DEVICE_NAME}' every {ADV_INTERVAL}ms") print(f"Payload ({len(payload)} bytes): {payload.hex()}") print("Press Ctrl+C to stop.\n") 

heartbeat = 0 

while True: time.sleep(5) heartbeat += 1 print(f"[{heartbeat * 5}s] Still advertising...") 

if **name** == " **main** ": try: run() except KeyboardInterrupt: print("\nStopped.") ble = bluetooth.BLE() ble.gap_advertise(None) # Stop advertising cleanly ble.active(False) 



<!-- Start of picture text -->
sae wicealeSS-<br>fv ioso feionm<br>Accel tox tlersy<br>Clon<br>a<br>g o= = 4<br>Ohio. — dats loo<br>ee - Stag Sensor :<br>rate gern .<br>“A =<br>|<br>Ble Y<br>tector b<br>: _ Det prec<s5)<br>Passive Mra S \ 7 \ -AlectpnnkiasAcct e ton<br>Alec 5 - Aches erany bores J<br>alah boacal -<br>\<br>|<br>_<br>fe, ash Parl O :<br>phon toads) _ -- = al<br>\ | ori: %<br>l f= ~<br>alects alerts alerts<br>5,<br><!-- End of picture text -->

LoRawan Indoor Transmission Range 

- With a single gateway LoRaWAN can have an indoor transmission range of 200500m in dense areas such as office spaces. The Gateway should be positioned in the middle of the transmission area to cover the most area and avoid disrupted signals. 

### Ble Packet Size 

- Ble has a MTU of 512bytes before headers are added. This could be suitable if we are only sending small packets of information such as if a fall occurs and if the panic button was pressed, however if we decide to add more features the packets may need to be fragmented which will reduce throughput and leave room for corrupted data. 

Options for Indoor Positioning 

Ble and UWB are the most viable indoor positioning systems for this project as they both provide highly accurate positioning and use little power. 

- Ble is the most used indoor positioning and is most applicable to the ERS due to its low power consumption and high accuracy. This will need gateways around the office installed and research done to manage strength of signal 

- UWB offers higher accuracy for indoor positioning, however for our application a cm level accuracy is not required, and the tradeoffs for this accuracy are not worth it as it has a higher power consumption and much more difficult to set up infrastructure 

### LoRaWAN latency 

- Latency is dependent on whether the device is always listening for a transmitted signal. This will consume more power but have lower latency. Latency in this mode will be a maximum of a few seconds as we will constantly be transmitting signals to ensure fast system response as this is the main objective of the system 



<!-- Start of picture text -->
; ; | MaxBox<br>Client Device 1 mud Gateway - (Optional) Intermet<br><!-- End of picture text -->



<!-- Start of picture text -->
——Fall Detection Sensor<br><!-- End of picture text -->



<!-- Start of picture text -->
Audio Out SMS Out eSIM Module<br>Email Out Relay Qut Relay Box<br>Uninterupptable<br>Power Supply<br><!-- End of picture text -->

### **Part options** 

### <u>Already made;</u> 

Client Device 

- LW014 Panic Button/Fall detector 

- Mokosmart H8 tag with accelerometer 

- Mokosmart B1 Bluetooth panic button 

Gateways 

- LoRaWAN gateways 

### Server 

- Likely own computer 

### <u>Custom parts;</u> 

Client Device 

### MCU 

- Pi Pico W (wifi and bluetooth) 

- ESP32 (wifi and Ble) 

Gateway 

### Server 

- Raspberry Pi 5 

- MaxBox 

- Any server computer 

- ESIM module 

- Relay Box 

- PA System (likely already installed) 

# UPS 

# RTLS 

### RSSI Fingerprinting 

- Use 4 gateways in each corner of the building 

- Calibrate by creating a grid within the office and taking and averaging around 1 minute worth of rssi readings for each gateway and each grid box gets its own signature 

- When the data comes in collect the rssi for each gateway from the tag and complete a Euclidean distance against all stored rssi values 

- Choose the smallest distance from a signature and this is the grid box that the emergency has occurred in 

Can do this for a certain area not necessarily grid spaces; maybe rooms instead would require less calibration but less accuracy, but then room accuracy could still be very helpful for this case. 

Pico cannot have antenna attached to it as it only uses internal antenna, and has an open range of only 10-20m, which is reduced by walls etc. 

Particle argon microcontroller with Nordic nRF52840 (same as Moko H8 Ble button), Wi-Fi capabilities and additional antenna that can be used for either Bluetooth or Wi-Fi. This Ble chip as seen with the h8 identification tag has a much higher range than the pi Pico (10m indoors if lucky) and should also be able to have the same functions as the pi Pico. 

- - <u>https://core electronics.com.au/particle argon.html? gad_source=1&gad_campaignid=17417005429&gbraid=0AAAAADlEpP70KukaoRAQL4Rg_ TshMZBCB&gclid=CjwKCAiAncvMBhBEEiwA9GU_fSwhpfb1ARqkWHOMWH5tAAt3rfOKJbl LBoxyBBV6oOuRZJ3GO0GRoCMwEQAvD_BwE</u> 

Minew G1 IOT Bluetooth gateway claims up to 300m range (line of sight) with an indoor range of around 35-40m, higher than any other Ble gateway I have seen but still not what we were hoping for (100m) 

<u>https://www.minew.com/product/g1-iot-bluetooth-gateway/</u> 



<!-- Start of picture text -->
Distance 7 11<br>(m)<br>RSSI(dBm) -15 -65 -68 -75 -/76 -80 -77 -/74 -84 -86 -87 -89<br>de »<br><!-- End of picture text -->



<!-- Start of picture text -->
RSSI level<br>0<br>oo 0 7] 8] 9 Oo} 11) 71S 20 5<br>E<br>oo<br>= -50<br>ra<br>uy<br>o<br>-100<br>Distance (m)<br>B Hall @ Boardroom<br>@ Boardroom Through glass door @ Office (1 Dry wall)<br>B Office - (1 Dry Wall) - diagonal<br><!-- End of picture text -->

