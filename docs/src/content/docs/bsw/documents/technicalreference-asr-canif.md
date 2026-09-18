---
title: "TechnicalReference Asr CanIf"
description: "Converted from TechnicalReference_Asr_CanIf.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanIf.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (62 pages).

**Pages:** 62

---

This is a **62-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

CAN Interface 
Technical Reference 
 
 
Version 2.10.01 
 
 
 
 
 
 
 
 
 
 
Authors Thomas Arnold, Rüdiger Naas, Eugen Stripling 
Versions: 2.10.01 
Status: Released 
 
 
 
 
 

Technical Reference CAN Interface 
©2011, Vector Informatik GmbH Version: 2.10.01 
based on template version 2.10.0 
2/ 6 2
1 Document Information 
1.1 History 
Author Date Version Remarks 
Thomas Arnold 2006-06-22 1.0 Initial version 
Thomas Arnold 2006-07-05 1.1 Minor corrections (Review) 
Add additional DET error codes 
Thomas Arnold 2006-07-05 1.2 Add justification for possible 
compiler warning 
Thomas Arnold 2006-10-30 1.3 Add additional features (TxFullCAN, 
TxPolling, …), 
Add GENy configuration chapter. 
Hartmut Hörner 2007-01-04 1.4 Added information about supported 
AUTOSAR version 
Thomas Arnold 2007-01-19 1.5 Add additional features (BusOff 
polling, Post build configuration). 
Changes in GENy configuration 
chapter. 
Thomas Arnold 2007-06-04 1.6 Adapt to AUTOSAR 2.1 
Thomas Arnold 2007-07-20 1.7 Switch to new template / 
modifications for Autosar 2.1 
Thomas Arnold 2008-03-03 1.8 Add Extended ID support 
Thomas Arnold 2008-03-10 2.0 Adapt to AUTOSAR 3 
Thomas Arnold 2008-05-16 2.1 Changes due to review: 
- Add info about DLC to 
ReadRxPduData API 
- Layout changes 
- Remove Can_MainFunction 
API 
- … 
Thomas Arnold 2008-06-11 2.2 Add CanIf_CanTrcv.h to chapter 
4.1.2 
Thomas Arnold 2008-08-04 2.3 Add description of 
WakeUpValidation (Chapters 3.12, 
3.15, 6.19) 
Update GENy Screenshots and 
description (Chapter 5) 
Thomas Arnold 2008-10-07 2.4 Change GENy attribute names 
(Chapter 5) 
Update include structure (Chapter 
4.2) 

Technical Reference CAN Interface 
©2011, Vector Informatik GmbH Version: 2.10.01 
based on template version 2.10.0 
3/ 6 2
Thomas Arnold 2008-10-17 2.5 Add description of AUTOSAR 2.1 
ComM support (Chapter 3.16) 
Thomas Arnold 2008-10-31 2.6 Update of figure 3-1 
Update GENy screenshots / 
attribute names (Chapter 5) 
Rework chapter 6 API description 
Minor improvements 
Rüdiger Naas 2009-06-29 2.7 Description Double Hash search 
algorithm added 
Rüdiger Naas 2009-08-25 2.7.1 Limitation for API CanIf_Transmit() 
added 
Rüdiger Naas 2009-09-25 2.7.2 Chapter Deviations/Limitations 
added 
Rüdiger Naas 2009-11-23 2.7.3 Defines for CanIf_PduSetModeType 
changed 
Example for how to convert 
Upper/Lower ID to mask and code. 
Rüdiger Naas 2010-01-11 2.7.4 Minor changes regarding indication 
function types. 
Rüdiger Naas 2010-03-08 2.8.0 Dynamic transmit L-PDU handles 
EcuM_GeneratorCompatibilityError 
API added 
Rüdiger Naas 2010-06-30 2.9.0 Expansion of the description for the 
interrupt lock mechanism 
Typo corrected for chapter 
“sleep/wakeup” 
Tx buffer handling expansion 
Postbuild parameter description 
changed 
Bit Queue support 
Rüdiger Naas 2011-01-12 2.10.0 Some typos corrected at chapter 
“sleep/wakeup”. 
Eugen Stripling 2011-06-30 2.10.01 DLC check against not optimized 
DLC 
Table 1-1 History of the Document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_CAN_Interface.pdf 3.0.1 
[2] AUTOSAR_SWS_DET.pdf 2.2.0 
[3] AUTOSAR_SWS_DEM.pdf 2.2.1 
[4] AUTOSAR_BasicSoftwareModules.pdf 1.2.0 
Table 1-2 References Documents 

Technical Reference CAN Interface 
©2011, Vector Informatik GmbH Version: 2.10.01 
based on template version 2.10.0 
4/ 6 2
 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference CAN Interface 
©2011, Vector Informatik GmbH Version: 2.10.01 
based on template version 2.10.0 
5/ 6 2
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 3 
2 Introduction ................................................................................................................... 10 
2.1 Architecture Overview..................................................................................... 10 
3 Functional Description ................................................................................................. 12 
3.1 Deviations regarding AUTOSAR standard...................................................... 12 
3.2 Feature List..................................................................................................... 12 
3.3 Initialization ..................................................................................................... 13 
3.4 Transmission................................................................................................... 14 
3.5 Dynamic transmission..................................................................................... 15 
3.6 Transmit Buffer ............................................................................................... 15 
3.7 Reception........................................................................................................ 16 
3.8 Ranges ........................................................................................................... 16 
3.9 DLC check ...................................................................................................... 17 
3.9.1 DLC check against not optimized DLC ........................................................... 18 
3.10 Communication Modes ................................................................................... 18 
3.10.1 Controller Mode .............................................................................................. 18 
3.10.2 Channel Mode ................................................................................................ 18 
3.11 Polling ............................................................................................................. 19 
3.12 Error Notification ............................................................................................. 19 
3.12.1 Development Error Detection ......................................................................... 19 
3.12.2 Production Error Detection ............................................................................. 23 
3.13 Transceiver handling....................................................................................... 23 
3.14 Sleep / WakeUp.............................................................................................. 24 
3.15 Bus Off............................................................................................................ 27 
3.16 Version Info..................................................................................................... 27 
3.17 Services used by the CAN Interface............................................................... 28 
3.18 Critical Sections .............................................................................................. 29 
3.19 AUTOSAR 2.1 ComM compliance.................................................................. 30 
3.19.1 API Description ............................................................................................... 30 
3.19.2 Call back functions.......................................................................................... 31 
3.19.3 Initialization ..................................................................................................... 31 
4 Integration ..................................................................................................................... 33 
4.1 Files and include structure.............................................................................. 33 

Technical Reference CAN Interface 
©2011, Vector Informatik GmbH Version: 2.10.01 
based on template version 2.10.0 
6/ 6 2
4.1.1 Static Files ...................................................................................................... 33 
4.1.2 Dynamic Files ................................................................................................. 33 
4.2 Include Structure............................................................................................. 34 
4.3 Compiler Abstraction and Memory Mapping................................................... 34 
5 Configuration ................................................................................................................ 36 
5.1 Module properties ........................................................................................... 36 
5.1.1 Common configuration.................................................................................... 36 
5.1.2 Post build configuration .................................................................................. 37 
5.1.3 Miscellaneous ................................................................................................. 38 
5.1.3.1 Software Filter Type........................................................................................ 40 
5.1.3.2 Transmit Buffer ............................................................................................... 41 
5.1.3.3 Callback functions........................................................................................... 42 
5.1.3.4 MICROSAR extensions .................................................................................. 43 
5.2 Channel specific properties ............................................................................ 44 
5.3 Tx message properties ................................................................................... 45 
5.4 Dynamic Tx message properties .................................................................... 46 
5.5 Rx message properties................................................................................... 47 
6 API Description ............................................................................................................. 48 
6.1 Services provided by the CAN Interface......................................................... 48 
6.1.1 CanIf_GetVersionInfo ..................................................................................... 48 
6.1.2 CanIf_Init ........................................................................................................ 48 
6.1.3 CanIf_InitController......................................................................................... 48 
6.1.4 CanIf_SetControllerMode ............................................................................... 49 
6.1.5 CanIf_GetControllerMode............................................................................... 49 
6.1.6 CanIf_Transmit ............................................................................................... 50 
6.1.7 CanIf_TxConfirmation..................................................................................... 50 
6.1.8 CanIf_RxIndication ......................................................................................... 50 
6.1.9 CanIf_ControllerBusOff................................................................................... 51 
6.1.10 CanIf_SetPduMode ........................................................................................ 51 
6.1.11 CanIf_GetPduMode ........................................................................................ 52 
6.1.12 CanIf_InitMemory ........................................................................................... 52 
6.1.13 CanIf_CancelTxConfirmation.......................................................................... 53 
6.1.14 CanIf_SetTransceiverMode ................................................................

## Extracted outline

- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 1.2 Reference Documents *(page 3)*
- 3.1 Deviations regarding AUTOSAR standard...................................................... 12 *(page 5)*
- 3.9.1 DLC check against not optimized DLC ........................................................... 18 *(page 5)*
- 3.17 Services used by the CAN Interface............................................................... 28 *(page 5)*
- 3.19 AUTOSAR 2.1 ComM compliance.................................................................. 30 *(page 5)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 34 *(page 6)*
- 5.4 Dynamic Tx message properties .................................................................... 46 *(page 6)*
- 6.1 Services provided by the CAN Interface......................................................... 48 *(page 6)*
- 6.1.16 CanIf_GetTrcvWakeupReason .......................................................................54 *(page 6)*
- 6.1.17 CanIf_SetTransceiverWakeupMode ...............................................................54 *(page 6)*
- 6.2.1 EcuM_GeneratorCompatibilityError................................................................ 59 *(page 7)*
- 10 / 62 *(page 10)*
- 2 Introduction *(page 10)*
- 2.1 Architecture Overview *(page 10)*
- 11 / 62 *(page 11)*
- Com Dcm *(page 11)*
- Can Drv *(page 11)*
- Trcv Drv *(page 11)*
- 12 / 62 *(page 12)*
- 3 Functional Description *(page 12)*
- 3.1 Deviations regarding AUTOSAR standard *(page 12)*
- 3.2 Feature List *(page 12)*
- 13 / 62 *(page 13)*
- 3.3 Initialization *(page 13)*
- 14 / 62 *(page 14)*
- 3.4 Transmission *(page 14)*
- 15 / 62 *(page 15)*
- Canif_Get_Tx_Online *(page 15)*
- 3.5  Dynamic transmission *(page 15)*
- 3.6 Transmit Buffer *(page 15)*
- 16 / 62 *(page 16)*
- 3.7 Reception *(page 16)*
- 3.8 Ranges *(page 16)*
- 17 / 62 *(page 17)*
- 3.9 DLC check *(page 17)*
- 18 / 62 *(page 18)*
- 3.9.1 DLC check against not optimized DLC *(page 18)*
- 3.10 Communication Modes *(page 18)*
- 3.10.1 Controller Mode *(page 18)*
- - Canif_Cs_Stopped *(page 18)*
- - Canif_Cs_Started *(page 18)*
- - Canif_Cs_Sleep *(page 18)*
- - Canif_Cs_Uninit *(page 18)*
- 3.10.2 Channel Mode *(page 18)*
- 19 / 62 *(page 19)*
- - Canif_Get_Offline *(page 19)*
- - Canif_Get_Rx_Online *(page 19)*
- - Canif_Get_Tx_Online *(page 19)*
- - Canif_Get_Online *(page 19)*
- - Canif_Get_Offline_Active *(page 19)*
- - Canif_Get_Offline_Active_Rx_Online *(page 19)*
- 3.11 Polling *(page 19)*
- 3.12 Error Notification *(page 19)*
- 3.12.1 Development Error Detection *(page 19)*
- 20 / 62 *(page 20)*
- 1 CanIf_Init *(page 20)*
- 2 CanIf_InitController *(page 20)*
- 3 CanIf_SetControllerMode *(page 20)*
- 4 CanIf_GetControllerMode *(page 20)*
- 5 CanIf_Transmit *(page 20)*
- 6 CanIf_ReadRxPduData *(page 20)*
- 9 CanIf_SetPduMode *(page 20)*
- 10 CanIf_GetPduMode *(page 20)*
- 11 CanIf_GetVersionInfo *(page 20)*
- 13 CanIf_SetTransceiverMode *(page 20)*
- 14 CanIf_GetTransceiverMode *(page 20)*
- 15 CanIf_GetTrcvWakeupReason *(page 20)*
- 16 CanIf_SetTransceiverWakeupMode *(page 20)*
- 17 CanIf_CheckWakeup *(page 20)*
- 18 CanIf_CheckValidation *(page 20)*
- 19 CanIf_TxConfirmation *(page 20)*
- 20 CanIf_RxIndication *(page 20)*
- 21 CanIf_CancelTxConfirmation *(page 20)*
- 22 CanIf_ControllerBusoff *(page 20)*
- 250 CanIf_CancelTransmit *(page 20)*
- 251 CanIf_CancelTxNotification *(page 20)*
- 10 CANIF_E_PARAM_CANID The error code is used if an invalid CAN identifier *(page 20)*
- 11 CANIF_E_PARAM_DLC The error will be reported by *(page 20)*
- 12 CANIF_E_PARAM_LPDU The error will be raised by the following functions *(page 20)*
- 21 / 62 *(page 21)*
- 13 CANIF_E_PARAM_HRH The error code is used in the function *(page 21)*
- 14 CANIF_E_PARAM_CHANNEL Not used. *(page 21)*
- 15 CANIF_E_PARAM_CONTROLLER Used by the following functions if an invalid *(page 21)*
- 20 CANIF_E_PARAM_POINTER The error is raised if a NULL pointer is passed to *(page 21)*
- 30 CANIF_E_UNINIT The error is raised if one of the following API *(page 21)*
- 22 / 62 *(page 22)*
- 40 CANIF_E_NOK_NOSUPPORT Not used. *(page 22)*
- 50 CANIF_TRCV_E_TRANSCEIVER This error code notifies about an invalid *(page 22)*
- 60 CANIF_TRCV_E_TRCV_NOT_STAND *(page 22)*
- 70 CANIF_TRCV_E_TRCV_NOT_NORMA *(page 22)*
- 80 CANIF_E_INVALID_TXPDUID Not used (see CANIF_E_PARAM_LPDU) *(page 22)*
- 90 CANIF_E_INVALID_RXPDUID Not used (see CANIF_E_PARAM_LPDU) *(page 22)*
- 45 CANIF_E_CONFIG              The error code CANIF_E_CONFIG is used *(page 22)*
- 46 CANIF_E_FATAL               The error code CANIF_E_FATAL is used to *(page 22)*
- 23 / 62 *(page 23)*
- 3.12.2 Production Error Detection *(page 23)*
- Canif_E_Stopped *(page 23)*
- Canif_E_Full_Tx_Buffer *(page 23)*
- Canif_E_Invalid_Dlc *(page 23)*
- 3.13 Transceiver handling *(page 23)*
- 24 / 62 *(page 24)*
- 3.14 Sleep / WakeUp *(page 24)*
- 25 / 62 *(page 25)*
- 26 / 62 *(page 26)*
- Canif_Trcv_Mode_Normal) *(page 26)*
- Canif_Cs_Stopped)    ] *(page 26)*
- Canif Cs Started ) *(page 26)*
- Canif_Cs_Stopped) *(page 26)*
- Canif_Cs_Sleep) *(page 26)*
- Canif_Trcv_Mode_Standby) *(page 26)*
- 27 / 62 *(page 27)*
- 3.15 Bus Off *(page 27)*
- 3.16 Version Info *(page 27)*
- Canif_Ar_Major_Version *(page 27)*
- Canif_Ar_Minor_Version *(page 27)*
- Canif_Ar_Patch_Version *(page 27)*
- Canif_Sw_Major_Version *(page 27)*
- Canif_Sw_Minor_Version *(page 27)*
