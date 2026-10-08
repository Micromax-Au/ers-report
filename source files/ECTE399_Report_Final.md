













<!-- Start of picture text -->
Professional<br>Experience Report<br>ECTE399<br>Thomas Robert Speer<br><!-- End of picture text -->

Professional Experience Report ECTE399 Thomas Robert Speer 7679877 





<!-- Start of picture text -->
7679877<br><!-- End of picture text -->











**0** | **PROFESSIONAL EXPERIENCE REPORT** 

# ECTE399 Professional Experience Report Coversheet 

###### **School of Engineering** 



|**Category**|**Descrip�on**|
|---|---|
|**Student Name**|**Thomas Robert Speer**|
|**Student Number**|7679877|
|**Student Discipline**|Electrical and Electronics|
|**Subject Code**|ECTE399|
|**Placement Dates**|19/01/2026 – 24/06/2026|
|**Duration**|During Uni-Break - 5 weeks x 4 days per week<br>In Uni Semester - 14 weeks x 2.5 days per week (even<br>weeks 3 days per week, odd weeks 2 days per week)<br>Total – 60 Days|
|**Organisation Name**|Micromax Technologies|
|**Organisation**<br>**Address**|5 Orangegrove Ave, Unanderra NSW 2526|
|**Organisation**<br>**Website**|https://micromaxtechnology.com/|
|**Mentor Name**|Shakif Aziz|
|**Mentor Title**|Research and Development Team Leader|
|**Mentor Phone**|0242237602|
|**Mentor Email**|saziz@micromax.com.au|
|**Mentor Qualifcation**|Bachelor of Engineering - Honours (Computer<br>Engineering)|
|**Mentor Title**|Research and Development Team Leader|
|**Word Count**|4635|
|**Student Signature**||
|**Submission Date**|2/07/2026|

















**1** | **PROFESSIONAL EXPERIENCE REPORT** 

## Contents 

|1<br>INTRODUCTION....................................................................................................................... 3|
|---|
|2<br>COMPANY DESCRIPTION..................................................................................................... 4|
|3<br>WORK DESCRIPTION............................................................................................................. 4|
|4<br>EVALUATION............................................................................................................................. 8|
|4.1<br>Experience Learned....................................................................................................... 8|
|4.2<br>Achievements and Milestones................................................................................... 9|
|4.3<br>Link to Degree................................................................................................................ 10|
|4.4<br>Feedback on the Organisation / Overall satisfaction....................................... 12|
|**Conclusion**............................................................................................................................................................ 12|
|Appendix ................................................................................................................................................................ 14|
|ECTE399 Professional Experience – Marker’s Report ................................................................. 28|

















**2** | **PROFESSIONAL EXPERIENCE REPORT** 

## 1 INTRODUCTION 

This report outlines the professional experience I gained during my ECTE399 placement at Micromax Technologies in Unanderra, New South Wales. Micromax Technologies focuses on IT infrastructure such as people and traffic counting. 

This placement was undergone from the January 2026 – June 2026 working full time during university break and part time during university semester to complete a total of 60 days. My role throughout this internship was Electrical Engineering Intern as part of the Research and Development Team. 

My placement provided lots of experience where I mainly continued a project that I had previous experience with in ECTE351.  The main goal of this internship was to get the Emergency Response System to a point that could be deployed around the Micromax office for testing and to improve and add features that were not within the scope of the initial ECTE351 project. Throughout this placement I gained experience with IoT Devices, sensor integration, Computer Aided Design and Wireless Communications including LoRaWAN and Wi-Fi. 

This internship provided an opportunity to apply theoretical knowledge gained throughout my Electrical and Electronics Engineering degree to a professional setting and helped bridge the gap between theoretical and practical knowledge. 

This report is an overview of my ECTE399 placement at Micromax Technologies and includes a company description, work description and evaluation of the work I completed during my internship. 















**3** | **PROFESSIONAL EXPERIENCE REPORT** 

## 2 COMPANY DESCRIPTION 

Micromax Technology works across many industries such as healthcare, industrial, transport, retail and commercial sectors. The company consists of 20 team members across 4 departments: Sales, Service, R&D and Administration. 

The core services provided by Micromax Technology is providing traffic and people counting solutions to many shopping centres around Australia, however they focus on many other services as well including providing health services with smart solutions such as patient monitoring. 

Micromax’s main values are having a customer first approach, innovation in action, collaboration, integrity, sustainability and excellence. 

Some achievements and projects Micromax are proud to have worked on are their people counting solution for Sydney’s Mardi Gras, and their AI Gender Detection from CCTV Footage for retail centres. 

## 3 WORK DESCRIPTION 

Throughout my time at Micromax Technology my role was Electrical Engineering Intern as part of the Research and Development team. My main responsibility for the placement was continuing the development of the Emergency Response System (ERS), a project I had started previously in ECTE351. The goal was to take the system from an early prototype to a point where it could be deployed around the Micromax office as a test site, while also improving on it and adding features that were never within the scope of the original university project. Because the ERS was an ongoing R&D project rather than a set task, my day-to-day work varied a lot and covered hardware, software, wireless communications, testing and mechanical design. Working on a live company project rather than a university assignment also meant the decisions I made had to hold up in a real environment, which shaped the way I approached everything from choosing components to writing documentation. 

At the start of the placement, I completed the standard induction and site tour, then set up my existing ECTE351 prototype so I could show the team the progress that had already been made and use it as a reference point for where the project needed to go. I met with the head director to understand the company's expectations for the ERS, which helped me define the direction of the work early on. From there I spent time on documentation and research to define exactly what the system needed to do, which involved finalising a system specification 















**4** | **PROFESSIONAL EXPERIENCE REPORT** 

document and putting together a procurement list of suitable parts. Before committing to any components, I tested a number of options to see what would actually work for the ERS, including a previous LoRaWAN prototype, a BLE to WiFi gateway, a Mokosmart panic button, a LoRa switch transceiver and the HLKLD2410C human presence detector. Getting hands-on with these early on helped me understand the trade-offs between the different communication protocols and sensors, and I documented the results so the team would have a reference for future use. I also produced architecture diagrams for the system and digitised them so the overall design was clear and could be shared with the rest of the team. 

A large part of the client-side device work was around the emergency triggers themselves. I set up the button so that it could tell the difference between a mass emergency and a personal emergency, using a set number of presses for one and a press-and-hold for the other, and then had that button press signal sent to a server that logged the type of emergency and the time it was pressed. From there I built out the response side of the system. I created an email workflow and an SMS workflow so that the right people would be notified with information about the type of emergency when an alert was triggered and set up the triggered client device to play an audio alert and open a relay so the system could interact with other equipment on site. Building both the trigger logic and the notification workflows meant I had to think carefully about how the system would behave in an actual emergency, and about making sure the correct information reached the right people quickly and reliably. 

Fall detection was one of the more involved features I worked on. I ran a series of calibration trials, graphing the acceleration peaks and timing against real movements so I could get a visual representation of what values indicated a genuine fall. I tested different types of falls using a mattress to work out the maximum threshold needed to reliably detect a fall without setting the system off unnecessarily, then programmed the fall detection algorithm around those thresholds. To make the system more usable in a real environment I added a false alarm protection feature, so that if a fall was detected but help wasn't needed, the client had a ten second window to cancel the request before anyone was notified. I documented the whole experiment and the justification for the threshold values I chose so the decisions were traceable, which was important given that the reliability of a feature like fall detection has real consequences if it gets it wrong. Later in the placement I also tested new MPU6050 modules to make sure they were all working correctly for this part of the system. 

Communications and indoor positioning ended up being a running theme across the whole placement. I started by taking RSSI readings from a BLE tag through multiple obstacles to get an average value at a set distance and wrote a script that could determine whether the tag was within roughly two metres of a 















**5** | **PROFESSIONAL EXPERIENCE REPORT** 

gateway and start a timer that stopped if the tag left that area. I researched how Real Time Location Systems (RTLS) are implemented in other buildings and how that could be applied to our solution and looked into how previous studies had achieved indoor positioning using BLE so I wasn't starting from scratch. As the work progressed it became clear that BLE alone would not be reliable enough, so I redesigned the communication redundancy around LoRaWAN. I researched how a BLE to Wi-Fi gateway could be replaced with a BLE to LoRaWAN gateway, using LoRaWAN as a backup communication protocol so that location and alert services could still function even if the Wi-Fi went down. Later in the placement I combined my own server and Pico scripts with a colleague's scripts to bring the LoRaWAN capability into the main system, using Wi-Fi as the backup, and worked through the issues that came up when integrating everything together, which was a good exercise in getting separate pieces of work to function as one system. 

To support the positioning work I tested and compared a range of gateways and modules, including the Minew G1, the Mokosmart MKGW3 PoE BLE to Wi-Fi gateway, and Seeed nRF52840 BLE modules sending packets through to the gateway and viewing them on MQTT Explorer. I tested the range of the gateways at different distances around the office and built a comparison table of all the different BLE gateways I tested so the team could see how each one performed. I also set up a configuration where a Raspberry Pi Pico triggered the alarm while an nRF52840 module sent the BLE signal for the gateway to pick up, which was intended to be used for indoor footprinting from the RSSI values. Towards the end of the placement, I worked on a trilateration algorithm to try and calculate indoor location from the RSSI readings, added a fourth gateway to improve accuracy, and experimented with applying fuzzy logic and Kalman filtering to the trilateration and centroid algorithms to see whether cleaner results could be achieved. I also sat in on a visit from BlueIOT to discuss a potential partnership and their current and future positioning products, which gave me a good look at how these problems are being solved commercially and how our approach compared. 

Alongside the positioning work I developed the software side of the ERS. I built a graphical user interface connected to a database so that customers could see all the emergency data in one place, with the interface split across multiple pages including a Dashboard, a Logs page, a Staff page and a Configuration page. The Staff page let an administrator assign an email and phone number to each staff member, and the Configuration page let them allocate specific devices to staff and decide which staff would receive alerts if an emergency occurred. I added a number of practical features to the GUI, such as a stop button for the mass emergency trigger so the relay and audio alerts could be shut off once danger had cleared, the ability to export logs as a CSV file, and an evacuation drill function that ran the same workflow as a real mass emergency but was classified 















**6** | **PROFESSIONAL EXPERIENCE REPORT** 

as a test in the database. To make the logs more usable for office audits I moved them into an SQLite database so they could be filtered and read more easily. I spent a good amount of time testing every feature of the GUI and trying to find anything that was broken and fixed the webpage on the occasions where a change had stopped it running correctly. Working on the interface taught me to think about the system from the point of view of the person who would be using it day to day, not just from an engineering perspective. 

Power and battery management was another significant area of the work, given the device needed to run reliably for a full day. I bench tested and compared different power options, including the Seeed LiPo Rider Plus and the Waveshare Pico UPS B, and tested their battery capacities to work out which would best suit the ERS while still allowing for a whole day of use with a factor of safety above 1.5. I got the Pico to display an LED when the battery dropped below a certain level to indicate that charging was needed and worked on showing the client-side device's battery percentage on the server webpage, with low battery alerts sent by SMS or email depending on the configured admin settings. I also started reworking the battery percentage so that it followed the actual discharge curve rather than a straight line, which made the reading far more accurate, and remapped the range so the full scale accounted for the shutdown voltage rather than cutting out with charge still showing. I also tested UPS options for the Raspberry Pi 5 and the Pico so that the different parts of the system could keep running as intended. 

The placement also gave me a lot of mechanical and hardware design experience. I created a CAD model of the ERS client-side device to design an enclosure that could be used to deploy the system around the office, deliberately leaving access holes in the early versions so the device could still be reprogrammed as needed. I went through several iterations of the 3D model, printing and checking dimensions before refining the design each time and redesigned the enclosure again later to suit the final soldered prototype. I reverse engineered and drew up a schematic diagram for a traffic counter that had no existing documentation, which gave me experience reading and interpreting undocumented hardware and turning it into something the company could use. I also worked with KiCad for PCB design as part of taking the client device further, and near the end of the placement I soldered two vero board prototypes, one built for display so all of the components could be seen and explained, and another made as small as possible for functionality and further testing. 

Throughout all of this I worked closely with the rest of the R&D team and reported progress to my mentor on a regular basis, including demonstrating the ERS dashboard and running a full product demonstration to all staff. Toward the end of the placement, I contributed to the final presentation and the client tutorial, and I also helped set up and test a piezoelectric sensor used for traffic counting 















**7** | **PROFESSIONAL EXPERIENCE REPORT** 

so that the next group of ECTE351 students would have working equipment to collect. The tools and technologies I used across the placement included KiCad, CAD and 3D printing, SQLite, MQTT Explorer, Python scripting, and a range of hardware such as the Raspberry Pi Pico, Raspberry Pi 5, nRF52840 modules, MPU6050 sensors and various BLE and LoRaWAN gateways. Working across so many different areas meant I was constantly switching between hardware, software and design tasks, which gave me a broad view of what it takes to develop a product rather than just one narrow part of it . 

## 4 EVALUATION 

#### 4.1 Experience Learned 

This placement gave me a large amount of both technical and professional growth, a lot of which came from working with technologies that were never introduced during my degree. The clearest example of this was LoRaWAN. I had no real experience with it going into the placement, but by the end I understood how to use it as a communication protocol and how to build it into a system as a backup to Wi-Fi so that the ERS could keep functioning even if the main network went down. In the same way, I picked up a few tools and skills that I was unfamiliar with at the start. I had never used KiCad or done any PCB design before, and I got comfortable with both over the course of the placement. I also learned to work with MQTT for passing messages between devices and gateways, and SQLite for storing and filtering the emergency logs in a way that would be useful for office audits. Getting exposure to all of these gave me a much broader practical toolkit than I had coming in and showed me how quickly you can pick up a new technology when you have a real reason to use it. 

Beyond the specific technologies, the biggest thing I took away was real practical experience of building something ends to end. A lot of what I had learned at university was theoretical, and this placement let me apply that theory to an actual product that had to work in the real world. Seeing a concept move from research and testing all the way through to a working device taught me a lot about the parts of engineering that don't always come across in coursework, like the amount of iteration, testing and documentation that goes into getting something reliable. I also learned that a solution that works once on the bench is not the same as a solution that works consistently once it is deployed, and a lot of my time went into that gap between something functioning and something being dependable. 

There were also challenges that I had to work through, and not all of them ended the way I would have liked. The indoor positioning was the hardest problem I faced. I put a lot of effort into improving the accuracy of the location data, 















**8** | **PROFESSIONAL EXPERIENCE REPORT** 

including implementing fuzzy logic and Kalman filtering to try and clean up the RSSI readings and adding a fourth gateway, but unfortunately, I ran out of time before I could get it to the standard I wanted, and it had to be left where it was. While it wasn't fully finished, working on it taught me a lot about the limits of RSSI-based positioning and about the reality that not every problem gets solved within the time available. It also taught me the value of documenting where I got to and what I had tried, so that whoever picks the work up next has a clear starting point rather than having to repeat what I had already done. The Raspberry Pi 5 boot issue was another challenge that took up a lot of time. I spent a while trying to diagnose and work around it, and in the end the solution was to move to a new Raspberry Pi, but it was a good lesson in knowing when to stop chasing a fault and take a different path so the rest of the project could keep moving. 

On the professional side I improved a number of skills that had nothing to do with the hardware itself. My documentation improved a lot over the placement, which was something my mentor specifically noted, and I got much better at managing a project over a long period of time while balancing full-time work during the break and part-time work during semester. Managing my own time and deciding what to prioritise when there was always more that could be done was a skill, and it is something I got noticeably better at as the placement went on. I also learned a great deal about working to client expectations and delivering a finished product, rather than just getting something working on the bench, which is a different mindset to the one I was used to from university assignments. Presenting my work to the director and to the rest of the staff also made me more confident at explaining technical decisions clearly to other people, including people who weren't necessarily across the detail of the project. 

#### 4.2 Achievements and Milestones 

The achievement I am most proud of from this placement was delivering a working prototype inside a finished enclosure by the end of the internship. That was the main goal set out at the start, and getting the ERS from an early ECTE351 prototype all the way to a soldered, enclosed and functioning device that could be deployed around the office as a test site felt like a real result. It pulled together almost every part of the work I did, from the hardware and soldering through to the enclosure design, and it was rewarding to have something physical and complete to show at the end rather than just a collection of separate features. 

Along the way there were a number of milestones that built towards that outcome. Getting the fall detection system working, with calibrated thresholds and a ten second false alarm cancellation window, was an important one, as was completing the emergency response side of the system with the email, SMS, 















**9** | **PROFESSIONAL EXPERIENCE REPORT** 

audio and relay workflows all triggered from a single device. Building the full graphical user interface and database was another significant milestone, since it turned the system from a collection of scripts into something a customer could view and manage, with a dashboard, filterable logs, staff and device configuration, CSV exporting and even an evacuation drill mode. On the communications side, getting LoRaWAN integrated as a backup protocol and building a full comparison of the different BLE gateways were both solid achievements that improved the reliability of the system and gave the company useful information to draw on for future work. Reverse engineering the traffic counter and producing a schematic for hardware that had no documentation was also a milestone I was pleased with, since it was a piece of work that had value to the company beyond the ERS itself. 

I also reached measurable targets in a few areas of the work. On the power side I tested and selected a battery solution that met the requirement of running the device for a full day with a factor of safety above 1.5 and reworked the battery percentage reporting so it followed the real discharge curve and gave an accurate reading across the full range rather than cutting out early. On the positioning side I established a reliable two metre detection zone around a gateway using averaged RSSI readings and worked to improve location accuracy by adding a fourth gateway and applying fuzzy logic and filtering to the algorithm. Each of these gave me a concrete result I could point to and justify with the testing I had done. 

In terms of recognition, the feedback I received was positive throughout. My mentor described my work as a very comprehensive and accurate account of the placement and noted my documentation skills, and the staff at Micromax seemed genuinely impressed with the work that had been done when I demonstrated the system. I presented the ERS dashboard to the director, ran a full product demonstration to all staff, and contributed to the final presentation and client tutorial at the end of the placement, and the response to the finished system was encouraging. Having the work taken seriously by the people around me and seeing it reach a point where it could be tutored to a client, was one of the more satisfying parts of the whole experience. 

#### 4.3 Link to Degree 

This placement connected to my Electrical and Electronics Engineering degree in a lot of direct ways, and several subjects I had studied fed straight into the work I was doing. The most obvious link was to ECTE351, which is where the Emergency Response System began. The placement was essentially a continuation and expansion of that project, so the foundation I built during the subject carried right through and gave me a starting point to build on, as well as a clear sense of how 















**10** | **PROFESSIONAL EXPERIENCE REPORT** 

much further a project can go once it moves out of a university setting and into a company. 

Communication systems was one of the areas of my degree that applied most heavily. Almost the entire placement involved wireless communication in some form, whether that was LoRaWAN, Wi-Fi or BLE, and concepts like signal strength, range, redundancy and choosing the right protocol for a given situation were things I dealt with every day. Working with RSSI readings, gateways and the trade-offs between different protocols gave me a much more practical understanding of the material than I had from the theory alone, and having to design proper communication redundancy into the system forced me to apply those concepts in a way that a normal assignment never really would. 

Power electronics was another subject that tied in closely, particularly through the battery and power management side of the client device. Selecting an appropriate power solution, testing battery capacities, dealing with charging and shutdown voltages, and reworking the discharge curve so the battery percentage read accurately all drew on what I had learned about power. The electronics side of my degree also applied throughout, from testing and integrating sensors and modules to PCB design in KiCad and soldering the final prototypes, which was where the more fundamental electronics knowledge came into play and where I could see the direct value of the circuit and component theory I had covered at university. 

Intelligent control was the subject that connected to the more advanced positioning work. When I was trying to improve the accuracy of the indoor positioning, I applied fuzzy logic and Kalman filtering to the trilateration and centroid algorithms, which came directly out of the control concepts I had studied. The fall detection algorithm, with its calibrated thresholds and logic for distinguishing a real fall from ordinary movement, also drew on that same kind of thinking, and seeing these techniques used to solve a genuine problem made the theory behind them a lot clearer to me. 

More broadly, the placement reinforced and expanded on my academic learning by putting all of it into a real setting at the same time. At university these subjects are usually studied separately, but on the placement, I had to combine communications, power, electronics and control into one working product, which gave me a much better sense of how they fit together in practice. It also taught me technologies and skills that my degree hadn't covered, such as LoRaWAN and PCB design, and gave me an insight into the industry that I couldn't have gotten from coursework. In terms of my career path, I am still working out exactly which industry I want to move into, with power distribution being one area I am interested in, but regardless of where I end up this placement has given me practical experience, industry insight and professional connections that will help 















**11** | **PROFESSIONAL EXPERIENCE REPORT** 

me going forward and that build directly on what I have studied throughout my degree. 

#### 4.4 Feedback on the Organisation / Overall satisfaction 

Overall, my impression of Micromax Technology is that they work on a wide range of technology solutions around Australia, and I enjoyed my time interning. Shakif provided excellent mentoring throughout the experience, and all staff were friendly to work alongside. The team culture at Micromax is very inviting and time for celebrations are allocated with respect to all the necessary work being achieved. This internship has met my expectations as I learned skills in many new technologies and software’s that will help my future career endeavours, and I would recommend an internship at Micromax technology to anyone searching for an ECTE based internship. 

## **Conclusion** 

Overall, my ECTE399 placement at Micromax Technology was a valuable and rewarding experience that gave me the chance to apply my degree to a real engineering project from start to finish. Over the course of the placement, I took the Emergency Response System from an early prototype through to a working, enclosed device that could be deployed around the office, and in doing so I gained hands-on experience across wireless communications, sensor integration, power management, PCB and CAD design, software and database development, and system testing. Working on a single project over an extended period also let me see how a product develops over time, and how much of engineering is iteration, testing and refinement rather than getting something right the first time. 

The placement developed both my technical and professional skills. I became comfortable with a range of technologies I had never used before, including LoRaWAN, KiCad and PCB design, MQTT and SQLite, and I improved my documentation, project management and ability to work to client expectations and deliver a finished product. Just as importantly, I learned from the parts of the project that didn't go perfectly, such as the indoor positioning that had to be left unfinished and the boot issue that cost time before I found a workable solution, and these taught me as much about real engineering as the parts that went smoothly. 

More than anything, this placement has helped prepare me for future roles by bridging the gap between the theory I learned at university and the practical reality of professional engineering. It has not only helped me meet the requirements of my degree but has given me genuine insight into how the 















**12** | **PROFESSIONAL EXPERIENCE REPORT** 

industry works and valuable connections for the future. I would happily recommend an internship at Micromax to anyone looking for an ECTE-based placement, and I finish it feeling far more confident and better equipped as an engineer than when I started. 















**13** | **PROFESSIONAL EXPERIENCE REPORT** 

~~Oe~~ om: 









<!-- Start of picture text -->
om:<br><!-- End of picture text -->

UNIVERSITY OF WOLLONGONG AUSTRALIA 

Unpaid Work Experience Application v1 

01/07/2026, 13:45 

UNIVERSITY OF WOLLONGONG AUSTRALIA 

### Engineering and Information Sciences Unpaid Work Experience Application 

###### Student Details 





|ID Number|7679877|
|---|---|
||Bachelor of Engineering (Honours) (Single Major)|
||Electrical and Electronics Engineering|
|Year ofyour<br>degree|4th orgreateryear|
|emai|trs275@uowmail.edu.au|
|Session Intending |<br>to Graduate|spring|
|Year Intending to<br>Graduate|2026|
|Any Pre-Existing<br>Medical<br>Conditions or<br>Information<br>Relevant to the<br>Placement|N/A|





<!-- Start of picture text -->
Electrical and Electronics Engineering<br>Year of your 4th or greater year<br>degree<br>emai trs275@uowmail.edu.au<br>Session Intending | spring<br>to Graduate<br><!-- End of picture text -->



<!-- Start of picture text -->
Year Intending to 2026<br>Graduate<br>Any Pre-Existing N/A<br>Medical<br>Conditions or<br>Information<br>Relevant to the<br>Placement<br><!-- End of picture text -->

https://studentplacement.uow.edu.au/SoniaOnline/EFormEdit.aspx 

1/5 









om 

UNIVERSITY OF WOLLONGONG AUSTRALIA 

01/07/2026, 13:45 

Unpaid Work Experience Application v1 

##### Period of Employment 





|Start Date|19/01/2026|||
|---|---|---|---|
|End Date|29/06/2026|||
|Full time or part<br>timeemployment|Please specify in format (x days/<br>3days/wk *20wks =60d|wk * ywks = x*y days) eg. (<br>ays|3 days/wk * 20wks = 60 days)|
|Schedule of<br>employment|eg. 12weeks or6 + 6weeks<br>20Weeks|||
|Comments for<br>period of<br>employment<br>Organisation De|tails|||
||MicromaxTechnology||https://micromaxtechno<br>logy.com/|
|fsuoue<br>||unandera<br>||County<br>||tata|
|Organisation St<br>|<br><br>udent Mentor Detai<br>|<br><br>ls<br>|<br>|
|a|“|Ea|_|
||<br>||Research and<br>Development Team<br>Leader<br>|
|ageree]|emerieomeman|fommsone|—|





<!-- Start of picture text -->
logy.com/<br>fsuoue | unandera | County | tata<br>Organisation Student Mentor Details<br><!-- End of picture text -->



<!-- Start of picture text -->
a “ Ea _<br>Research and<br>Development Team<br>Leader<br>ager ee] emerieomeman fommsone —<br><!-- End of picture text -->

https://studentplacement uow.edu.au/SoniaOnline/EFormEdit.aspx 

2/5 











<!-- Start of picture text -->
UNIVERSITY<br>OF WOLLONGONG<br>AUSTRALIA<br><!-- End of picture text -->

<u>N</u> 

rs au UNIVERSITY OF WOLLONGONG AUSTRALIA 

| 

01/07/2026, 13:45 Unpaid Work Experience Application v1 Student's Research into Organisation The following criteria will be used to check if the organisation and placement you are submitting can satisfy the requirements 



<!-- Start of picture text -->
Organisation Profile<br><!-- End of picture text -->



<!-- Start of picture text -->
Work Experience Expected<br>The work experience needs to be related to an Engineering problem. It is expected that the student<br>will be involved in significant aspects of the project(s) assigned by the industry.<br>Simple site visit is NOT accepted. Work experience needs to ensure the student is trained to be a<br>future engineer, not a skilled worker.<br>Primary Project: Lead the development of the Emergency Response System from prototype to<br>commercially viable product Secondary Project: Design and implement a LoRaWAN-enabled<br>remote power management board Key Responsibilities - Develop harcware and software solutions<br><!-- End of picture text -->



<!-- Start of picture text -->
analysis, system design, and technical specifications - Create detailed technical documentation<br>throughout the development lifecycle - Participate in testing protocols including reliability testing,<br>false alarm analysis, and compliance validation - Design and prototype LoRaWAN communication<br>systems for remote device management- Collaborate with the wider team to gather requirements<br>from potential clients and industry partners - Present progress updates and technical solutions to<br>stakeholders<br><!-- End of picture text -->



https.//studentplacement uow.edu.au/SoniaOnlina/EFormEdit.aspx 

3/5 



<!-- Start of picture text -->
UNIVERSITY<br>OF WOLLONGONG<br>AUSTRALIA<br><!-- End of picture text -->

~~a~~ rs UNIVERSITY OF WOLLONGONG AUSTRALIA 



<!-- Start of picture text -->
01/07/2026, 13:45 Unpaid Work Experience Application v1<br>Student Declarations<br>Yes As the student, | declare | have had initial discussions with this<br>organisation.<br>| declare | have had previous discussions with the contact person at this<br>organisation regarding a professional experience placement, and this contact<br>person will be aware of this communication via an email link to complete the<br>form.<br><!-- End of picture text -->



<!-- Start of picture text -->
Yes As the student, I declare there is no conflict of interestfor this work<br>placement<br>For example, the student can NOT be supervised by his/her relatives. Note:<br>Self-employed company does not account for work experience.<br>Yes As the student, | declare this work placement is UNPAID<br>« lam not employed by the Placement Organisation and will not be<br>receiving payment in respect of the Placement.<br>¢ lagree that! will only perform activities that fall within the scope of the<br>Brief Description of Placement Activities described above. If | am asked to<br>do other activities | will first notify the University to obtain approval to do<br><!-- End of picture text -->

Add any general comments regarding this application 



<!-- Start of picture text -->
Actioned by Thomas Speer (7679877) on 17/12/2025 12:40:35 PM<br><!-- End of picture text -->

Actioned by Faisel Tubbal on 17/12/2025 1:59:36 PM 







<!-- Start of picture text -->
hitps://studentplacement uow.edu.au/SoniaOnlina/EFormEdit.aspx<br><!-- End of picture text -->







4/5 





<!-- Start of picture text -->
rs<br><!-- End of picture text -->

UNIVERSITY OF WOLLONGONG AUSTRALIA 

01/07/2026, 13:45 Unpaid Work Experience Application v1 CT UOW Insurance has been approved for the above student and placerrent. Yes 

Certificate of Insurance 

WOLL - Seneral and Products Liability 20m CoP 25-26.pdf, Certificate of Currency 2024-25. PA (Staff & Students) Insurance.pdf 









https://studentplacement.uow.edu.au/SoniaOnline/EFormEdit.aspx 







5/5 



rs 

UNIVERSITY OF WOLLONGONG AUSTRALIA 

01/07/2026, 13:45 

ECTE399 - Student Weekly Diary 



<!-- Start of picture text -->
ae<br><!-- End of picture text -->

UNIVERSITY OF WOLLONGONG AUSTRALIA 

Faculty of Engineering and Information Sciences 

##### Student Weekly Diary 

||Thomas Speer||Micromax Technology|
|---|---|---|---|
|Id Number|7679877|Organisation<br>Mentor|ShakifAziz|
|Degree Course|| Bachelor ofEngineering<br>(Honours) (Single Major)|Placement Start <br>Date|| 19/01/2026|
|Discipline|Electrical and Electronics<br>Engineering|PlacementEnd<br>Date|29/06/2026|





<!-- Start of picture text -->
(Honours) (Single Major) Date<br>Discipline Electrical and Electronics Placement End 29/06/2026<br>Engineering Date<br><!-- End of picture text -->



1/6 















<!-- Start of picture text -->
rs<br><!-- End of picture text -->

https://studentplacement.uow.edu.au/SoniaOnline/EFormEdit.aspx 

UNIVERSITY OF WOLLONGONG AUSTRALIA 





<!-- Start of picture text -->
01/07/2026, 13:45 ECTE399 - Student Weekly Diary<br>Weeks Date List of Activities Supporting<br>Documents or<br>Images<br>Week 1 | 19/01/ | - Induction paperwork/tour. - Set up prototype ECTE351 Photo 21-1-2026, 3<br>2026 to show team previous progress. - Meeting with head 01 07 pm.jpg, Photo<br>director about expectations for the ERS. -Started 20-1-2025, 41145<br>documentation and research for the emergency pm.jpg<br>response system. - Tested previous LoRaWAN prototype<br>and BLE-Wi-Fi gateway as options for the ERS<br>communication protocols. - Architecture Diagram<br>Drawings and digitalized them. -Tested Mokosmart panic<br>button. - Tested LoRa switch transceiver. - Further<br>research into components for ERS.<br>Week 2 | 27/01/ | - Finalized System Spec document. - Testing HLK- Photo 30-1-2026, 4<br>2026 LD2410C human presence detector and documentation 10 54 pm. jpg<br>for futur2 use. - Research suitable parts for the ERS. -<br><!-- End of picture text -->

|01/07/2026, 13:45<br>Weeks|Date|ECTE399 - StudentWeekly Diary<br>List of Activities|Supporting<br>Documents or<br>Images|
|---|---|---|---|
|Week 1|| 19/01/ |<br>2026|- Induction paperwork/tour. -Setup prototype ECTE351<br>toshowteam previous progress. - Meeting with head<br>director about expectations for the ERS. -Started<br>documentation and research for the emergency<br>response system. - Tested previous LoRaWAN prototype<br>and BLE-Wi-Fi gatewayas options for the ERS<br>communication protocols. -Architecture Diagram<br>Drawings and digitalized them. -Tested Mokosmart panic<br>button. -Tested LoRa switch transceiver. - Further<br>research into components for ERS.|Photo 21-1-2026, 3<br>01 07 pm.jpg, Photo<br>20-1-2025, 41145<br>pm.jpg|
|Week2 ||27/01/ |<br>2026|- Finalized System Specdocument. -TestingHLK-<br>LD2410C human presence detectoranddocumentation<br>for futur2 use. - Research suitable parts for the ERS. -<br>LoRaWAN power cycling device research. - KiCAD<br>tutorials/PCBdesign. - StartofERS production. -Make<br>Button detect Mass emergency(5 presses) or Personal<br>Emergency( 5 second press), and differentiate between<br>the 2. - Receive button press signal on a serverand<br>create alog oftype ofemergencyand time pressed.|Photo 30-1-2026, 4<br>1054 pm. jpg|
|Week 3 ||4/02/2 <br>026||<br>- Procurement Listfor ERS. - Fall detection calibration<br>research and trials. Graphing peaks and time to get a<br>visual representation ofwhat values need to be<br>thresholds for a real fall.<br>- Raspberry Pi Pico Ble tests for<br>communication redundancyand indoor positioning. -<br>Testing different falls with mattress todetermine the<br>maximum threshold needed for fall detection. -<br>Programmingthe fall detection algorithm. -Create a<br>false alert protection so ifthe fall is triggered and help is<br>not needed then the client can cancel the request for<br>help within the first 10 seconds. - Create email workflow<br>soemail is sentwhen an alert is triggered with info on<br>the type ofemergency. -Create SMSworkflow -Allow<br>triggered client device to trigger audio alert to be played<br>/ relay taopen -Testing Ble Gateways and Ble tags in<br>conjunction.|Photo 5-2-2026, 10<br>2150am.jpg, Photo<br>4-2-2026, 10 1108<br>am.jpg|





<!-- Start of picture text -->
LoRaWAN power cycling device research. - KiCAD<br>tutorials/ PCB design. - Start of ERS production. - Make<br>Button detect Mass emergency(5 presses) or Personal<br>Emergency( 5 second press), and differentiate between<br>the 2. - Receive button press signal on a server and<br>create alog of type of emergency and time pressed.<br>Week 3 | 4/02/2 | - Procurement List for ERS. - Fall detection calibration Photo 5-2-2026, 10<br>026 research and trials. Graphing peaks and time to get a 2150 am.jpg, Photo<br>visual representation of what values need to be 4-2-2026, 10 1108<br><!-- End of picture text -->



<!-- Start of picture text -->
thresholds for a real fall. - Raspberry Pi Pico Ble tests for am.jpg<br>communication redundancy and indoor positioning. -<br>Testing different falls with mattress to determine the<br>maximum threshold needed for fall detection. -<br>Programming the fall detection algorithm. - Create a<br>false alert protection so if the fall is triggered and help is<br>not needed then the client can cancel the request for<br>help within the first 10 seconds. - Create email workflow<br>so email is sent when an alert is triggered with info on<br>the type of emergency. -Create SMS workflow - Allow<br><!-- End of picture text -->

https://studentplacement uow.edu.au/SoniaOnlina/EFormEditaspx 

2/6 



<!-- Start of picture text -->
rs<br><!-- End of picture text -->









<!-- Start of picture text -->
1<br><!-- End of picture text -->

<u>\</u> 

1 

UNIVERSITY OF WOLLONGONG AUSTRALIA 



<!-- Start of picture text -->
0107/2026, 13:45 ECTE399 - Student Weekly Diary<br>Week 4 | 12/02/ | - Connect Ble Tag to Ble-WIFI gateway and take RSSI<br>2026 readings through multiple obstacles to get an average<br>RSSI value at 2m. - Create a script that will determine if<br>the Ble tag is within 2m of the gateway and start a timer<br>that will stop if the tag leaves this 2m area. -<br>Documentation of fall detection experiment and<br>justification of threshold values set. - Research of current<br>technolagies and how RTLS is implemented within other<br><!-- End of picture text -->

|0107/2026, 13:45<br>Week4|| 12/02/ <br>2026|ECTE399 - StudentWeekly Diary<br>| -Connect BleTagto Ble-WIFIgatewayand take RSSI<br>readings through multiple obstacles to getan average<br>RSSI value at 2m. - Create a script that will determine if<br>the Ble tag is within 2m ofthegateway and start a timer<br>that willstop ifthe tag leaves this2m area. -<br>Documentation of fall detection experiment and<br>justification of threshold values set. - Research ofcurrent<br>technolagiesand how RTLS is implemented within other<br>structures and how can that be assigned to our sclution.<br>- Making ERS logs more readable and filterable for office<br>audits or office use using SQLite. - Research and noteson<br>how previous studies were conducted to show how<br>indoor positioningwas achieved using Ble.<br>- Research on<br>Ble toWIFI gateways for indoor use as well as redesign<br>ofcomms redundancy as Ble will likely not work, most<br>likely use LoRaWAN - Development of ERS GUI<br>connected to database so customers can see all<br>emerger<br>cy data aswell as run evacuation drills from the<br>GUI that will trigger thesameworkflow as mass<br>emerger<br>cy but be classified astestwithin thedatabase.|
|---|---|---|
|Week 5|| 20/02/ <br>2026|| - Research intohowa BletoWIFI gatewaycould be<br>replaced by a Ble to LoRaWAN gateway and using<br>LoRaWAN as a backup communication protocol so that<br>location services can be used regardlessof ifthe WIFI is<br>down. - Development of multiple pages within the GUI<br>for the ERS, including Dashboard, Logs, Staffand<br>Configuration Page. Staff page allows for email and<br>phone numberto be assigned to staffand configuration<br>pageallows for specific devicestobe allocated toa staff<br>member The configuration page also letsyou decide<br>which staff will receivethe alerts ifan emergency occurs.<br>-Adding features to the GUI such as a stop button for<br>the massemergency trigger, so that relayand audio<br>alerts can be stopped once danger is cleared, a button to<br>export logs as a csv file, and minor tweaks tothe<br>aesthetics ofthe page. Spending time to tryand find<br>anythingwrong with the GUI and testing all features to<br>ensureworkingcorrectly.|





<!-- Start of picture text -->
structures and how can that be assigned to our sclution.<br>- Making ERS logs more readable and filterable for office<br>audits or office use using SQLite. - Research and notes on<br>how previous studies were conducted to show how<br>indoor positioning was achieved using Ble. - Research on<br>Ble to WIFI gateways for indoor use as well as redesign<br>of comms redundancy as Ble will likely not work, most<br>likely use LoRaWAN - Development of ERS GUI<br>connected to database so customers can see all<br>emergercy data as well as run evacuation drills from the<br><!-- End of picture text -->



<!-- Start of picture text -->
GUI that will trigger the same workflow as mass<br>emergercy but be classified as test within the database.<br>Week 5 | 20/02/ | - Research into how a Ble to WIFI gateway could be<br>2026 replaced by a Ble to LoRaWAN gateway and using<br>LoRaWAN as a backup communication protocol so that<br>location services can be used regardless of if the WIFI is<br>down. - Development of multiple pages within the GUI<br>for the ERS, including Dashboard, Logs, Staff and<br>Configuration Page. Staff page allows for email and<br><!-- End of picture text -->



<!-- Start of picture text -->
phone number to be assigned to staff and configuration<br>page allows for specific devices to be allocated to a staff<br>member The configuration page also lets you decide<br>which staff will receive the alerts if an emergency occurs.<br>- Adding features to the GUI such as a stop button for<br>the mass emergency trigger, so that relay and audio<br>alerts can be stopped once danger is cleared, a button to<br>export logs as a csv file, and minor tweaks to the<br>aesthetics of the page. Spending time to try and find<br>anything wrong with the GUI and testing all features to<br><!-- End of picture text -->

3/6 







<!-- Start of picture text -->
1<br><!-- End of picture text -->







<!-- Start of picture text -->
rs<br><!-- End of picture text -->

https://studentplacement uow.edu.au/SoniaOnline/EFormEdit.aspx 

<u>\</u> 

1 

UNIVERSITY OF WOLLONGONG AUSTRALIA 





<!-- Start of picture text -->
01/07/2026, 13:45 ECTE399 - Student Weekly Diary<br>Week 6 | 3/03/2 | - Started creating a cad model of the ERS client side<br>026 device to eventually create an enclosure to deploy the<br>ERS throughout the Micromax office as a test site. This is<br>not a final enclosure, therefore| left holes to allow for<br>further programming as it may be required. Basic<br>sketches to get idea of how it will look. Design not final<br>as parts are yet to arrive. - Reverse Engineering and<br>creating a schematic diagram for a traffic counter that<br>does not have any documentation. -Continuing on the<br>traffic counter schematic -Testing Components that were<br>delivered for the ERS -Adjustments to the ERS Client Side<br>Device Casing - Continued on ERS 3d model<br>Week7 | 12/03/ | -testing Seeed nrf52840 Ble modules sending packets to Photo 19-3-2026,<br>2026 the Minew g1 gateway and receiving on matt explorer. - 10 47 28 am.jpg<br>Testing range of Minew G1 -Demonstration to Director of<br>the ERS dashboard - Utilizing both pico and nrf52840<br>together, so the pico triggers the alarm and the nrf sends<br><!-- End of picture text -->

|01/07/2026, 13:45<br>Week6|| 3/03/2 <br>026|ECTE399 - StudentWeekly Diary<br>|<br>- Started creatingacad model ofthe ERS client side<br>device to eventually create an enclosure to deploy the<br>ERS throughout the Micromax office as a test site. This is<br>not a final enclosure, therefore| left holes toallow for<br>further programming as it may be required. Basic<br>sketches to get idea ofhow it will look. Design not final<br>as parts are yet to arrive. - Reverse Engineering and<br>creatinga schematic diagram for a traffic counterthat<br>does not have any documentation. -Continuing on the<br>traffic counter schematic -TestingComponents thatwere<br>delivered for the ERS -Adjustments to the ERS Client Side<br>Device Casing - Continued on ERS 3d model||
|---|---|---|---|
|Week7|| 12/03/ <br>2026|| -testing Seeed nrf52840 Blemodulessending packetsto<br>the Minew g1gateway and receiving on matt explorer. -<br>Testing range ofMinewG1 -Demonstration to Director of<br>the ERS dashboard - Utilizing both picoand nrf52840<br>together, so the pico triggers thealarm and the nrfsends<br>the Ble signal for the minewg1 to pickup; to be used in<br>the future for indoor footprinting using rssi values -<br>Finished first 3D model for printingand checking<br>dimensions before further modelling - Testing rssi values<br>for different distances around the office. - Testingnew<br>MPU6050modules to ensure all working correctly -<br>Tested UPS Hat for Pi S and Pi Pico2W|Photo 19-3-2026,<br>1047 28 am.jpg|
|Week8|| 31/03/ <br>2026|| -Comparing differences between Seeed LiPo Rider Plus<br>and Waveshare Pico UPS B and bench testing to see<br>which will be the bestoption for the ERS - Testing battery<br>capacities to see which will be most suitableand allow<br>forawholedayusage,withafactorofsafetyof>1.5.||





<!-- Start of picture text -->
the Ble signal for the minew g1 to pickup; to be used in<br>the future for indoor footprinting using rssi values -<br>Finished first 3D model for printing and checking<br>dimensions before further modelling - Testing rssi values<br>for different distances around the office. - Testing new<br>MPU6050 modules to ensure all working correctly -<br>Tested UPS Hat for Pi S and Pi Pico 2W<br>Week 8 | 31/03/ | - Comparing differences between Seeed LiPo Rider Plus<br>2026 and Waveshare Pico UPS B and bench testing to see<br><!-- End of picture text -->



<!-- Start of picture text -->
which will be the best option for the ERS - Testing battery<br>capacities to see which will be most suitable and allow<br>for a whole day usage, with a factor of safety of >1.5.<br><!-- End of picture text -->

https://studentplacement uow.edu.au/SoniaOnlina/EFormEditaspx 

4/6 









<!-- Start of picture text -->
1<br><!-- End of picture text -->



<!-- Start of picture text -->
UNIVERSITY<br>OF WOLLONGONG<br>AUSTRALIA<br><!-- End of picture text -->

<u>\</u> 

rs UNIVERSITY OF WOLLONGONG AUSTRALIA 

1 





<!-- Start of picture text -->
01/07/2026, 13:45 ECTE399 - Student Weekly Diary<br>Week 9 | 14/04/ | - Got Pico displaying LED if its battery drops below a Photo 16-4-2026, 3<br>2026 certain level, indicating charging is needed. - Worked on 38 56 pm.jpg<br>getting client side device battery percentage shown on<br>server - Ble RSSI mapping around the office. - Sit in on<br>visit from BluelOT to discuss partnership with Micromax<br>and discuss their current and future products - Client<br>Device battery shown on server webpage, and alerts<br>sent via SMS/email depending on configured admin<br><!-- End of picture text -->

|01/07/2026, 13:45<br>Week9|| 14/04/ |<br>2026|ECTE399 - StudentWeekly Diary<br><br>-Got Pico displaying LED if itsbatterydrops below a<br>certain level, indicating charging is needed. -Worked on<br>getting client side device battery percentageshown on<br>server - Ble RSSI mapping around the office. - Sit in on<br>visit from BluelOT to discuss partnership with Micromax<br>and discuss their current and future products - Client<br>Device batteryshown on serverwebpage, and alerts<br>sent via SMS/email depending on configured admin<br>alerts for low battery on client device. - Review ofMinew<br>G1 - Started Fixing shown battery percentage to match<br>discharge curve rather than linear so it is more accurate,<br>and make range from 0-100 as shutdown voltage s<br>currently mapped to around 30% charge remaining. -<br>Setup new Mokosmart MKGW3 PoE BLE -WIFI gateway<br>for use ofindoor positioning -Comparison table of all<br>different BLEgateways tested -Combine both server<br>scripts and pico scripts with Skylar's scripts to<br>incorporate the LoRaWAN communication capabilities<br>for the maincommsand using Wi-Fi as a backup if<br>LoRaWAN networkgoes down. Fixingany issuesthat<br>occur. - Testing of piezoelectric sensor used for traffic<br>counting for upcoming ECTE351 students to collect next<br>week. - Fix Raspberry Pi 5 Boot Issue, try to find a way to<br>log this issue soweknowwhat is happeningand how to<br>avoid.|Photo 16-4-2026, 3<br>38 56 pm.jpg|
|---|---|---|---|
|Week<br>10|28/04/ |<br>2026|-Testing Blegateways andattempting to getble to<br>LoRaWAN gateways working. -Working on trilateration<br>for ble rssi indoor positioning.||
|Week<br>11|14/05/ <br>2026|| -Workedon trilateration algorithm and added fourth<br>gateway totryandgetmoreaccurate readingsofindoor<br><br>location - Implementing fuzzy logic to the trilateration<br>and centroid algorithm to see if better results are<br>wielded. Fixing webpage which had stopped running<br>correctly after a change. - Product demonstration to all<br>staff|Phcto9-4-2026, 1<br>, £126pm.jpg|
|Week<br>12|2/06/2<br>026|- Designingand solderingtwovero board prototypes,<br>one for display so all components can be seen and<br>explained, another as small as possible for functicnality<br>and further testing. - Redesigning Enclosure for newly<br>soldered functional prototype and 3d printing and<br>redesigning to account for any mistakes. - Finalizing<br>enclosure-FinalPresentation-ClienttutorialbyShakif|Photo 10-6-2026, 3<br>25 32 pm.jpg, Photo<br>10-6-2025, 14047<br>pm.jpg|





<!-- Start of picture text -->
alerts for low battery on client device. - Review of Minew<br>G1 - Started Fixing shown battery percentage to match<br>discharge curve rather than linear so it is more accurate,<br>and make range from 0-100 as shutdown voltage s<br>currently mapped to around 30% charge remaining. -<br>Setup new Mokosmart MKGW3 PoE BLE - WIFI gateway<br>for use of indoor positioning - Comparison table of all<br>different BLE gateways tested - Combine both server<br>scripts and pico scripts with Skylar's scripts to<br>incorporate the LoRaWAN communication capabilities<br><!-- End of picture text -->



<!-- Start of picture text -->
for the main comms and using Wi-Fi as a backup if<br>LoRaWAN network goes down. Fixing any issues that<br>occur. - Testing of piezoelectric sensor used for traffic<br>counting for upcoming ECTE351 students to collect next<br>week. - Fix Raspberry Pi 5 Boot Issue, try to find a way to<br>log this issue so we know what is happening and how to<br>avoid.<br>Week 28/04/ | - Testing Ble gateways and attempting to get ble to<br>10 2026 LoRaWAN gateways working. - Working on trilateration<br>for ble rssi indoor positioning.<br>Week 14/05/ | - Worked on trilateration algorithm and added fourth Phcto 9-4-2026, 1<br>11 2026 gateway to try and get more accurate readings ofindoor , £126pm.jpg<br>location - Implementing fuzzy logic to the trilateration<br>and centroid algorithm to see if better results are<br>wielded. Fixing webpage which had stopped running<br>correctly after a change. - Product demonstration to all<br>staff<br><!-- End of picture text -->

https://studentplacement.uow.edu.au/SoniaOnline/EFormEdit.aspx 

5/6 



<!-- Start of picture text -->
rs<br><!-- End of picture text -->









<!-- Start of picture text -->
1<br><!-- End of picture text -->

<u>\</u> 

1 

UNIVERSITY OF WOLLONGONG AUSTRALIA 

01/07/2026, 13:45 

ECTE399 - Student Weekly Diary 

Actioned by Thomas Speer (7679877) on 29/06/2026 3:21:42 PM 

Actioned by Thomas Speer (7579877) on 29/06/2026 3:22:16 PM 

##### Organisation Mentors Comments. 

This is a very comprehensive and accurate account of events during the placement. Good contemporaneous documentation skills. 

Actioned by Shakif Aziz on 30/06/2026 9:45:19 AM 







https://studentplacement uow.edu.au/SoniaOnline/EFormEdit.aspx 







6/6 



rs 

UNIVERSITY OF WOLLONGONG AUSTRALIA 



<!-- Start of picture text -->
* is & ~ 4<br><!-- End of picture text -->



<!-- Start of picture text -->
Atle :<br>« i |<br><!-- End of picture text -->





Picture 1: Testing Fall Detection 



<!-- Start of picture text -->
i | = | i<br>—— } = ; a<br>SSSR =|) =) ww<br>SS | if jl<br>—% al — q 4 f & di > 4 Se<br><!-- End of picture text -->

Picture 2: Demonstrating Prototype 















<!-- Start of picture text -->
UNIVERSITY<br>OF WOLLONGONG<br>AUSTRALIA<br><!-- End of picture text -->

ES UNIVERSITY OF WOLLONGONG AUSTRALIA 



_Picture 3: Soldering Final Prototype_ 















**27** | **PROFESSIONAL EXPERIENCE REPORT** 

This table is intended for Discipline Coordinator use only. Students must leave this form blank and attach it to the 









|~~pf~~ atesfouration<br>~~fT~~<br>~~Organisation Name Po Organisation Address Po Organisation URL~~<br>~~P|~~<br>~~eo~~ atesubmitted<br>Overview of the placement - includes a summary of the student role/position title and the organisation:<br>f<br>Company Description<br>Organisation/Employer Major Activities are adequately and accurately detailed:<br>f<br>Work Description<br>A detailed description of each of the activities/projects undertaken is provided:<br>~~P|~~<br>~~The student has included feedback on the placement organisation/employer:~~<br>~~Po~~<br>~~The work placement satisfies the requirements for ECTE399:~~<br>~~P|~~|
|---|







<!-- Start of picture text -->
Experience Application Form”: ee<br>The report includes an applicable “Approved Organisation Mentor's<br>Report - Certificate of Service Service Form”:<br>The presentation of the the report: Satisfactory Unsatisfactory<br><!-- End of picture text -->

~~<u>Experience Application Form”: ee</u>~~ The report includes an applicable “Approved Organisation Mentor's <u>Report - Certificate of Service Service Form”: The presentation of the the report: Satisfactory Unsatisfactory</u> ~~<mark>satisactory</mark>~~ Unsatisfactory 



<!-- Start of picture text -->
Unsatisfactory<br><!-- End of picture text -->





~~<mark>Po</mark>~~ <u>Satisfactory Unsatisfactory (Resubmit) Unsatisfactory (Repeat)</u> Additional Comments: 



<!-- Start of picture text -->
Additional Comments:<br><!-- End of picture text -->















<!-- Start of picture text -->
UNIVERSITY<br>OF WOLLONGONG<br>AUSTRALIA<br><!-- End of picture text -->

<u>N</u> 

re am UNIVERSITY OF WOLLONGONG AUSTRALIA 

<u>zl</u> 

