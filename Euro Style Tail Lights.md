# Euro style taillights "ID.Light"
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/183325196-1d971dd4-d042-40c1-9f65-0b1fc437ba41.jpeg" alt="(Euro-styke taillights)" width="300px">
</div>

## Situation
There are two types of taillights available for the ID.4. The "base" style (option 8VG) and the smart "ID.Light" (option 8VP). The latter only available in Europe in higher trim vehicles. The US taillights used for model years 2021 and 2022 are simple modification of the "base" Euro. The yellow LEDs in the unit for the turn light are replaced for red. In addition the US spec taillight has an internal connection between the brake segment and turn segment. As such both of these segments come on during braking and when turn light is on. The coding of the CECM (J519) "Vehicle Electrical System Control Module" is adjusted accordingly in US vehicles to "Bremslicht_ist_auch_Blinklicht"=Yes (Brake light is also turn light). In addition, the taillight connector can have one less pin and the wire harness one less wire, which makes it harder to retrofit yellow rear turn lights.

The US model year 2023 physically removed the turn light segment from the taillight for better esthetical appearance as the brake and turn segments were separated by tail/parking segment and it could be "too busy".

The top spec "ID.Light" provides dynamic yellow turn signals and "welcome" animation via main 9 taillight segments. ID Furkan did a good video about those animations [here](https://www.youtube.com/watch?v=KCvncdPqyN0).

This article describes one of the possible approaches to retrofit the Euro-style premium taillight (ID.Light further) into US spec ID.4. While the process for retrofitting to Euro cars can be similar, the existing harness and coding will be different.



## Challenges
- The base taillights use a simple drive-by wire system for each segment, the Euro-spec ID.Light uses a LIN interface and the internal computer of the taillight drives the individual segments based on the message from the LIN bus. So the lights are controlled fundamanetally differently and as such: 
  - The ID.Light has a different connector and additional signals / wires - (a) 12V connection for the internal computer and (b) a LIN bus connection to Gateway (J533)
  - The coding/adaptation of the CECM (J519) "Vehicle Electrical System Control Module" and Gateway (J533) "Data Bus on Board Diagnostic Interface" is very different. *To put the scope of adaptations in perspective - CECM has about 1,600 adaptations and Gateway around 1,000. These are way beyond the "long-coding" that is known from previous generation vehicles.*

## Approach and solutions

### Base Euro Tail Lights for Yellow Blinker (option 8VG)
One option to yellow light rear turn light is replacing of the outer lights with base european version (left 11A 945 095 and right  11A 945 096). The option was not explored in detail, so everything further for this option is a hypothesis. (1) Additional wire(s) need to be routed to the tail light to aacount for a seperate brake and turn indicators, (2) adaptation of CECM (J519) needs to be adjusted. It's not known today how to change the "Bremslicht_ist_auch_Blinklicht" setting to yes, (3) the tail light connector may be different than the US brown version.

### ID.Light Tail Lights for Yellow Blinker & Animations (option 8VP)
Cost-wise the additional investment is the center light (11A 945 276 B), the left (11A 945 207 A) and right (11A 945 208 A) light are almost same price as the base light. The amount of work seemed to be equal, so the decision was made to go with the ID.Light. Also, the "coolness" of animation was unbearable not to have.

Let us set the stage firts. On the scale of difficulty, this project on a 3 scale L-M-H, showed as HH+. The harness is not yet commercially available (the [offer from Kufatec](https://www.kufatec.com/en/light-sight/taillights/complete-set-led-rear-lights-with-dynamic-flashing-light-for-vw-id4-e21-46455)  is only for Euro vehicles and not yet tested for US vehicles), so the only option was to make it using OEM components based on the official electrical diagrams from https://erwin.vw.com/. Another challenge is the coding, the obvious approach is to compare the coding for (Pro Max Euro Version by downtime on [VCDS Forum](https://forums.ross-tech.com/index.php?threads/27745/)). This definitly helped, however the inability to adapt the "Bremslicht_ist_auch_Blinklicht" setting to "No" made the whole project even more complex. 

#### Components

| What | Part Number | Notes
| :------------- | :------------- | :----
| Left Taillight | 11A 945 207 A | Needs "blue" coded connector
| Right Taillight | 11A 945 208 A | Needs "blue" coded connector
| Center Light | 11A 945 276 B | Comes without VW logo, needs "blue" coded connector
| Blue connecotr for outer lights | 982-973-714-A | Waterproof, comes withou pins and without waterproofing rings
| Blue connector for center lights | 1K8 972 928 928 B | Not waterproof

#### Harness
The tail harness needs two power wires from fuse SC24 for the left and fuse SC10 for the right. The fuse slots for SC24 and SC10 are empty. Each power wire (0.5 rt/ge) wire needs to split at the back of the car to the tail connector T8w and T8aa (includes water insulation ring) and the lid interconnect T10e and T10f. Then continue from the lid interconnect T10h and T10i to the MX13 tail light – connectors T8s and T8aj. The LIN is relatively simple, for Pro models with "kick-to-open-tailgeta" the LIN can be found at the back near park assist module (where the DCC module is on Euro cars). The LIN (0.35 vi/sw) needs to go to each taillight connector T8w and T8aa (w/ water insulation ring) and via the lid interconnect T10f to the T8s and T8aj… An additional wire might be needed on the US spec cars from j519/CECM connections - the easiest is to find the "positive connection in tail light harness"  between pins 71 & 60 for T73a connector and 8 & 27 for connector T73b.

| Additional 3 wires (on top - LIN, Turn and +12V | New "blue" connector | Ready to plug in
| :------------- | :------------- | :----
| <img src="https://user-images.githubusercontent.com/107234448/184520654-5c01c179-a1b6-4d28-a6e8-eaa79c23d6da.jpeg" alt="HTML image alt text" title="Optional image title" width="300px"> | <img src="https://user-images.githubusercontent.com/107234448/184520530-3085aaa9-76d3-411c-acad-f30af95224f9.jpeg" alt="HTML image alt text" title="Optional image title" width="300px"> | <img src="https://user-images.githubusercontent.com/107234448/184520535-19230822-567c-4521-8720-42f257af099d.jpeg" alt="HTML image alt text" title="Optional image title" width="300px">
       
#### Coding
Higly recommend [VCDS](https://store.ross-tech.com/shop/vchv2_ent/), [OBD11 PRO](https://obdeleven.com/en/) is a must.

This section is work in progress.

#### End Product

The brake light now spans across the side and center lights and yellow turn light is indepandent.

https://user-images.githubusercontent.com/107234448/184520870-9b423880-1967-45f5-9b03-74fa5c036585.mp4

And this is the one of two welcome animations...

https://user-images.githubusercontent.com/107234448/184521899-61f484e4-4b1e-4c20-8236-670647630f44.mp4


