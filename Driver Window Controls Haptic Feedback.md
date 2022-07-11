# Driver Window Controls Haptic Feedback 
## Situation
There are only two driver side window controls that by default control front driver and passenger windows (part number known as 10A 959 862 S). 
- To control the rear windows the "REAR" soft button needs to be touched for more than 1 second, then the button lights up and the rear windows can be controlled by the same controls that previously controlled the front windows. The button stays lit for approx. 10 seconds, then turns off, reverting the controls to the front windows. 
- If the "REAR" soft button is touched and held for 2+ seconds, it starts to blink and all four windows can be controlled at the same time :heart:. 

## Challenges
1. It can't be located without looking, there is no sensual "dot or mark" where the button is, 
2. There is no haptic feedback in case the button is activated indicating the mode selected FRONT/REAR/ALL modes (e.g. FRONT = one, REAR = two, ALL = three)
     - There is a small "chime" in the speakers once the mode is changed, but it's not too obvious and can be easily missed (in addition it relies on a different sense in the body than the one creating the action) 
     - Furthermore the button is touched over the same area that lights up to indicate the mode, and it’s not possible to easily visually see the mode it entered, unless the finger is lifted.

## Solution to challenge #1 - "locating the button"
...is to e.g. add two self-adhesive pads to help easilly locate the touch sensitive area without looking at the location.\
One of the approaches below:\
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178167294-d7f9396d-2661-4cf0-a86d-ff0ece25f306.JPEG "
       alt="Helping to locate the touch sensitive area by two self adhesive pads"
       width="300px"
  />
</div>
:man_dancing: :woman_dancing:

## Solution to challenge #2 - "heptic feedback" 

For the haptic feedback, there is multiple options, as outlined below

Option | Details | Pros/Cons | OEM
---|---|---|---
#1 - Clone REAR button LED signal with a vibration motor | Once the REAR soft button lights up a vibration motor in the unit will vibrate | Simple circuit, but requires tapping into the unit and the motor will vibrate all the time | No
#2 - Digitally process the REAR button LED signal and digitally manage the haptic experience | A micro-controller will receive the REAR button LED signal and control the vibration motor to create better haptic experience | As above requires tapping into the unit, can't "decode" the mode easily from the REAR button LED | No
#3 - Connect to the control unit LIN bus, process it's signals and digitally control haptic experience | The unit has 3 wires - Vcc, Gnd and LIN. the LIN bus sends the "chime" signal to the speakers and can be used for a good haptic experience | Just plug and play, but requires to listen and decode the LIN bus, the LIN bus data may not distinguish between the REAR and ALL window modes | No
#4 - VW aka Volkswagen to come up with updated unit that would provide better experience | Go crazy VW, but please make it backwards compatible :smiley: | "Just plug and play from the OEM" | Yes

### Clone REAR button LED signal with a vibration motor
This was the immediate idea that felt the simplest to execute. However it requires to permananetly modify the part number known as 10A 959 862 S

#### Step 1 - get the signals

Option | Details 
---|---
PCB Side A |  <img src="https://user-images.githubusercontent.com/107234448/178168095-b9813c54-7df4-4347-9288-c45a16fcdb11.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >
PCB Side B |  <img src="https://user-images.githubusercontent.com/107234448/178168103-9d24c681-e8d7-4317-a2f6-28ea7a5df2a1.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >




#### Step 2 - design the circuit

#### Step 3 - test the circuit

#### Step 4 - design and test

