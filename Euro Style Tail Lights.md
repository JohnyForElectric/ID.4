# Euro style taillights "ID.Light"
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/183325196-1d971dd4-d042-40c1-9f65-0b1fc437ba41.jpeg" alt="(Euro-styke taillights)" width="300px">
</div>

## Situation
There are two types of taillights available for the ID.4. The "base" style (option 8VG) and the smart "ID.Light" (option 8VP). The latter only available in Europe in higher trim vehicles. The US taillights used for model years 2021 and 2022 are simple modification of the "base" Euro. The yellow LEDs in the unit for the turn light are replaced for red. In addition the US spec taillight has an internal connection between the brake segment and turn segment. As such both of these segments come on during braking and when turn light is on. The coding of the CECM (J519) "Vehicle Electrical System Control Module" is adjusted accordingly in US vehicles to "Bremslicht_ist_auch_Blinklicht"=Yes (Brake light is also turn light). In addition, the taillight connector can have one less pin and the wire harness one less wire.

The US model year 2023 physically removed the turn light segment from the taillight for better esthetical appearance as the brake and turn segments were separated by tail/parking segment and it could be "too busy".

The top spec "ID.Light" provides dynamic yellow turn signals and "welcome" animation via main 9 taillight segments. ID Furkan did a good video about those animations [here]([url](https://www.youtube.com/watch?v=KCvncdPqyN0)).

This article describes one of the possible approaches to retrofit the Euro-style premium taillight (ID.Light further) into US spec ID.4. While the process for retrofitting to Euro cars can be similar, the existing harness and coding will be different.

## Challenges
- The base taillights use a simple drive-by wire system for each segment, the Euro-spec ID.Light uses a LIN interface and the internal computer of the taillight drives the individual segments based on the message from the LIN bus. So the lights are controlled fundamanetally differently and as such: 
  - The ID.Light has a different connector and additional signals / wires - (a) 12V connection for the internal computer and (b) a LIN bus connection to Gateway (J533)
  - The coding/adaptation of the CECM (J519) "Vehicle Electrical System Control Module" and Gateway (J533) "Data Bus on Board Diagnostic Interface" is very different. In addition the Euro model has a higher spec of the CECM (H+). *To put the scope of adaptations in perspective - CECM has about 1,600 adaptations and Gateway around 1,000. These are way beyond the "long-coding" that is known from previous generation vehicles.*

