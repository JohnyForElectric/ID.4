# Driver Window Controls Haptic Feedback 

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178169793-c1a1a5a0-1f47-4f78-86ac-e202c0f3f884.JPEG" alt="(part number known as 10A 959 862 S)" width="300px">
</div>

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
...is to e.g. add two self-adhesive pads to help easily locate the touch sensitive area without looking at the location.\
One of the approaches below:\
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178167294-d7f9396d-2661-4cf0-a86d-ff0ece25f306.JPEG "
       alt="Helping to locate the touch sensitive area by two self adhesive pads"
       width="300px"
  />
</div>
:man_dancing: :woman_dancing:

## Solution to challenge #2 - "haptic feedback" 

For the haptic feedback, there is multiple options, as outlined below

Option | Details | Pros/Cons | OEM
---|---|---|---
#1 - Clone REAR button LED signal with a vibration motor | Once the REAR soft button lights up a vibration motor in the unit will vibrate | Simple circuit, but requires tapping into the unit and the motor will vibrate all the time | No
#2 - Digitally process the REAR button LED signal and digitally manage the haptic experience | A micro-controller will receive the REAR button LED signal and control the vibration motor to create better haptic experience | As above requires tapping into the unit, can't "decode" the mode easily from the REAR button LED | No
#3 - Connect to the control unit LIN bus, process it's signals and digitally control haptic experience | The unit has 3 wires - VCC, Gnd and LIN. the LIN bus sends the "chime" signal to the speakers and can be used for a good haptic experience | Just plug and play, but requires to listen and decode the LIN bus, the LIN bus data may not distinguish between the REAR and ALL window modes | No
#4 - VW aka Volkswagen to come up with updated unit that would provide better experience | Go crazy VW, but please make it backwards compatible :smiley: | "Just plug and play from the OEM" | Yes

### Clone REAR button LED signal with a vibration motor
This was the immediate idea that felt the simplest to execute. However it requires to permanently modify the part number known as 10A 959 862 S

#### Step 1 - get the signals

Description | Picture 
---|---
PCB Top Side - notice the touch sensitive areas and the LEDs for the backlight |  <img src="https://user-images.githubusercontent.com/107234448/178168852-df54bf17-b635-4225-a6e8-9a849a5738ea.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >
PCB Bottom Side - notice the microcontroller in the center, LIN interface on the top middle above the 3 pin header/connector |  <img src="https://user-images.githubusercontent.com/107234448/178168865-f210bfb4-26fe-475b-8864-fc78a13027ca.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >
PCB Top Side - detail of the REAR soft button LED |  <img src="https://user-images.githubusercontent.com/107234448/178169162-2850ebea-7fe0-4942-b965-8bda36746d9a.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >
PCB Bottom Side - REAR soft button LED signal pads in red |  <img src="https://user-images.githubusercontent.com/107234448/178169228-30e807a3-c68c-4dd0-b45c-b2dcfcd21cc9.JPEG" alt="HTML image alt text" title="Optional image title" width="300px" >
PCB Bottom Side - REAR soft button LED signal pads with soldered wires (yellow positive signal) |  <img src="https://user-images.githubusercontent.com/107234448/178169375-225d4410-e6e5-442d-8568-b50e5583532a.JPEG" title="Optional image title" width="300px" >
PCB Bottom Side - REAR soft button LED signal pads with soldered wires (yellow positive signal for LED, green negative signal for LED, black ground, red VCC) |  <img src="https://user-images.githubusercontent.com/107234448/178169613-7315cc26-744d-439b-bf05-8e68484e1f69.JPEG" title="Optional image title" width="300px" >


#### Step 2 - design the circuit
A quick design with Opto-coupler to physically separate the input (yellow and green wires) and the 12V/14.4V power line (red and black wire). The signal enters the opto-coupler via resistor R1 (100 Ohms) to opto-coupler ("solid state relay") [LCA110]([url](https://www.digikey.com/en/products/detail/ixys-integrated-circuits-division/LCA110/203107)). The two MOSFETs on the output turn on the vibration motor. The resistor R2 limits the total current and is depending on the type of vibration motor. D1 and D2 1N4148 protect the components (D1 from entering into the circuit, D2 from induction spikes when the motor turns off). Not on the picture - added C1 (0.1 uF) to the power rail.

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178170991-a529c745-80b2-4856-9eb2-a78070eb9c96.JPEG" alt="(part number known as 10A 959 862 S)" width="500px">
</div>

#### Step 3 - test the circuit
Time to test if it works. This design used a cheap vibration motor, R2 was 330O Ohms.
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178171918-aef1febd-014e-4f6d-b250-c3b79b78f387.JPEG" alt="(part number known as 10A 959 862 S)" width="500px">
</div>


#### Step 4 - design and test
Time for more rugged design, used the vibration motor used in the steering wheel touch buttons and added variable resistors to precisely adjust the haptic experience. Both resistors ended up around 100 Ohms. 

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178172063-042a45d0-997e-4ac7-809c-f1c4b93b97e7.JPEG" alt="(part number known as 10A 959 862 S)" width="500px">
</div>

...then 3D printed a "holder" (the red brick on the bottom) for the vibration motor using flexible filament to easily attach it to the part and to mimic the why the vibration motor sits in the steering wheel assembly. Protected all with beloved Tesa tape for a "professional" look :wink:

<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/178172359-7538693f-58f6-43e6-bb61-8adc774c9c2c.JPEG" alt="(part number known as 10A 959 862 S)" width="500px">
</div>
