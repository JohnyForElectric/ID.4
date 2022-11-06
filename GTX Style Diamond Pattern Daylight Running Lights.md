# GTX Style Diamond Pattern Accent Lights 

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/200187298-9b744836-5a2b-4177-963a-2d4dbc088c29.jpg" alt="(GTX Diamond-style accent light)" width="300px">
</div>

## Situation
The GTX version of ID.4 and ID.5 has two diamond-style accent lights in the front bumper. Let's get two misconceptions out of the way - (a) the accent light is not configured from the factory as a Day Time running light /DLR/ (even despite it's called DLR in the official wiring diagram) and (2) it's not a front fog light. It's an accent light that turns on with the front headlights.

## More details
The non-GTX versions have a same shape opening in the bumber thgat is used to (1) intake air for optimizing aerodynamics, (2) has one of the front parking sensors. The GTX version adds a third function - adds accent lights. So it's (1) air intake, (2) place for parking sensor and (3) accent light.

## Retrofits and mods
There are two usual steps to retrofits and mods (1) physicl parts and (2) coding. Let's get to each one-by-one

### Retrofit

List of parts 
What | Part Number | Notes
---|---|---
1 x Left Light Module | 11A 941 055 A |  One light module for all 3 lenses, known as L377
1 x Right Light Module | 11A 941 056 A | One light module for all 3 lenses, known as L378
1 x Left Bumper Trim | 11A 807 763 A | "Shiny" gloss cover for light module
1 x Right Bumper Trim | 11A 807 764 A | "Shiny" gloss cover for light module
1 x Left Bumper Reinforcement | 11A 807 884 B | Specific to slot the lighht module
1 x Right Bumper Reinforcement | 11A 807 883 B | Specific to slot the lighht module
2 x Connector | 4F0 973 702 F | "Wet" connection to bumper harness

### Harness and pin to pin connections
Despite of all expectations, the light module are connected to the front headlights MX1 (connector T14k /8) and MX2 (connector T14l /8) and not the CECM/J519. It's a simple two wire connection, one wire runs to each headlight and the other one is connected to the ground. The harness is routed via the bumper connector interconnect (TSFVL).

### Coding
