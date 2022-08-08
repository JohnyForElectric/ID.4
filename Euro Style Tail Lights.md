# Euro style taillights "ID.Light"
<div align="center">
  <img src="https://user-images.githubusercontent.com/107234448/183325196-1d971dd4-d042-40c1-9f65-0b1fc437ba41.jpeg" alt="(Euro-styke taillights)" width="300px">
</div>

## Situation
There are two types of taillights available on the ID.4. The "base" style (option 8VG) and the smart "ID.Light" (option 8VP) that are only available in Europe in higher trim vehicles. The US taillights used for model years 2021 and 2022 are simple modification of the base Euro. The yellow LEDs in the unit for the turn light (that is yellow in Europe) is replaced for red, in addition the US spec taillight has an internal connection between the brake segment and turn segment. As such both of these segments come on during braking and when turn light is on. The coding of the CECM (J519) "Vehicle Electrical System Control Module" is adjusted accordingly to "Bremslicht_ist_auch_Blinklicht"=Yes (Brake light is also turn light). In addition, the taillight connector can have one less pin and wire.

The model year 2023 physically removed the turn light segment from the taillight for better esthetical appearance as the brake and turn segments were separated by tail/parking segment and it IMHO too much was happening in the dark, when the car was braking and turning.

The top spec "ID.Light" provides dynamic yellow turn signals and "welcome" animation the main taillight. ID Furkan did a good video about those animations [here]([url](https://www.youtube.com/watch?v=KCvncdPqyN0)).

This article describes one of the possible approaches to retrofit the Euro-style premium taillight (ID.Light further) into US spec ID.4.

## Challenges
1. The base taillights use a simple drive-by wire system for each segment, the Euro-spec ID.Light uses a LIN interface and the internal computer drives the individual segments based on the message from the LIN bus.
2. The ID.Light has a an additional 12V connection for the internal computer
3. The coding/adaptation of the CECM (J519) "Vehicle Electrical System Control Module" and Gatway (J533) "Data Bus on Board Diagnostic Interface" (the official name does not make much sense to me) is very different, in addition the Euro model has a hiugher spec of the CECM. To put the scope of adaptation in perspective - CECM has about 1,600 adaptations and Gateway around 1,000. These is way beyond the "long-coding" that is known from previous generation vehicles.

![IMG_3781](https://user-images.githubusercontent.com/107234448/183325196-1d971dd4-d042-40c1-9f65-0b1fc437ba41.jpeg)
