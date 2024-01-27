# Center Console Phone Ventilation (German made cars)
<div align="center">
  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/397d9187-5226-4cea-a617-c289e4a0f691.jpg" alt="(Center console)" width="300px">
</div>


## Situation
Over the years we got multiple warnings on the phone about paused charging tdue to high temperatures. This is a feature of the phone to prevent battery demage and it occured on both wireless and cable charging. We believe that the rootcause was a bug in certain versions of iOS. Despite that we set of on a quest to solve this once for all - to add a small fan into the center console.

### More details
We have not explored over-heating in the US made cars that have a different center console. This tweak is specifically for German based cars (cars with two separate arm rests for the driver and passenger). We have made multiple multiple changes to the center console (1) introduced openings to allow air flow, (2) added 120mm computer fan with controller, (3) added additional heat sink to the built-in phone wireless charger plate (R125). The fan is directing forced airflow to the phon eitself, but also to the charger baseplate (R125).

## Retrofits and mods
Since this is not an OEM mod, there is no coding necessary for this mod. Unlike other modes, this one requires making permanent modifications to the center console to allow airflow. These modifications are not visible from the outsode.

### Parts for retrofit
There are 2 key parts this retrofit - the fan with regulator and additional heatsink. The additional heatsink is not required, but will improve the overall temperature comform for your phone and components inside of the OEM wireless phone charge plate (R125). We believe that any mod must be at least in the OEM quality, as such we selected high quality Noctua fan and controller.

What | Part Number | URL | Notes
---|---|---
1 x Noctua 120mm slim PWM fan | NF-A12x15 | [https://coolnoctua.at/en/na-fc1](https://noctua.at/en/nf-a12x15-pwm) |Main component
1 x Noctua fan grill | NA-FG1-121 Sx2 | https://noctua.at/en/na-fc1 | Grill to protect the fan blades from one side
1 x Noctua PWM fan controller | NA-FC1 | https://noctua.at/en/na-fc1 | Module for setting constant fan speed
1 x Right Bumper Trim | 11A 807 764 A | "Glossy" cover for light module
1 x Left Bumper Reinforcement | 11A 807 884 B | Specific to slot the lighht module
1 x Right Bumper Reinforcement | 11A 807 883 B | Specific to slot the lighht module
2 x Connector | 4F0 973 702 F | "Wet" connection to bumper harness

### Harness and pin to pin connections
Despite of all expectations, both light modules are connected to the front headlights MX1 (connector T14k /8) and MX2 (connector T14l /8) and not the CECM/J519. It's a simple two wire connection, one wire runs to each headlight and the other one is connected to the ground. The harness is routed via the bumper connector interconnect (TSFVL).


## Conclusion
  
The actual retrofit requires many OEM parts and removing the front bumper. There could be simpler options for adding non-OEM style LED DLR mini lights to each side to mimic the 3 diamond lights. We did not embark on this route as the longevity of non-OEM components is not superb (even for high-quality aftermarket brands, such as [VLEDs]([url](https://www.vleds.com/)) or [Morimoto]([url](https://www.morimotohid.com/))). 
  
Due to complexity of this retrofit (front bumper removal) - one consideration is to make additional retrofits at the same time in the front bumper (e.g. Front Camera, additional Park Pilot sensors, etc.) and connect the GTX-style accent lights to either an existing accent light or to a light channel on CECM/J519 for ultimate customizability. 
