# Center Console Ventilation for your Phone (German made cars)
<div align="center">
  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/397d9187-5226-4cea-a617-c289e4a0f691.jpg" alt="(Center console)" width="300px">
</div>


## Situation
Over the years we got multiple warnings on our phones about paused charging due to its high temperature. This is a feature of the phone to prevent battery demage and we believe it occured on both wireless and cable charging. We also believe that the rootcause was a bug in certain versions of iOS. Despite these bugs could be solved in one version but appreaded again on anther,  we set of on a quest to solve this once for all - to add a small fan into the center console to provide active cooling to both the phone and the wireless charging plate.

### More details
We have not explored over-heating in  US made cars as those have a different center console and this problem might not be apprering. This tweak is specifically for German based cars (cars with two separate arm rests for the driver and passenger). We have made  multiple changes to the center console (1) introduced openings to allow air flow, (2) added 120mm computer fan with controller, (3) added additional heat sink to the built-in phone wireless charging plate (R125). The fan is directing forced airflow to the phon itself, but also to the charger baseplate (R125) as apparent from the diagram below.

Overall Airflow | Phone Airflow 
---|---
<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/63b7d3d6-1ddf-422e-a84d-72fd47e59485" alt="(Center console)" width="540px"> | <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/2fc0f688-ad15-472f-ada3-875d7bfb9d9f" alt="(Center console)" width="380px">

## How we did it
Since this is not an OEM mod, there is no coding necessary. Unlike other mods in this repo, this one makes permanent modifications to the center console to allow airflow. These modifications are not visible from the outsode.

### Parts for retrofit
There are 2 key parts for this retrofit - the fan with fan controller and additional heatsink. The additional heatsink is not required, but will improve the overall temperature comfort of your phone and components inside of the OEM wireless phone charging plate (R125). This design uses fixed RPMs of the fan and the controller was used to fine-tune the right RPMs. We believe that any mod must be at least OEM quality, as such we selected high quality Noctua computer fan and a Noctua controller (that allows us to set the desired aiflow that cools, but can't be heard). 

What | Part Number | URL | Notes
---|---|---|---
1 x Noctua 120mm slim PWM fan | NF-A12x15 | https://noctua.at/en/nf-a12x15-pwm | Main component
1 x Noctua fan grill | NA-FG1-121 Sx2 | https://noctua.at/en/na-fg1-12 | Grill to protect the fan blades from intake side
1 x Noctua PWM fan controller | NA-FC1 | https://noctua.at/en/na-fc1 | Module for setting constant fan speed
1 x (Optional) Heatsink | Aluminium heatsink | https://www.amazon.com/gp/product/B07D9ZTTN2/ | Additional cooling for the OEM wireless charge plate. Only one is nedded. 
1 x (Optional) Thermally conductive adhesive | 8329TFF | https://www.amazon.com/gp/product/B07D18R5Z5/ | Adhesive to attach the additional heat sink (screws or rivets can use used as well)

### Connections
The system uses Noctua fan controller to drive and adjust the speed of the fan and a primite power supply. The power supply uses 4 rectifiers to drop the voltage by ~2.8V to not to exceed the opertating voltage of the controller and fan. Two capacitors buffer and filter the power line. The fan controller is set to low speed and the total power consumption is 30mA.
The ground (GND) is connected to the Phone Charging Plate harness (R125) (brown wire) and KL15 is the wire providing +12V ONLY if the ignition is ON. That is available at the back of the center console. The power for the rear USB charging (U37) is KL15. PLEASE NOTE the power to the phone charging pad (R126) and the front USB sockets is KL30, which means it's available all the time and never turns off.

Simplified electrical diagram 

<img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/572c6600-36ef-45f2-953c-bca4a1a5155b" alt="(Center console)" width="300px">


### Placement of parts
The 120 mm slim fan is perfectly fitting between metal clips of the front cover and the clips of the interior light of of the center console. The downside of the 120mm fan is that the interior light uses a light pipe that needs to be re-designed and the replacement 3D printed from transparent filament. Optionally a smaller 92mm fan can be used to keep the light pipe as is.

Step | Photo | Notes 
---|---|---
1 - Remove the cupholder | | 
2 - Drill holes | |
3 - Install fan | |
4 - Connect wire harness | |


## Conclusion
... 
