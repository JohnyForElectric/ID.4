# Driver Window Controls Haptic Feedback 
## Situation:
There are only two driver side window controls that by default control front driver and passenger windows. 
- To control the rear windows the "REAR" soft button needs to be touched for more than 1 second, then the button lights up and the rear windows can be controlled by the same controls that previously controlled the front windows. The button stays lit for 10 seconds, then turns off, reverting the controls to the front windows. 
- If the "REAR" soft button is touched and hold for 2+ seconds, it starts to blink and all four windows can be controlled at the same time. 

## Issues:
1. There is no sensual "dot or mark" where the button is, so it can't be located without looking
2. There is no haptic feedback in case the button is touched or pressed and held to change modes
     - There is a small "chime" in the speakers once the mode is changed, but it's not too obvious and can be missed. 
     - Further more the button is touched over the same area that lights up to indicate the mode, and it’s not possible to easily visually see the mode it entered, unless the finger is lifted.

## Solution:
Solution to problem #1 is to add two self-adhesive pads to indicate the touch sensitive area area.

For the heptic feedback, there is there multiple solutions, as outlined below

Option | Details | Pros/Cons | OEM
---|---|---|---
#1 - Clone REAR button LED signal with a vibration motor | Once the REAR soft button lights up a vibration motor in the unit will vibrate | Simple circuit, but requires tapping into the unit and the motor will vibrate all the time | No
#2 - Digitally process the REAR button LED signal and digitally manage the haptic experience | A micro-controller will recieve the the REAR button LED signal and control the vibration motor to create better haptic expereince | As above requires tapping into the unit, can't "decode" the mode easilly from the REAR button LED | No
#3 - Connect to the contol unit LIN bus, process it's signals and digitally control haptic experience | The unit has 3 wires - Vcc, Gnd and LIN. the LIN bus sends the "chime" signal to the speakers and can be used for a good haptic expereince | Just plug and play, but requires to listen and decode the LIN bus, the LIN bus data may not distinguish between the REAR and ALL window modes | No
#4 - VW aka Volskwagen to come up with updated unit that would provide better experience | Go crazy VW, but please make it backwards compatible :smiley: | Just plug and play from the OEM | Yes


