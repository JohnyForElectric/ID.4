## This page goes deeper into changes made by OTA (over-the-air) updates

A reference page for observed changes of ID.4 US module verson updates after OTA (Over-the-air updates).

## FUTURE Confirmed & upcoming

### 3.6.2 (TBD) - also known as 919A or "Black screen"



## PAST
Car - 2021 AWD, US spec

### 3.2.13 (October 2024) - also known as OUJ9

##### Software versions

| Address | Module | Sofware version before | Sofware version after
| :------------- | :------------- | :------------- | :---
| 19 | CAN Gateway (J533) | 0292	| 0299
| 8123 | App server 1 system 1 adaptive (SWC4) | 0290 | 0299
| 8124 | App server 1 system 2 Java (SWC5) | 0290 | 0299
| C002 | SW Cluster Embedded (SWC2) | 0290 | 0299 
| C003 | SW Cluster Housekeeping (SWC3) | 0290 | 0299 

Other observations - (1) update process very clunky and (2) massive amount of "communication" errors floded all modules after update. This likely happened during update and the update did not perform clean-up.

### 3.2.12 (July 2024) - also known as OUH1
Official VW link https://www.vw.com/en/owners-and-services/connectivity-and-apps/vehicle-software-updates/electric-vehicle-software-updates/electric-vehicle-software-update-3-2.html/__layer/layers/myvwportal/id_software_updates_/id--software-3-2-12-update/master.layer

Official version info "This software update provides minor bug fixes and enhances multiple systems. Enhancements include increased accuracy in the Travel Assist function, optimizations to the over-the-air software installation process, improvements to climate control and enhancements to the defogging function. This update is a prerequisite for future features.”

Our take - based on the modules updated - enhancements in travel assist and climate control plausible. OTA software update process - unlikely due to no changes in moduls such as Telematics, or any ICAS modules. The module that failed the module and bricke our car was 3C and/or A5. More [here]([url](https://www.vwidtalk.com/posts/286642/)).

##### Software versions

| Address | Module | Sofware version before | Sofware version after
| :------------- | :------------- | :------------- | :---
| 03 | Brakes (J104) | 0518	| 0524
| 08 | HVAC (J979) | 0425	| 0460
| 16 | Steering Wheel (J527) | 0071	| 0072
| 23 | Brake Booster (J539)	| 0625 | 0626
| 3C | Lane Change (J1086) | 0287	| 0289
| 42 | Driver Door (J386)	| 0550 | 0551
| 52 | Passenger Door (J387) | 0550 | 0551
| A5 | Frt Sens. Driv. Assist (R242) | 5321 | 5322
| BB | Door Rear Driver (J388) | 0550	| 0551
| BC | Door Reas Pass (J389) | 0550 | 0551

#### Adaptations changes
Please note - any "custom/after market coding" is reset to original values

| Address | Module | Adaptation name | Value before | Value after
| :------------- | :------------- | :------------- | :------------- | :------------- 
| 03 | Brakes (J104) | No changes |||
| 08 | HVAC (J979) | No changes |||
| 16 | Steering Wheel (J527) | IDE07159-ENG273891-Control module switch-off: counter-Bus KnockOut_Ctr | 05 | 07
| 23 | Brake Booster (J539)	| No changes |||
| 3C | Lane Change (J1086) | IDE07159-MAS05583-Control module switch-off: counter-Data bus | 3 | 1
| 42 | Driver Door (J386)	| IDE07159-MAS05583-Control module switch-off: counter-Data bus | 3 | 0
| 52 | Passenger Door (J387) | IDE07159-MAS05583-Control module switch-off: counter-Data bus | 3 | 0
| A5 | Frt Sens. Driv. Assist (R242) | No changes  | |
| BB | Door Rear Driver (J388) | IDE07159-MAS05583-Control module switch-off: counter-Data bus	| 3 | 0
| BC | Door Reas Pass (J389) | IDE07159-MAS05583-Control module switch-off: counter-Data bus | 3 | 0


## Interesting links
https://www.meinid.com/wiki/entry/6-software-versionsst%C3%A4nde-%C3%BCbersicht-3-x/
