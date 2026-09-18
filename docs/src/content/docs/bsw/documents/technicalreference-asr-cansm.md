---
title: "TechnicalReference Asr CanSM"
description: "Converted from TechnicalReference_Asr_CanSM.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanSM.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (51 pages).

**Pages:** 51

---

This is a **51-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR CAN State Manager 
Technical Reference 
 
 
Version 1.16 
 
 
 
 
 
 
 
 
 
 
 
 
 
Authors Mark A. Fingerle 
Status Released 
 

Technical Reference MICROSAR CAN State Manager 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Mark A. Fingerle 2008-02-04 1.0 ASR 3.0 beta release 
Mark A. Fingerle 2008-02-27 1.1 Switch to new template 
Mark A. Fingerle 2008-03-31 1.2 ESCAN00025504 Rename Technical Reference to 
MSR Short Name 
ESCAN00025710 Adapt initialization. 
ESCAN00025711 Adapt Chapter Configuration 
GENy to ASR names 
Mark A. Fingerle 2008-05-06 1.3 ESCAN00025892 Simplify the set controller mode 
algorithm of the CanSM 
ESCAN00026001 Extend error handling to the case 
a transition fails and the mode request changes 
before recovering of the transition. 
Mark A. Fingerle 2008-07-18 1.4 Allowed timer values 
IPDU via drop down list 
critical section kinds 
Mark A. Fingerle 2008-10-08 1.5 New feature/API ECU passive mode 
CAN bus specific bus-off configuration parameter 
Mark A. Fingerle 2008-10-28 1.6 State machine start/entry point 
Additional explanation of passive mode 
Additional explanation of error counter 
Figure 4-1 updated 
GENy screen shots updated 
Mark A. Fingerle 2009-02-18 1.7 add API CanSM_PreventBusSleepAtStartUp 
advance chapter 4.2 Initialization 
Mark A. Fingerle 2009-03-23 1.8 Adapt configuration of the transceiver handling 
Mark A. Fingerle 2009-05-13 1.9 Correct Figure 6-1 CanSM interactions with other 
BSW 
4.3.1 “Transition Check” in case set transceiver 
mode fail 
Add Error code CANSM_E_SETTRANSCEIVERMODE in 
Table 4-6 
Add application bus-off notification functions 4.3.2, 
6.5.2, 6.5.2 
Mark A. Fingerle 2009-10-13 1.10 ESCAN00037731 Ambiguous description of critical 
sections in chapter 5.5 
GENy feature Disable Pdu Group and BusOff Notification 
©2011, Vector Informatik GmbH Version: 1.16 
based on template version 3.1 
2/ 5 1

Technical Reference MICROSAR CAN State Manager 
7.1.5 
Mark A. Fingerle 2010-01-13 1.10.01 Correct chapter 7.1.3, EcuM Î SchM 
Mark A. Fingerle 2010-03-03 1.11 Update 5.5 critical sections 
Mark A. Fingerle 2010-04-23 1.12 ESCAN00040930 Add API 
EcuM_GeneratorCompatibilityError Table 6-11, 
Figure 6-1 
ESCAN00037126 Better the Onscreen Help of the 
"Bor Counter L2 Err Ch" Table 7-4 
ESCAN00041444 re-initialization of signals when 
switching from NO to FULL communication in 
chapter 7.1.5 
Mark A. Fingerle 2010-08-13 1.13 ESCAN00043552 Add support for XCP shutdown 
chapter 4.4 
Mark A. Fingerle 2010-10-03 1.14 ESCAN00045704 Disable DeadlineMonitoring in 
state CANSM_SILENT_COMMUNICATION. Add 
DM description to the states in chapter 4.3.1. 
ESCAN00045482 Wrong configuration class for 
AUTOSAR parameter: CanSM Post Build Config 
Start Address Table 7-1 
Mark A. Fingerle 2011-01-23 1.15 R11: During the BusOff recovery the Nm may 
trigger the shutdown NmTimeOut 4.3.2 
BusOffEnd missing if NoCom is triggered 4.3.2 
Partial Networks 8.1.10 
BswM ComMode Indication 8.1.11 
Multiple identity 8.1.12 
Usage CANSM_EXCLUSIVE_AREA_4 
Mark A. Fingerle 2011-04-23 1.16 R12: ESCAN00049972 Add MSR Dem errors to 
deviation chapter 8.1.13 
ESCAN00047985 No CAN communication 
possible, caused by bus-off in SILENT 
communication 8.1.14 
ESCAN00050250 Extend Bus Off recovery 
handling, additional ModeIndications during BusOff 
recovery 4.3.2 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR Specification of CAN State Manager 1.0.0 
[2] AUTOSAR Specification of Development Error Tracer 2.2.0 
[3] AUTOSAR Specification of Diagnostics Event Manager 2.2.1 
[4] AUTOSAR List of Basic Software Modules 1.2.0 
[5] AUTOSAR Specification of CAN Interface 2.1.0 
©2011, Vector Informatik GmbH Version: 1.16 
based on template version 3.1 
3/ 5 1

Technical Reference MICROSAR CAN State Manager 
[6] AUTOSAR Specification of Communication Manager 2.0.0 
[7] AN-ISC-8-1093 1.0.0 
[8] AN-ISC-8-1118 MICROSAR BSW Compatibility Check 1.0.0 
Table 1-2 Reference documents 
1.3 Scope of the Document 
This technical reference describes the gener al use of the CAN State Manager basis 
software. All aspects which are CAN controlle r specific are described in a separate 
document [5], which is also part of the delivery. 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
©2011, Vector Informatik GmbH Version: 1.16 
based on template version 3.1 
4/ 5 1

Technical Reference MICROSAR CAN State Manager 
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 3 
1.3 Scope of the Document .................................................................................... 4 
2 Component History....................................................................................................... 11 
3 Introduction ................................................................................................................... 12 
3.1 Architecture Overview..................................................................................... 12 
4 Functional Description ................................................................................................. 14 
4.1 Features.......................................................................................................... 14 
4.2 Initialization ..................................................................................................... 14 
4.3 State Machines ............................................................................................... 15 
4.3.1 Network Mode State Machine......................................................................... 15 
4.3.2 Bus-off Recovery State Machine..................................................................... 18 
4.4 XCP notification function................................................................................. 20 
4.5 ECU passive mode ......................................................................................... 21 
4.6 Main Function ................................................................................................. 21 
4.7 Communication Modes ................................................................................... 21 
4.8 Communication Mode Polling ......................................................................... 21 
4.9 Error Handling................................................................................................. 21 
4.9.1 Development Error Reporting ......................................................................... 21 
4.9.1.1 Parameter Checking ....................................................................................... 22 
4.9.2 Production Code Error Reporting ................................................................... 23 
5 Integration .....................................................................................................................2 4 
5.1 Brief Instruction............................................................................................... 24 
5.2 Scope of Delivery............................................................................................ 24 
5.2.1 Static Files ...................................................................................................... 24 
5.2.2 Dynamic Files ................................................................................................. 25 
5.3 Include Structure............................................................................................. 25 
5.4 Compiler Abstraction and Memory Mapping................................................... 26 
5.5 Critical Areas................................................................................................... 26 
6 API Description ............................................................................................................. 28 
6.1 Interfaces Overview ........................................................................................ 28 
6.2 Type Definitions .............................................................................................. 28 
©2011, Vector Informatik GmbH Version: 1.16 
based on template version 3.1 
5/ 5 1

Technical Reference MICROSAR CAN State Manager 
6.3 Services Provided by CanSM ......................................................................... 29 
6.3.1 CanSM_InitMemory ........................................................................................ 30 
6.3.2 CanSM_Init ..................................................................................................... 30 
6.3.3 CanSM_MainFunction .................................................................................... 31 
6.3.4 CanSM_RequestComMode............................................................................ 31 
6.3.5 CanSM_SetEcuPassive.................................................................................. 32 
6.3.6 CanSM_GetCurrentComMode ....................................................................... 32 
6.3.7 CanSM_GetVersionInfo .................................................................................. 32 
6.3.8 CanSM_PreventBusSleepAtStartUp............................................................... 33 
6.4 Services used by CanSM ............................................................................... 33 
6.5 Callback Functions ......................................................................................... 34 
6.5.1 CanSM_ControllerBusOff ............................................................................... 34 
6.5.2 Appl_CanSM_BusOffBegin............................................................................. 34 
6.5.3 Appl_CanSM_BusOffEnd ............................................................................... 35 
7 Configuration ................................................................................................................ 36 
7.1 Configuration with GENy ................................................................................ 36 
7.1.1.1 Basic ............................................................................................................... 36 
7.1.2 Activation of the CAN State Manager ............................................................. 37 
7.1.3 General Settings ............................................................................................. 38 
7.1.4 Network Settings............................................................................................. 41 
7.1.5 General CAN Channel Specific Settings......................................................... 41 
7.1.6 Bus-off Recovery State Machine Configuration .............................................. 43 
7.1.7 Values from other BSW Modules.................................................................... 45 
8 AUTOSAR Standard Compliance................................................................................. 47 
8.1 Additions / Extensions .................................................................................... 47 
8.1.1 Additional Error Handling in the Network Mode State Machine ...................... 47 
8.1.2 API CanSM_InitMemory()............................................................................... 47 
8.1.3 Error Code ...................................................................................................... 47 

## Extracted outline

- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 4.3.1 “Transition Check” in case set transceiver *(page 2)*
- 1.2 Reference Documents *(page 3)*
- [7]  An-Isc-8-1093 1.0.0 *(page 4)*
- 1.3 Scope of the Document *(page 4)*
- 4.3.1 Network Mode State Machine......................................................................... 15 *(page 5)*
- 4.3.2 Bus-off Recovery State Machine..................................................................... 18 *(page 5)*
- 4.8 Communication Mode Polling ......................................................................... 21 *(page 5)*
- 4.9.2 Production Code Error Reporting ................................................................... 23 *(page 5)*
- 5.4 Compiler Abstraction and Memory Mapping................................................... 26 *(page 5)*
- 6.3 Services Provided by CanSM ......................................................................... 29 *(page 6)*
- 6.3.4 CanSM_RequestComMode............................................................................ 31 *(page 6)*
- 6.3.6 CanSM_GetCurrentComMode ....................................................................... 32 *(page 6)*
- 6.3.8 CanSM_PreventBusSleepAtStartUp............................................................... 33 *(page 6)*
- 6.4 Services used by CanSM ............................................................................... 33 *(page 6)*
- 6.5.2 Appl_CanSM_BusOffBegin............................................................................. 34 *(page 6)*
- 6.5.3 Appl_CanSM_BusOffEnd ............................................................................... 35 *(page 6)*
- 7.1.2 Activation of the CAN State Manager ............................................................. 37 *(page 6)*
- 7.1.5 General CAN Channel Specific Settings......................................................... 41 *(page 6)*
- 7.1.6 Bus-off Recovery State Machine Configuration .............................................. 43 *(page 6)*
- 7.1.7 Values from other BSW Modules.................................................................... 45 *(page 6)*
- 8.1.1 Additional Error Handling in the Network Mode State Machine ...................... 47 *(page 6)*
- 8.1.5 API CanSM_PreventBusSleepAtStartUp()...................................................... 47 *(page 6)*
- 8.1.9 No mode notification during CanSM_Init ........................................................ 48 *(page 6)*
- 8.1.13 Additional bus-off recovery in state silent ....................................................... 48 *(page 6)*
- 10 / 51 *(page 10)*
- 2 Component History *(page 11)*
- 11 / 51 *(page 11)*
- 3 Introduction *(page 12)*
- 3.1 Architecture Overview *(page 12)*
- 12 / 51 *(page 12)*
- Can Sm *(page 13)*
- Can If *(page 13)*
- 13 / 51 *(page 13)*
- 4 Functional Description *(page 14)*
- 4.1 Features *(page 14)*
- 4.2 Initialization *(page 14)*
- 14 / 51 *(page 14)*
- 4.3 State Machines *(page 15)*
- 4.3.1 Network Mode State Machine *(page 15)*
- 15 / 51 *(page 15)*
- Cansm_Full_Communication *(page 16)*
- Cansm_No_Communication *(page 16)*
- Cansm_Silent_Communication *(page 16)*
- [T01_Ok] *(page 16)*
- [T02_Ok] *(page 16)*
- [T03_Ok] *(page 16)*
- 16 / 51 *(page 16)*
- 17 / 51 *(page 17)*
- 4.3.2 Bus-off Recovery State Machine *(page 18)*
- 18 / 51 *(page 18)*
- Cansm_Bor_Idle *(page 19)*
- Cansm_Bor_Check_Init *(page 19)*
- Cansm_Bor_No_Bus_Off *(page 19)*
- Cansm_Bor_Txoff_L1, Cansm_Bor_Txoff_L2 *(page 19)*
- Cansm_Bor_Check_L1, Cansm_Bor_Check_L2 *(page 19)*
- 19 / 51 *(page 19)*
- 4.4 XCP notification function *(page 20)*
- 20 / 51 *(page 20)*
- 4.5 ECU passive mode *(page 21)*
- 4.6 Main Function *(page 21)*
- 4.7 Communication Modes *(page 21)*
- 4.8 Communication Mode Polling *(page 21)*
- 4.9 Error Handling *(page 21)*
- 4.9.1 Development Error Reporting *(page 21)*
- Std_On. *(page 21)*
- 21 / 51 *(page 21)*
- Work_Handle *(page 22)*
- Work_Mode *(page 22)*
- Oller *(page 22)*
- 4.9.1.1 Parameter Checking *(page 22)*
- 22 / 51 *(page 22)*
- 23 / 51 *(page 23)*
- Cansm_Dev_Error_Detect. *(page 23)*
- 4.9.2 Production Code Error Reporting *(page 23)*
- Cansm_E_Busoff_Network_< *(page 23)*
- Cansm_E_Mode_Change_Netw *(page 23)*
- Ork_<X> *(page 23)*
- Cansm_E_Settransceivermode_ *(page 23)*
- Network_<X> *(page 23)*
- 5 Integration *(page 24)*
- 5.1 Brief Instruction *(page 24)*
- 5.2 Scope of Delivery *(page 24)*
- 5.2.1 Static Files *(page 24)*
- 24 / 51 *(page 24)*
- 25 / 51 *(page 25)*
- 5.2.2 Dynamic Files *(page 25)*
- 5.3 Include Structure *(page 25)*
- 5.4 Compiler Abstraction and Memory Mapping *(page 26)*
- Cansm_Var_Noinit *(page 26)*
- Cansm_Var_Zero_Init *(page 26)*
- Cansm_Const *(page 26)*
- Cansm_Pbcfg *(page 26)*
- Cansm_Code *(page 26)*
- Cansm_Start_Sec_Var_Noinit_Unspecified *(page 26)*
- Cansm_Stop_Sec_Var_Noinit_Unspecified *(page 26)*
- Cansm_Start_Sec_Var_Zero_Init_8Bit *(page 26)*
- Cansm_Stop_Sec_Var_Zero_Init_8Bit *(page 26)*
- Cansm_Start_Sec_Var_Noinit_8Bit *(page 26)*
- Cansm_Stop_Sec_Var_Noinit_8Bit *(page 26)*
- Cansm_Start_Sec_Const_8Bit *(page 26)*
- Cansm_Stop_Sec_Const_8Bit *(page 26)*
- Cansm_Start_Sec_Const_32Bit *(page 26)*
- Cansm_Stop_Sec_Const_32Bit *(page 26)*
- Cansm_Start_Sec_Const_Unspecified *(page 26)*
- Cansm_Stop_Sec_Const_Unspecified *(page 26)*
- Cansm_Start_Sec_Pbcfg *(page 26)*
- Cansm_Stop_Sec_Pbcfg *(page 26)*
- Cansm_Start_Sec_Code *(page 26)*
- Cansm_Stop_Sec_Code *(page 26)*
- 5.5 Critical Areas *(page 26)*
- 26 / 51 *(page 26)*
- 27 / 51 *(page 27)*
- 28 / 51 *(page 28)*
- 6 API Description *(page 28)*
- 6.1 Interfaces Overview *(page 28)*
- 6.2 Type Definitions *(page 28)*
- Cansm_Uninited *(page 28)*
- 29 / 51 *(page 29)*
