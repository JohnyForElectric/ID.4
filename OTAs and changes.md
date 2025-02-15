## This page goes deeper into changes made by OTA (over-the-air) and workshop (ODIS) updates

A reference page for observed module changes for 2021 ID.4 AWD US specification after OTA (Over-the-air) and worshop (ODIS) updates.

## FUTURE Confirmed & upcoming


## PAST

### ID.software version 3.5.11 (OTA & workshop ODIS) - also known as 919A or "Black screen"

| Address | Module | Sofware version before | Sofware version after
| :------------- | :------------- | :------------- | :---
| 01 | Engine (J623-EBRA) | 2222	| 2603
| 03 | ABS Brakes (J104) | 0524 | 0526
| 09 | Cent. Elect. (J519) | 0307 | 0311
| 19 | CAN Gateway (J533) | 0299 | 0329 
| 5F | Information Electr. (J794) | 0561 | 1751
| 6C | Back-up Cam. (J772) | 0394 | 0397
| 75 | Telematics (J949) | 0664 | 0686
| C6 | Batt. Chrg. (J1050) | 1019 | 2022
| 8123 | App server 1 system 1 adaptive (SWC4) | 0299 | 0329
| 8124 | App server 1 system 2 Java (SWC5) | 0299 | 0329
| 8125 | App server 3 system 1 infotaint. (SWC6) | 0561 | 1751
| C002 | SW Cluster Embedded (SWC2) | 0299 | 0329
| C003 | SW Cluster Housekeeping (SWC3) | 0299 | 0329 


### ID.software version 3.2.13 (OTA October 2024) - also known as OUJ9

Our take - progress and actual update process not great (more on [VWIDTalk](https://www.vwidtalk.com/posts/296230/)), changes in the actual payload likely aligned with the official "OTA improvements" messaging as all ICAS systems were updated. No changes to custom adaptations in 19 CAN Gateway (J533) surprisingly. The hypothesis is that there were no code changes for the actual Gateway section of the module. 

Other observations - (1) update process very clunky and (2) massive amount of "communication" errors floded all modules after update. This likely happened during update and the update did not perform clean-up.

##### Software versions

| Address | Module | Sofware version before | Sofware version after
| :------------- | :------------- | :------------- | :---
| 19 | CAN Gateway (J533) | 0292	| 0299
| 8123 | App server 1 system 1 adaptive (SWC4) | 0290 | 0299
| 8124 | App server 1 system 2 Java (SWC5) | 0290 | 0299
| C002 | SW Cluster Embedded (SWC2) | 0290 | 0299 
| C003 | SW Cluster Housekeeping (SWC3) | 0290 | 0299 

### ID.software version 3.2.12 (OTA July 2024) - also known as OUH1
Official VW [link](https://www.vw.com/en/owners-and-services/connectivity-and-apps/vehicle-software-updates/electric-vehicle-software-updates/electric-vehicle-software-update-3-2.html/__layer/layers/myvwportal/id_software_updates_/id--software-3-2-12-update/master.layer)

Official version info "This software update provides minor bug fixes and enhances multiple systems. Enhancements include increased accuracy in the Travel Assist function, optimizations to the over-the-air software installation process, improvements to climate control and enhancements to the defogging function. This update is a prerequisite for future features.”

Our take - based on the modules updated - enhancements in travel assist and climate plausible, but no changes observed while driving. OTA software update process enhancements - unlikely due to no changes in modules such as Telematics, or any ICAS modules. The module that failed the update and bricked our car was 3C and/or A5. More [here](https://www.vwidtalk.com/posts/286642/). There also were additional changes to all door modules, likely related to door handle recall that was not advertised in the official description.

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
