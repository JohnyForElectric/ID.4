# Euro style taillights "ID.Light"
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/183325196-1d971dd4-d042-40c1-9f65-0b1fc437ba41.jpeg" alt="(Euro-styke taillights)" width="300px">
</div>

## Situation
There are two types of taillights available for the ID.4. The "base" style (option 8VG) and the smart "ID.Light" (option 8VP). The latter only available in Europe in higher trim vehicles. The US taillights used for model years 2021 and 2022 are simple modification of the "base" Euro. The yellow turn light LEDs in the unit are replaced for red. In addition the US spec taillight has an internal connection between the brake segment and turn segment. As such both of these segments come on during braking and when turn light is on. The coding of the CECM (J519) "Vehicle Electrical System Control Module" is adjusted accordingly in US vehicles to "Bremslicht_ist_auch_Blinklicht"=Yes (Brake light is also turn light). In addition, the taillight connector has one less pin and the wire harness one less wire, which makes it harder to retrofit yellow rear turn lights.

The US model year 2023 physically removed the turn light segment from the taillight for better esthetical appearance as the brake and turn segments were separated by tail/parking segment.

The top spec "ID.Light" provides dynamic yellow turn signals and "welcome" animation via main 9 taillight segments. ID Furkan did a good video about those animations [here](https://www.youtube.com/watch?v=KCvncdPqyN0).

This article describes one of the possible approaches to retrofit the Euro-style premium taillight (ID.Light further) into US spec ID.4. While the process for retrofitting to Euro cars can be similar, the existing harness and coding will be different.



## Challenges
- The base taillights use a simple drive-by wire system for each segment, the Euro-spec ID.Light uses a LIN interface and the internal computer of the taillight drives the individual segments based on the message from LIN bus. So the lights are controlled fundamanetally differently and as such: 
  - The ID.Light has a different connector and additional signals / wires - (a) 12V connection for the internal computer and (b) a LIN bus connection to Gateway (J533)
  - The coding/adaptation of the CECM (J519) "Vehicle Electrical System Control Module" and Gateway (J533) "Data Bus on Board Diagnostic Interface" is very different. *To put the scope of adaptations in perspective - CECM has about 1,600 adaptations and Gateway around 1,000. These are way beyond the "long-coding" that is known from previous generation vehicles.*

## Approach and solutions

### Option 1: Base Euro Tail Lights for Yellow Blinker (option 8VG)
One option for yellow rear "blinker" is to replace the outer lights with base european version (left 11A 945 095 and right 11A 945 096). This option was not explored in detail, so everything further for this option is a hypothesis. (1) Additional wire(s) need to be routed to the tail light to account for a seperate brake and turn indicators, (2) adaptation of CECM (J519) needs to be adjusted. It's not known today how to change the "Bremslicht_ist_auch_Blinklicht" setting to "No", (3) the tail light connector (that is "coded" by a small notch on the side) may be different than the US "brown-coded" version. 

### Option 2: ID.Light Tail Lights for Yellow Blinker & Animations (option 8VP)
This option compared to the previuos adds the center light (11A 945 276 B). The left (11A 945 207 A) and right (11A 945 208 A) lights are available for almost same price as the base light (option 1). The amount of work seemed to be equal, so the decision was made to go with the ID.Light for this project. Also, the "coolness" of animation was unbearable not to try out. Seriously :)

Let us set the stage first. On the scale of difficulty, this project on a 3 scale Low-Medium-Hight, showed as High++. The harness is not yet commercially available (the [offer from Kufatec](https://www.kufatec.com/en/light-sight/taillights/complete-set-led-rear-lights-with-dynamic-flashing-light-for-vw-id4-e21-46455) is only for Euro vehicles and not yet tested for US vehicles), so the only option was to make it using OEM components based on the official electrical diagrams from  https://erwin.vw.com/. Another challenge is the coding/adaptatiopn, the obvious approach was to compare US Spec vehicle coding with the coding of Pro Max ID.4 Euro . Luckily'downtime' posted full adaptation maps on [VCDS Forum](https://forums.ross-tech.com/index.php?threads/27745/) - thank you, this helped a ton! However the inability to adapt the "Bremslicht_ist_auch_Blinklicht" setting to "No" (with VCDS or OBD11) made the entire project more complex - more in [VCDS Forum](https://forums.ross-tech.com/index.php?threads/33372/#post-281097)). We do have a workaround solution that cancels all errors on the dash and allows to "unplug" the taillights for software updates, but is not as elegant as desired... and is described below.

#### Components Needed

| What | Part Number | Notes
| :------------- | :------------- | :----
| 1 x Left Taillight | 11A 945 207 A | A.k.a "MX3. "Needs "blue" coded connector (the pin layout of the connector is the same, but there is a noth on a different place that prevents connecting differently "coded" connectors. The color of the connector is different to denote the different "coding".)
| 1 x Right Taillight | 11A 945 208 A | A.k.a "MX4. _same connector as above_
| 1 x Center Light | 11A 945 276 B | A.k.a "MX13". Comes without VW logo, needs "blue" coded connector. T?he connector is different than connector for MX3 and MX4/
| 2 x Blue connector for outer lights (MX3 and MX4) | 982-973-714-A | Waterproof, comes without pins and without waterproofing rings
| 2 x Blue connector for center lights (MX13) | 1K8 972 928 928 B | Not waterproof, the middle light has two connectors for each side

# Harness
The harness shall deliver power (+12/14.4V), data (LIN) and for US pec vehicles additional wire for separete turn light. The harness starts in the internal fuse box / CECM(J519) on the dirver's side and can be routed along the main harness to the back of the car, where it splits in three ways: to each side and up throught the tailgate to middle lights.
 - The two power wires go from fuse SC24 for the left and fuse SC10 for the right. The fuse slots for SC24 and SC10 are empty. Each power wire (0.5 rt/ge) wire splits at the back of the car to the tail connector T8w and T8aa (includes water insulation ring) and the lid interconnect T10e and T10f. Then continues from the lid interconnect T10h and T10i to the MX13 tail light – connectors T8s and T8aj. 
 - The LIN is routerd from Gateway/ICAS1(J533). For Pro models with "kick-to-open-tailgate" the LIN can be found at the back near park assist module (where the DCC module is on Euro cars). The LIN (0.35 vi/sw) goes to each taillight connector T8w and T8aa (w/ water insulation ring) and via the lid interconnect T10f to the MX13 T8s and T8aj. 
 - An additional wire for each side is needed on the US spec cars from J519/CECM connections - the easiest is to find the "positive connection in tail light harness" between pins 71 & 60 from the T73a connector and 8 & 27 from connector T73b (great theory, we could not easilly find the splice so we routed an extra wire). However with the "Bremslicht_ist_auch_Blinklicht"=Yes workaround we recommend to route in total two extra wires for each side (one turn and one break signal) - so 4 in total.

## Pin to pin connections

Following table shows connections between J519/CECM and each tail-light connector. Left tail MX3 (connector T8w), center tail MX13 (connectors T8s and T8aj) and right tail MX4 (connector T8aa). 

The "Workround/US" column shows suggested connections for US vehicles in case the adaptation "Bremslicht_ist_auch_Blinklicht" *__cannot__* be changed to __no__. If "Bremslicht_ist_auch_Blinklicht"=Yes, the coding is *__expecting__* one channel to be *__coded__* as "joined turn and brake light" (last row of the table). In addition the load management cannot be disabled by setting the "Lasttyp" to "LED_Kleinleistung_ohne_Open_Load_Diagnose" so it has to be terminated by a resistor. The resistor maximal resistance (minimal current) was determined as 400Ohms, in some situations (with low 12V battery) an error can show on the dash, so the suggested value is 300Ohms (that is approx. 50mA and 0.7W), for safety we picked 10W resistor.

For better understanding of the table, let us explain the J519/CECM light channels and essentials of coding. The J519/CECM has 29 "light channels" that can be configured and adapted with multiple different advanced functions, numbered from 16 to 45. Those channels show in adaptation as e.g. "Leuchte 18 BLK HL A60" - that means "Lights", then channel # (e.g. 18), function (BLK=Blinker/Turn light, BR=Brems Licht/Brake Light, SL=Tail Lights, RFL=Backup light, NSL=Fog lights (not used in US spec vehicles)...), Location (HL=Hinten Links/Rear Left, HR=Hinten Rechtes/Rear Right,...), connector and pin of the J519/CECM (A61=connector T73a/pin 61; C09=connector T73b/pin 9 and B03=connector T46f/pin 3...)

The table shows both the "logical" connections - that correspond with the adaptation channel in J519/CECM (for coding) and "physical" connection that is the actual connector and pin of the J519/CECM.

| Signal | Expected/Euro: <BR> J519/CECM Logical (Physical) Connection ("Bremslicht_ist_auch_Blinklicht" = No)  | Workaround/US: <BR> J519/CECM Logical (Physical) Connection ("Bremslicht_ist_auch_Blinklicht"=Yes) | Connected to...
| :------------- | :------------- | :----  | :----
| Turn Light | 18 BLK HL A60 (Connector T73a /60);<BR> 19 BLK HR C27 (Connector T73b /27) | 40 Zusatz hecklicht HL B03 (Connector T46f /3);<BR> 41 Zusatz hecklicht HR B20 (Connector T46f /20) | Turn Light Lamp:<BR> MX3 (Connector T8w /8);<BR> MX4 (Connector T8aa /8) 
| Brake Light | 20 BR L A71 (Connector T73a /71);<BR> 21 BR R C8 (Connector T73b /8) | 18 BLK HL A60 (Connector T73a /60);<BR> 19 BLK HR C27 (Connector T73b /27) | Brake Light Lamp:<BR>  MX3 (Connector T8w /5);<BR> MX4 (Connector T8aa /5) and<BR> MX13 (Connectors T8s /5 and T8aj /5)
| Tail/Posion Lamps | 23 SL HL C31; <BR> 24 SL HR A61 | 23 SL HL C31; <BR> 24 SL HR A61 | Not connected, only proper coding required to aviod error on the dash
| Error Cancellantion | Not necessary |  20 BR L A71 (Connector T73a /71); <BR> 21 BR R C8 (Connector T73b /8) | Coded as combined Brake and Turn Light, connected via 300 Ohm resistor to ground

## Wiring & harness photos

| Additional 3 wires (on top - LIN, Turn and +12V | New "blue" connector | Ready to plug in
| :------------- | :------------- | :----
| <img src="https://user-images.githubusercontent.com/107234448/184520654-5c01c179-a1b6-4d28-a6e8-eaa79c23d6da.jpeg" alt="HTML image alt text" title="Optional image title" width="300px"> | <img src="https://user-images.githubusercontent.com/107234448/184520530-3085aaa9-76d3-411c-acad-f30af95224f9.jpeg" alt="HTML image alt text" title="Optional image title" width="300px"> | <img src="https://user-images.githubusercontent.com/107234448/184520535-19230822-567c-4521-8720-42f257af099d.jpeg" alt="HTML image alt text" title="Optional image title" width="300px">
       
# Coding
[OBD11 PRO](https://obdeleven.com/en/) is a must. Higly recommend [VCDS](https://store.ross-tech.com/shop/vchv2_ent/) for exporting Ada/Adaptations maps for comparisons and coding itself... 

This section is work in progress... We are close... More coming very soon...

## Module 19 / ICAS1 / CAN Gateway

### Configure IQ Lights
- ENG253039-SFT271909-Intelligente Heckleuchte-Verbau-left tail lamp 1, __installed__ 
- ENG253039-SFT272142-Intelligente Heckleuchte-Verbau-left tail lamp 2, __installed__
- ENG253039-SFT272143-Intelligente Heckleuchte-Verbau-Right rear tail lamp 1, __installed__
- ENG253039-SFT272144-Intelligente Heckleuchte-Verbau-Right rear tail lamp 2, __installed__
  
### Configure Light Parameters
ENG253070-ENG258451-Intelligente Heckleuchte-Parametierung-p_SHL_Anim_LTM_Auto, __active__
ENG253070-ENG259407-Intelligente Heckleuchte-Parametierung-p_SHL_AnimDimm_Freigabe_KL15aus, __1__
ENG253070-ENG260457-Intelligente Heckleuchte-Parametierung-p_SHL_AnimDimm_Freigabe_KL15ein, __1__
ENG253070-ENG259766-Intelligente Heckleuchte-Parametierung-p_SHL_dynamisch, __active__
  
### Enable light animations
IDE12986-ENG278492-BAP configuration-Bap_fc_list_exterior_light,FF FF FF F__F__ FF FF
IDE12986-ENG142232-BAP configuration-HMI_exterior_light_sensitivity,__7__
IDE12986-ENG278470-BAP configuration-HMI_exterior_light_sensitivity_2,__3__
  
 

# Conclusion
  
#### ... and the End Product

The brake light now spans across the side and center lights and yellow turn light is indepandent.

https://user-images.githubusercontent.com/107234448/184520870-9b423880-1967-45f5-9b03-74fa5c036585.mp4

And this is the one of two welcome animations...

https://user-images.githubusercontent.com/107234448/184521899-61f484e4-4b1e-4c20-8236-670647630f44.mp4


