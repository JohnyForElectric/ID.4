# Center Console Ventilation for your phone (German made cars)
<div align="center">
  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/397d9187-5226-4cea-a617-c289e4a0f691.jpg" alt="(Center console)" width="300px">
</div>


## Situation
Over the years we got multiple warnings on our phones about paused charging due to its high temperature. This is a feature of the phone to prevent battery demage and we believe it occured on both wireless and cable charging. We also believe that the rootcause was a bug in certain versions of iOS. These bugs were resolved in one version but appreaded again on another, so we set of on a quest to solve this once for all - by introducing airflow to cool the space. How? By adding a small fan into the center console to provide active cooling to both the phone and the OEM wireless charging plate (R126). 

3 outcomes that drove this design:
1) Cool the phone and the charging plate (R126)
2) No parts visible from the inside of the vehicle (including wiring)
3) Fan must be silent

### Quick summary
We have not explored center console ventilation in US made cars as those have a different center console. This tweak is specifically for German-made 2021 and 2022 cars (cars with two separate arm rests for the driver and passenger). We have made multiple updates to the center console (1) introduced openings to allow air flow, (2) added 120mm computer fan with controller, (3) added additional heat sink to the built-in phone wireless charging plate (R126). The fan is directing airflow to the phone itself, but also to the charger baseplate (R126) as apparent from the diagram below.

Overall Airflow | Phone Airflow 
---|---
<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/63b7d3d6-1ddf-422e-a84d-72fd47e59485" alt="(Center console)" width="540px"> | <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/2fc0f688-ad15-472f-ada3-875d7bfb9d9f" alt="(Center console)" width="380px">

## How we did it
Since this is not an OEM mod, there is no coding necessary. Unlike other mods in this repo, this one makes permanent modifications to the center console to allow airflow. These modifications are not visible from the outsode.

### Parts for retrofit
There are 2 key parts for this retrofit - the fan with fan controller and additional heatsink for the OEM wireless phone charging plate (R126). The additional heatsink is optional, but we expect it to improve temperature comfort of the components inside the OEM wireless phone charging plate (R126) that sits below the phone and thus should help to reduce the phone heating problem. 

This design uses fixed RPMs for the fan (not temperature depandant), the task of the fan controller is to manually fine-tune the right airflow and minimize any noise. We believe that any mod must be at least OEM quality, as such we've selected high quality Noctua computer fan and a Noctua fan controller (that allows us to set the desired aiflow that cools, but can't be heard). 

What | Part Number | URL | Notes
---|---|---|---
1 x Noctua 120mm slim PWM fan | NF-A12x15 | https://noctua.at/en/nf-a12x15-pwm | Main component
1 x Noctua fan grill | NA-FG1-121 Sx2 | https://noctua.at/en/na-fg1-12 | Grill to protect the fan blades from intake side
1 x Noctua PWM fan controller | NA-FC1 | https://noctua.at/en/na-fc1 | Module for setting constant fan speed
1 x (Optional) Heatsink | Aluminium heatsink | https://www.amazon.com/gp/product/B07D9ZTTN2/ | Additional cooling for the OEM wireless charge plate. Only one is nedded. 
1 x (Optional) Thermally conductive adhesive | 8329TFF | https://www.amazon.com/gp/product/B07D18R5Z5/ | Adhesive to attach the additional heat sink (screws or rivets can use used instead of the adhesive).

### Connections
The system uses Noctua fan controller to drive and adjust the speed of the fan and a primite power supply. The power supply has automotive 2A fuse, uses 4 rectifiers for isolation and to drop the voltage by ~2.8V, so the opertating voltage of the controller and fan is not exceeded. Two capacitors buffer and filter the power line. The fan controller is set to low speed and the total power consumption for our fan speed setting is 30mA (less than 0.4W).
The ground (GND) is connected to the Phone Charging Plate harness (R126) (brown wire) and +12V power to the KL15 (providing +12V ONLY if the ignition is ON). KL15 is available at the back of the center console, the power for the rear USB charging module (U37) is KL15 (red/blue wire). PLEASE NOTE the power to the phone charging pad (R126) and the front USB sockets is KL30, which means it's directly connected to the 12V battery (via fuses of course) without any interruption. So if the fan would be directly connected to that rail, it would not stop.

Simplified electrical diagram 

<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/5fcb059f-1969-41e3-909b-a11ee1c7238b" alt="(Wiring diagram)" width="450px">

### Placement of parts
The 120mm slim fan is perfectly fitting between metal clips of the front cover and the clips of the interior light for the center console. The downside of the 120mm fan is that the interior light uses a light pipe that needs to be re-designed. The replacement can be easilly 3D printed from transparent filament (attached STL file for details). Optionally, a smaller 92mm fan can be used to keep the light pipe as is.

Step | Photo | Notes 
---|---|---
1 - Removed the cupholder | <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/29c3adff-4811-44e3-adde-04b5f19c7aab" alt="(Cupholder removal)" width="350px"> | The bigger the pry tool the better, taped the surface to protect form sctraches.
2 - Drilled holes |  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/50530615-91d8-4c5b-aeb6-d5548c425792" alt="(Cupholder removal)" width="350px"> | Drilled sixteen 10mm holes around the light pipe assembly on top and 5 in the front (see next photo). The number and location depands on the fan selection.
3 - Trimed the storage compartment mat |  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/d0138948-9442-473a-8f20-d02e685c9280" alt="(Trim storage compartment mat)" width="350px"> | Trimmed the top mat by 18mm to allow more airflow. Once the cupholder on the top is installed the only light is the ambient light.
4 - Made and tested power supply |  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/74f17f4b-fb8e-4e78-bfba-a05e3b0704c2" alt="(Cupholder removal)" width="350px"> | Made the power supply and integrated the fan controller and fuse into small plastic box. Added a connector for easy future upgrades.
5 - Prepared the fan and tested setup |  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/5f08e700-6f59-43f5-8fd2-ac234ded6f13" alt="(Cupholder removal)" width="350px"> | Attached the fan grill on the intake side (bottom on the picture) with the long anti-vibration mounts included with the fan. Those are AWESOME! 
6 - Installed fan |  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/b534b5b4-2f94-4e0a-8d15-6a9fb03f4cb2" alt="(Fan)" width="350px"> | The 120mm slim fan is perfectly fitting between the metal clips of the front cover and the clips of the ambient light for the center console. Drilled additional 4mm holes to pull the fan mounts through to make sure the fan is even more secure. Moved the Ambient Light LED Module (L193) to the top and made new light diffusor. 
7 - (Optional) Additional heatsink for charging plate (R126) |<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/b7166d33-1606-4669-9566-f36218d131c0" alt="(J126 additional heatsink)" width="350px">| Made sure no sharp edges exist on the new heatsink...

Done!


## Conclusion
Interesting project - a good deep dive into few ventilation areas. Hopefully a good primer to go into ventilated seats.

## To geek around a bit more - if you are interested...
The fan controller is using PIC microcontroller https://www.microchip.com/en-us/product/PIC12F1571. Interesting automotive components https://www.microchip.com/en-us/solutions/automotive-and-transportation/body-electronics/heated-cooled-seats. Lot of cool stuff :) Another interesting descovery is this LIN controller https://www.melexis.com/en/product/MLX81108/Single-Channel-LIN-RGB-Slave-Ambient-Light-Controller that is used in ID.4's ambient lights :)

In case you are wondering how the OEM VW charging pad R126 looks inside - here is a sneak peak
1) Heatsink on the bottom removed
<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/26c653bf-75b8-4815-a027-3807397c2b05" alt="(J126 additional heatsink)" width="300px">

2) Charging coils in detail
<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/568ae173-fd9a-42d5-b933-c66a7f2be5c9" alt="(J126 additional heatsink)" width="300px">
