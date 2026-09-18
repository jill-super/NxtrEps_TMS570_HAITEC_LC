---
title: "TechnicalReference Asr EcuM"
description: "Converted from TechnicalReference_Asr_EcuM.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_EcuM.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (117 pages).

**Pages:** 117

---

This is a **117-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR ECUM 
Technical Reference 
 
 
Version 2.07.02 
 
 
 
 
 
 
 
 
 
 
 
Authors Christian Marchl, Bethina Mausz 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
2/ 1 1 7
1 Document Information 
1.1 History 
Author Date Version Remarks 
Christian Marchl 2006-10-12 0.9 Initial setup 
Christian Marchl 2006-12-12 1.0 Rework of review findings, 
first release 
Christian Marchl 2007-07-30 1.1 Update chapter for AUTOSAR 
2.1 release 
Christian Marchl 2007-09-26 1.2 Description of EcuM_Init() 
function corrected 
Christian Marchl 2008-04-03 1.03.00 Added AUTOSAR 3 changes. 
Christian Marchl 2008-05-07 1.04.00 File renamed according to 
new standard name. 
Christian Marchl, Heike Bischof 2008-05-07 2.00.00 Conversion to MICROSAR 
Technical Reference. 
Christian Marchl 2008-07-23 2.00.01 ESCAN00028261: Added TTII 
in abbreviation table. 
Christian Marchl 2008-10-22 2.00.02 Added description for 
PreCompile implementation 
variant. 
Christian Marchl 2008-12-08 2.01.00 Added description for 
currentMode port, 
Solved ESCAN00031271, 
Added description new callout 
function for selection the boot 
target. 
Christian Marchl 2009-03-20 2.02.00 ESCAN00032687: Added 
chapter for BSW initialization 
example. ESCAN00032038: 
Added chapter how to handle 
wakeup events after 
ShutdownOS() 
Added Chapters 4.7, 4.8, 4.9, 
4.10 
Christian Marchl 2009-05-19 2.03.00 ESCAN00034455: Update 
Figure 2-1 AUTOSAR 
architecture, 
ESCAN00034997: Document 
Restriction and deviations for 
multiple configuration ECUs, 
Ch 4.11. 
Christian Marchl 2009-07-20 2.04.00 ESCAN00035749: Add 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
3/ 1 1 7
restriction for usage of 
InitItems regarding modules 
without standard AUTOSAR 
naming (Ch 4.8.1) 
ESCAN00036018: Add 
chapter configuration variant. 
(Ch 6.1) 
ESCAN00036019: Add 
changed SWC generation 
behavior (Ch 5.8) 
ESCAN00036020: Add 
description for 
UserBlockCode generation 
(Ch 4.12) 
Christian Marchl 2009-09-10 2.04.01 ESCAN00037245: corrected 
description of 
Compiler/Memory Abstraction 
in Ch 4.3. 
Christian Marchl 2009-11-23 2.04.02 ESCAN00039291: Added Ch 
7.3.6 
Christian Marchl 2010-04-13 2.04.03 ESCAN00037828: Corrected 
execution sequence 
regarding WdgM_SetMode() 
(Ch 4.6) 
Rework of review findings: 
(Ch 3.6.3, 7.2.4) 
ESCAN00042035: upda
ted 
chapter 4.6 
ESCAN00039984: adde
d 
chapter 7.2.5. 
ESCAN00042228: extended 
chapter 4.4.7 
ESCAN00042314: extended 
chapter 5.6.2.1, 3.6.1. 
ESCAN00042505: adde
d 
chapter 4.10.4. 
Bethina Mausz 2010-07-30 2.04.04 ESCAN00043965: Corrected 
ECUM_SUBSTATE_MASK 
description in chapter 5.2 
ESCAN00044273: Inserted 
more description in chapter 
4.4.7 
Bethina Mausz 2010-09-20 2.04.05 ESCAN00045520: inserted 
Mcu_PerformReset call into 
chapter 4.6 
Bethina Mausz 2010-10-15 2.05.00 ESCAN00045755: added 
Nvm_GetErrorStatus call into 
NvM_ReadAll loop chapter 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
4/ 1 1 7
4.8.2 
ESCAN00042662: added 
information about CAT1 ISRs 
in chapter 4.7 
ESCAN00046048 adapted 
the description to new Sleep 
Mode ISR handling in chapter 
4.7 
ESCAN00046058 modified 
the description for 
Mcu_SetMode in chapter 
4.10.4 
Bethina Mausz 2010-11-09 2.05.00 Update after review 
Bethina Mausz 2011-01-24 2.07.00 ESCAN00046327 more 
description about 
EcuM_KillAllRUNRequests 
added 
ESCAN00045114 more 
description about 
NvM_CancelWriteAll usage 
added 
ESCAN00046158 more 
description about 
Rte_Feedback usage added 
Figure 2-2 update 
Added the description for new 
configuration parameters: 
“RTE Acknowledgment 
Mechanism” and 
“NvM_CancelWriteAll Timout”
Bethina Mausz 2011-02-09 2.07.01 Architecture Overview 
updated, issues from last 
review fixed and 
ESCAN00048281 
Bethina Mausz 2011-06-17 2.07.02 ESCAN00051734 
modifications in chapter 4.7 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_ECU_StateManager.pdf V1.2.0 
[2] AUTOSAR_SWS_DET.pdf V2.2.0 
[3] AUTOSAR_SWS_DEM.pdf V2.2.1 
[4] AUTOSAR_BasicSoftwareModules.pdf V1.2.0 
Table 1-2 Reference documents 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
5/ 1 1 7
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
6/ 1 1 7
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 4 
2 Introduction ................................................................................................................... 15 
2.1 Architecture Overview..................................................................................... 16 
3 Functional Description ................................................................................................. 18 
3.1 Features.......................................................................................................... 18 
3.2 Initialization ..................................................................................................... 19 
3.3 Startup into wakeup validation state ............................................................... 19 
3.4 States.............................................................................................................. 20 
3.5 Main Functions ............................................................................................... 21 
3.5.1 Run Request Protocol..................................................................................... 21 
3.5.2 Time Triggered Increased Inoperation Protocol.............................................. 22 
3.5.3 Wakeup Validation Protocol ............................................................................22 
3.6 Error Handling................................................................................................. 24 
3.6.1 Development Error Reporting ......................................................................... 24 
3.6.1.1 Parameter Checking ....................................................................................... 26 
3.6.2 Production Code Error Reporting ................................................................... 28 
3.6.3 Vector specific error reporting......................................................................... 28 
4 Integration ..................................................................................................................... 29 
4.1 Scope of Delivery............................................................................................ 29 
4.1.1 Static Files ...................................................................................................... 29 
4.1.2 Dynamic Files ................................................................................................. 29 
4.2 Include Structure............................................................................................. 30 
4.3 Compiler Abstraction and Memory Mapping................................................... 30 
4.4 Dependencies on SW modules ...................................................................... 31 
4.4.1 AUTOSAR OS ................................................................................................ 31 
4.4.2 MCU................................................................................................................ 31 
4.4.3 DEM................................................................................................................ 32 
4.4.4 DET................................................................................................................. 32 
4.4.5 WDGM ............................................................................................................ 32 
4.4.6 COMM ............................................................................................................ 32 
4.4.7 NVM................................................................................................................ 32 
4.4.8 RTE................................................................................................................. 33 
4.4.9 SCHM ............................................................................................................. 33 

Technical Reference MICROSAR ECUM 
©2011, Vector Informatik GmbH Version: 2.07.02 
based on template version 3.1 
7/ 1 1 7
4.4.10 Other BSW Modules ....................................................................................... 33 
4.5 Successive Adding of Modules .......................................................................34 
4.6 Callout execution sequences.......................................................................... 34 
4.7 Critical code sections...................................................................................... 40 
4.7.1 Wakeup Interrupt Source Handling – General Description .............................40 
4.7.2 Wakeup Interrupt Source Handling – Cautions and further Information ......... 41 
4.8 AUTOSAR stack initialization.......................................................................... 41 
4.8.1 Configuration set selection ............................................................................. 41 
4.8.2 Initialization order............................................................................................ 43 
4.9 Handling of wakeup events after ShutdownOS() ............................................44 
4.10 Wakeup event handling and Wakeup Validation............................................. 44 
4.10.1 Wakeup after a physical sleep mode ..............................................................45 
4.10.1.1 Use case description ...................................................................................... 45 
4.10.1.2 Execution flow................................................................................................. 45 
4.10.1.3 Callout implementation examples................................................................... 46 
4.10.2 Handling of wakeup events while ECUM is in RUN state ...............................47 
4.10.2.1 Use case description ...................................................................................... 47 
4.10.2.2 Execution flow................................................................................................. 47 
4.10.2.3 Callout implementation examples................................................................... 47 
4.10.3 Wakeup validation of communication channels (ECUM in RUN state)........... 47 
4.10.3.1 Use case description ...................................................................................... 47 
4.10.3.2 Execution flow................................................................................................. 47 
4.10.3.3 Callout implementation examples................................................................... 49 
4.10.4 Notes to Mcu_SetMode()................................................................................ 50 
4.11 Multiple Identity ECUs .................................................................................

## Extracted outline

- Microsar Ecum *(page 1)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 2.1 release *(page 2)*
- Ecum_Substate_Mask *(page 3)*
- Escan00048281 *(page 4)*
- 1.2 Reference Documents *(page 4)*
- 3.3 Startup into wakeup validation state ............................................................... 19 *(page 6)*
- 3.5.2 Time Triggered Increased Inoperation Protocol.............................................. 22 *(page 6)*
- 3.6.2 Production Code Error Reporting ................................................................... 28 *(page 6)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 30 *(page 6)*
- 4.4 Dependencies on SW modules ...................................................................... 31 *(page 6)*
- 4.5 Successive Adding of Modules .......................................................................34 *(page 7)*
- 4.6 Callout execution sequences.......................................................................... 34 *(page 7)*
- 4.7.1 Wakeup Interrupt Source Handling – General Description .............................40 *(page 7)*
- 4.7.2 Wakeup Interrupt Source Handling – Cautions and further Information ......... 41 *(page 7)*
- 4.8 AUTOSAR stack initialization.......................................................................... 41 *(page 7)*
- 4.9 Handling of wakeup events after ShutdownOS() ............................................44 *(page 7)*
- 4.10 Wakeup event handling and Wakeup Validation............................................. 44 *(page 7)*
- 4.10.1 Wakeup after a physical sleep mode ..............................................................45 *(page 7)*
- 4.10.2 Handling of wakeup events while ECUM is in RUN state ...............................47 *(page 7)*
- 4.10.3 Wakeup validation of communication channels (ECUM in RUN state)........... 47 *(page 7)*
- 4.11.1 Restrictions when implementation variant PreCompile is used ...................... 50 *(page 7)*
- 5.3 Services provided by ECUM........................................................................... 55 *(page 7)*
- 5.3.6 EcuM_ComM_RequestRUN........................................................................... 58 *(page 7)*
- 5.3.7 EcuM_ComM_ReleaseRUN ........................................................................... 59 *(page 7)*
- 5.3.8 EcuM_ComM_HasRequestedRUN ................................................................ 59 *(page 8)*
- 5.3.9 EcuM_RequestPOST_RUN............................................................................ 60 *(page 8)*
- 5.3.10 EcuM_ReleasePOST_RUN............................................................................ 60 *(page 8)*
- 5.3.12 EcuM_SelectShutdownTarget......................................................................... 62 *(page 8)*
- 5.3.14 EcuM_GetShutdownTarget............................................................................. 63 *(page 8)*
- 5.3.15 EcuM_GetLastShutdownTarget ......................................................................63 *(page 8)*
- 5.3.16 EcuM_GetPendingWakeupEvents.................................................................. 64 *(page 8)*
- 5.3.17 EcuM_ClearWakeupEvent.............................................................................. 65 *(page 8)*
- 5.3.18 EcuM_GetValidatedWakeupEvents ................................................................65 *(page 8)*
- 5.3.19 EcuM_GetExpiredWakeupEvents................................................................... 65 *(page 8)*
- 5.3.20 EcuM_GetStatusOfWakeupSource................................................................. 66 *(page 8)*
- 5.3.21 EcuM_SelectApplicationMode ........................................................................ 67 *(page 8)*
- 5.4 Services used by ECUM................................................................................. 70 *(page 8)*
- 5.5.1 EcuM_CB_NfyNvMJobEnd............................................................................. 70 *(page 8)*
- 5.5.2 EcuM_SetWakeupEvent .................................................................................71 *(page 8)*
- 5.5.3 EcuM_ValidateWakeupEvent.......................................................................... 71 *(page 8)*
- 5.6.2.5 EcuM_DeterminePbConfiguration .................................................................. 76 *(page 8)*
- 5.6.2.8 EcuM_GenerateRamHash.............................................................................. 77 *(page 8)*
- 5.6.2.19 EcuM_EnableWakeupSources ....................................................................... 83 *(page 9)*
- 5.6.2.20 EcuM_DisableWakeupSources ...................................................................... 84 *(page 9)*
- 5.6.2.22 EcuM_StopWakeupSources ...........................................................................86 *(page 9)*
- 5.6.2.25 EcuM_GeneratorCompatibilityError................................................................ 87 *(page 9)*
- 5.6.3.1 Appl_EcuM_currentMode_currentMode ......................................................... 90 *(page 9)*
- 5.6.3.2 Rte_Switch_currentMode_currentMode ......................................................... 91 *(page 9)*
- 5.8 Software Component Template....................................................................... 93 *(page 9)*
- 5.8.2 Generation by DaVinci Configurator ............................................................... 94 *(page 9)*
- 6.2 Configuration of ECUM with DaVinci Configurator/EAD .................................96 *(page 9)*
- 6.2.2 ECUM Configuration Perspective ................................................................... 96 *(page 9)*
- 10 / 117 *(page 10)*
- 6.2.2.7 Child Nodes of “Sleep Modes”......................................................................104 *(page 10)*
- 7.1.2 Supervised Entity in WDGM ..........................................................................111 *(page 10)*
- 7.1.3 Parameter “EcuMWdgMStartupModeRef” not supported ..............................111 *(page 10)*
- 7.1.4 Signature and name of DriverInitLists in configuration variant “post-build”....111 *(page 10)*
- 7.1.5 Enabling/Disabling wakeup sources ..............................................................111 *(page 10)*
- 7.1.6 Execution flow in shutdown sequence........................................................... 111 *(page 10)*
- 7.2.3 Wakeup validation in each state ....................................................................112 *(page 10)*
- 7.2.4 Callout EcuM_GeneratorCompatibilityError() ................................................112 *(page 10)*
- 7.2.5 Buffering of wakeup events until COMM is initialized ....................................112 *(page 10)*
- 7.3.1 Link-time Configuration not supported........................................................... 113 *(page 10)*
- 7.3.2 Configuration Check via Consistency Hash not implemented .......................113 *(page 10)*
- 11 / 117 *(page 11)*
- 7.3.5 Not supported configuration parameters........................................................113 *(page 11)*
- 7.3.6 Polling of Wakeup Sources Is Not Supported................................................113 *(page 11)*
- 12 / 117 *(page 12)*
- 13 / 117 *(page 13)*
- 14 / 117 *(page 14)*
- 15 / 117 *(page 15)*
- 2 Introduction *(page 15)*
- 16 / 117 *(page 16)*
- 2.1 Architecture Overview *(page 16)*
- 17 / 117 *(page 17)*
- Sw-C / Rte *(page 17)*
- Autosar Os *(page 17)*
- 18 / 117 *(page 18)*
- 3 Functional Description *(page 18)*
- 3.1 Features *(page 18)*
- 19 / 117 *(page 19)*
- 3.2 Initialization *(page 19)*
- 3.3 Startup into wakeup validation state *(page 19)*
- 20 / 117 *(page 20)*
- 3.4 States *(page 20)*
- Ecum_State_Prep_ *(page 20)*
- Shutdown *(page 20)*
- Ecum_State_Wakeup_ *(page 20)*
- Validation *(page 20)*
- Wakesleep *(page 20)*
- Reaction *(page 20)*
- 21 / 117 *(page 21)*
- 3.5 Main Functions *(page 21)*
- 3.5.1 Run Request Protocol *(page 21)*
- 22 / 117 *(page 22)*
- 3.5.2 Time Triggered Increased Inoperation Protocol *(page 22)*
- 3.5.3 Wakeup Validation Protocol *(page 22)*
- 23 / 117 *(page 23)*
- 24 / 117 *(page 24)*
- 3.6 Error Handling *(page 24)*
- 3.6.1 Development Error Reporting *(page 24)*
- 25 / 117 *(page 25)*
- Null_Ptr *(page 25)*
- Requests *(page 25)*
- Elease *(page 25)*
- _Range *(page 25)*
- Wakeup_Source *(page 25)*
- Uccesfully *(page 25)*
- Usage *(page 25)*
- 26 / 117 *(page 26)*
- Validation_Prot_Error *(page 26)*
- Expected *(page 26)*
- N_State *(page 26)*
- Ibility *(page 26)*
- Sion_Check_Failed *(page 26)*
- 3.6.1.1 Parameter Checking *(page 26)*
- Ecum_E_Generator_Compatibility *(page 26)*
- Ecum_E_Not_Inited *(page 26)*
