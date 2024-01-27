# Ventilated Phone Storage in the center console

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/397d9187-5226-4cea-a617-c289e4a0f691.jpg" alt="(GTX Diamond-style accent light)" width="300px">
</div>

<div align="center">
  <img src="https://github.com/JohnyForElectric/ID.4/assets/107234448/397d9187-5226-4cea-a617-c289e4a0f691.jpg" alt="(GTX Diamond-style accent light)" width="300px">
</div>
![Phone storage](https://github.com/JohnyForElectric/ID.4/assets/107234448/397d9187-5226-4cea-a617-c289e4a0f691)

## Situation
The GTX version of ID.4 and ID.5 has two diamond-style accent lights in the front bumper. Let's get two misconceptions out of the way - (a) the accent lights are not configured from the factory as a Day Time running light /DLR/ (even despite it's called DLR in the official wiring diagram) and (2) it's not a front fog light. It's an accent light that turns on with the front headlights.

### More details
The non-GTX versions have the same shape of opening in the front bumber that is used to (1) intake air for optimizing aerodynamics, (2) houses one of the front parking sensors. The GTX version adds a third function - a cool diamond-style accent lights. So for GTX this part of the bumper has 3 functions: (1) air intake, (2) place for parking sensor and (3) accent light.

## Retrofits and mods
There are two usual steps to retrofits and mods (1) physical parts and (2) coding. Let's get to each one-by-one.

### Parts for retrofit

There are 3 key parts for each side - light module, bumper trim and internal bumper reinformecemt. Installation requires to remove the front bumper.

What | Part Number | Notes
---|---|---
1 x Left Light Module | 11A 941 055 A |  One light module for all 3 lenses, known as L377
1 x Right Light Module | 11A 941 056 A | One light module for all 3 lenses, known as L378
1 x Left Bumper Trim | 11A 807 763 A | "Glossy" cover for light module
1 x Right Bumper Trim | 11A 807 764 A | "Glossy" cover for light module
1 x Left Bumper Reinforcement | 11A 807 884 B | Specific to slot the lighht module
1 x Right Bumper Reinforcement | 11A 807 883 B | Specific to slot the lighht module
2 x Connector | 4F0 973 702 F | "Wet" connection to bumper harness

### Harness and pin to pin connections
Despite of all expectations, both light modules are connected to the front headlights MX1 (connector T14k /8) and MX2 (connector T14l /8) and not the CECM/J519. It's a simple two wire connection, one wire runs to each headlight and the other one is connected to the ground. The harness is routed via the bumper connector interconnect (TSFVL).

### Coding
To adapt these light modules, the head lights D6:Light Control Left (A31) and D7:Light Control right (A27) adaptations/coding need to be adjusted. The "coding/adaptation" via VCDS and OBD11, is not yet known. The only "hint" in the adaptation channel "NG178996-VehicleEquipmentCode And ProductionNumberCombination", but it has all zeroes across 12 x 8 bit numbers so the "current" state can't be determined.

The only clue we were able to find is the list of LED channels, their functions and dimming levels based on the funtion:

Channel 1-12 (rows) <BR> Mode/function (columns) <BR> PWM value (%) | Assumend Function | Brigtness Class | Hi-Beam | Parking | Low-Beam | Poor Wether + Low-Beam | Trun Light | Turn + Parking | DLR
---|---|---|---|---|---|---|---|---|---
1 | Poor Weather / Corner Light |	LK1 ||||75.6
2 | Hi-Beam	| LK2 |72.5
3 | DLR & Position | LK2 ||100|5.6|5.6|||100
4 | Low-Beam | LK2	|||100|100
5 | Hi-Beam |	LK2 |100
6 | DLR & Position | LK2||62.8|62.8|62.8|||62.8
7 | Light bar (side marker) | K1||100|100|100||100
8 | Turn light | LK1 |||||100|100
9
10
11
12


## Conclusion
  
The actual retrofit requires many OEM parts and removing the front bumper. There could be simpler options for adding non-OEM style LED DLR mini lights to each side to mimic the 3 diamond lights. We did not embark on this route as the longevity of non-OEM components is not superb (even for high-quality aftermarket brands, such as [VLEDs]([url](https://www.vleds.com/)) or [Morimoto]([url](https://www.morimotohid.com/))). 
  
Due to complexity of this retrofit (front bumper removal) - one consideration is to make additional retrofits at the same time in the front bumper (e.g. Front Camera, additional Park Pilot sensors, etc.) and connect the GTX-style accent lights to either an existing accent light or to a light channel on CECM/J519 for ultimate customizability. 
