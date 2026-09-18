---
title: "TechnicalReference Asr ComM"
description: "Converted from TechnicalReference_Asr_ComM.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_ComM.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (65 pages).

**Pages:** 65

---

This is a **65-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR Communication Manager 
Technical Reference 
 
 
Version 3.14 
 
 
 
 
 
 
 
 
 
 
 
Authors Thomas Petrus 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
2/ 6 5
1 Document Information 
1.1 History 
Author Date Version Remarks 
Thomas Petrus 2008-02-01 3.0 Complete rework and 
adaptation to new template 
Thomas Petrus 2008-02-20 3.1  correct 
ComM_MainFunction() 
description 
 correct and advance ComM 
service port description 
 advance configuration setting 
description 
Thomas Petrus 2008-03-20 3.2  Update Compiler Abstraction 
and Memory Mapping 
Thomas Petrus 2008-03-30 3.3  add description for DEM 
support 
 update file structure 
 remove callback decriptions 
for 
ComM_LinSm_ModeIndicatio
n, 
ComM_CanSm_ModeIndicati
on and 
ComM_FrSm_ModeIndicatio
n 
 add callback description for 
ComM_BusSM_ModeIndicati
on 
 update configuration chapter 
Thomas Petrus 2008-05-08 3.4  update include structure 
 update chapter 5.1.2 
Dynamic Files 
 Add chapter 4.4.2, 4.4.3, 5.4 
and 5.5 
 update configuration 
description 
Thomas Kuhl 2008-08-22 3.5  Update function description of 
ComM_GetCurrentComMode 
 Update function description of 
ComM_BusSM_ModeInidicati
on 
 Update Chapter 8.2. 
Limitations 
 Update Configuration chapter
 Update ComM state diagram 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
3/ 6 5
(ESCAN00029568) 
Thomas Kuhl 2008-10-17 3.6  Update configuration chapter 
 Add API description for 
ComM_Dcm_SetPassiveMod
e 
Thomas Kuhl 2008-12-04 3.7  Remove 
ComM_RTE_ComMModeIndi
cation callback function 
 Update component history 
 Update configuration chapter 
 Update chapter 8 
 Update chapter 4.1 
 Add function description for 
mode indication (6.6.4, 6.6.5) 
 Add chapter 6.7.1.2 
Thomas Kuhl 2009-03-16 3.8  Remove API 
ComM_Dcm_SetEcuPassive
Mode 
 Add Nm Variant OSEK 
Thomas Kuhl 2009-07-14 3.9  Update chapter 5.4 Critical 
cod
e sections 
 Update API descriptions 
inside chapter 6.3, especially 
adaptio
n of API return values 
 Add chapter 8.1.4 ComM 
Servic
e API Return Value 
COMM_UNINIT 
Thomas Kuhl 2009-11-19 3.10  Update chapter 7.1.2 General 
Config
uration 
 Update chapter 5.3 Compiler 
Abstra
ction and Memory 
Mapping 
 Update chapter 5.5 Handling 
of non-volatil
e data 
 Update chapter 6.2 Type 
Definitions
 
Thomas Kuhl 2010-02-15 3.11  Add chapter 6.3.17 
ComM_ConmmunicationCont
rol 
 Add chapter 6.3.18 
ComM_GetNumSendRcvApp
l 
 Add chapter 6.3.19 
ComM_GetOverallBusState 
 Advance chapter 6.7.1.1 
Thomas Kuhl 2010-04-28 3.12  Remove chapter 6.3.17 – 
6.3.19 
 Remove port description of 
ComM_GetNumSendRcvApp
l 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
4/ 6 5
 ESCAN00041031, 
ESCAN00040931 and 
ESCAN00039887 
Thomas Kuhl 2010-08-11 3.13  ESCAN00043830 
 Add description for Ethernet 
support 
Thomas Kuhl 2011-02-10 3.14  Extend description of 
ComM_Init and 
ComM_MainFunction 
 Add description of 
BswM_ComM_CurrentMode 
 ESCAN00045289, 
ESCAN00046463 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_ComM.pdf V2.0.0 
[2] AUTOSAR_SWS_DET.pdf V2.2.0 
[3] AUTOSAR_SWS_DEM.pdf V2.2.0 
[4] AUTOSAR_BasicSoftwareModules.pdf V1.2.0 
[5] AUTOSAR_SWS_DCM.pdf V3.0.0 
[6] AUTOSAR_SWS_CAN_StateManager.pdf V1.0.0 
[7] AUTOSAR_SWS_ECU_Statemanager.pdf V1.2.0 
[8] AUTOSAR_SWS_FlexRay_StateManager.pdf V1.0.0 
[9] AUTOSAR_SWS_LIN_StateManager.pdf V1.0.0 
[10] AUTOSAR_SWS_NMInterface.pdf V1.0.0 
[11] AUTOSAR_SWS_NVRAMManager.pdf V2.2.0 
[12] AN-ISC-8-1118 MICROSAR BSW Compatibility Check V1.0.0 
Table 1-2 Reference documents 
 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
5/ 6 5
1.1 Scope of the Document 
This technical reference describes the gene ral use of the Communication Manager basic 
sof
tware. 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
6/ 6 5
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 4 
1.1 Scope of the Document .................................................................................... 5 
2 Component History....................................................................................................... 11 
3 Introduction ................................................................................................................... 12 
3.1 Architecture Overview..................................................................................... 13 
4 Functional Description ................................................................................................. 14 
4.1 Features.......................................................................................................... 14 
4.2 Initialization ..................................................................................................... 14 
4.3 States.............................................................................................................. 15 
4.4 Main Functions ............................................................................................... 17 
4.4.1 Communication Control Handling ................................................................... 17 
4.4.2 Mode Limitation .............................................................................................. 20 
4.4.3 Synchronous Wake Up ................................................................................... 22 
4.4.4 Mode Indication .............................................................................................. 22 
4.5 Error Handling................................................................................................. 23 
4.5.1 Development Error Reporting ......................................................................... 23 
4.5.1.1 Parameter Checking ....................................................................................... 25 
4.5.2 Production Code Error Reporting ................................................................... 25 
5 Integration ..................................................................................................................... 27 
5.1 Scope of Delivery............................................................................................ 27 
5.1.1 Static Files ...................................................................................................... 27 
5.1.2 Dynamic Files ................................................................................................. 27 
5.2 Include Structure............................................................................................. 28 
5.3 Compiler Abstraction and Memory Mapping................................................... 28 
5.4 Critical code sections...................................................................................... 29 
5.5 Handling of non-volatile data .......................................................................... 30 
6 API Description ............................................................................................................. 31 
6.1 Interfaces Overview ........................................................................................ 31 
6.2 Type Definitions .............................................................................................. 32 
6.3 Services provided by ComM........................................................................... 33 
6.3.1 ComM_InitMemory ......................................................................................... 33 

Technical Reference MICROSAR Communication Manager 
©2011, Vector Informatik GmbH Version: 3.14 
based on template version 3.1 
7/ 6 5
6.3.2 ComM_Init ...................................................................................................... 33 
6.3.3 ComM_GetStatus ........................................................................................... 34 
6.3.4 ComM_GetInhibitionStatus .............................................................................34 
6.3.5 ComM_RequestComMode ............................................................................. 35 
6.3.6 ComM_GetMaxComMode .............................................................................. 35 
6.3.7 ComM_GetRequestedComMode ................................................................... 36 
6.3.8 ComM_GetCurrentComMode......................................................................... 37 
6.3.9 ComM_PreventWakeUp ................................................................................. 37 
6.3.10 ComM_LimitChannelToNoComMode .............................................................38 
6.3.11 ComM_LimitECUToNoComMode ...................................................................38 
6.3.12 ComM_ReadInhibitCounter ............................................................................ 39 
6.3.13 ComM_ResetInhibitCounter ........................................................................... 39 
6.3.14 ComM_SetECUGroupClassification ............................................................... 40 
6.3.15 ComM_GetVersionInfo ................................................................................... 40 
6.3.16 ComM_MainFunction...................................................................................... 41 
6.4 Services used by ComM................................................................................. 41 
6.5 Callback Functions ......................................................................................... 43 
6.5.1 ComM_EcuM_RunModeIndication ................................................................. 43 
6.5.2 ComM_EcuM_WakeUpIndication................................................................... 43 
6.5.3 ComM_BusSM_ModeIndication ..................................................................... 44 
6.5.4 ComM_DCM_ActiveDiagnostic ...................................................................... 44 
6.5.5 ComM_DCM_InactiveDiagnostic.................................................................... 45 
6.5.6 ComM_Nm_NetworkStartIndication................................................................ 45 
6.5.7 ComM_Nm_NetworkMode ............................................................................. 46 
6.5.8 ComM_Nm_PrepareBusSleep........................................................................ 46 
6.5.9 ComM_Nm_BusSleepMode ........................................................................... 47 
6.5.10 ComM_Nm_RestartIndication......................................................................... 47 
6.6 Configurable Interfaces................................................................................... 47 
6.6.1 Dcm_ComM_FullComModeEntered............................................................... 48 
6.6.2 Dcm_ComM_SilentComModeEntered............................................................ 48 
6.6.3 Dcm_ComM_NoComMode

## Extracted outline

- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- (Escan00029568) *(page 3)*
- Comm_Uninit *(page 3)*
-  Escan00041031, *(page 4)*
- Escan00039887 *(page 4)*
-  Escan00045289, *(page 4)*
- Escan00046463 *(page 4)*
- 1.2 Reference Documents *(page 4)*
- 1.1 Scope of the Document *(page 5)*
- 4.4.1 Communication Control Handling ................................................................... 17 *(page 6)*
- 4.5.2 Production Code Error Reporting ................................................................... 25 *(page 6)*
- 5.3 Compiler Abstraction and Memory Mapping................................................... 28 *(page 6)*
- 6.3 Services provided by ComM........................................................................... 33 *(page 6)*
- 6.3.5 ComM_RequestComMode ............................................................................. 35 *(page 7)*
- 6.3.6 ComM_GetMaxComMode .............................................................................. 35 *(page 7)*
- 6.3.7 ComM_GetRequestedComMode ................................................................... 36 *(page 7)*
- 6.3.8 ComM_GetCurrentComMode......................................................................... 37 *(page 7)*
- 6.3.9 ComM_PreventWakeUp ................................................................................. 37 *(page 7)*
- 6.3.10 ComM_LimitChannelToNoComMode .............................................................38 *(page 7)*
- 6.3.11 ComM_LimitECUToNoComMode ...................................................................38 *(page 7)*
- 6.3.14 ComM_SetECUGroupClassification ............................................................... 40 *(page 7)*
- 6.4 Services used by ComM................................................................................. 41 *(page 7)*
- 6.5.1 ComM_EcuM_RunModeIndication ................................................................. 43 *(page 7)*
- 6.5.2 ComM_EcuM_WakeUpIndication................................................................... 43 *(page 7)*
- 6.5.3 ComM_BusSM_ModeIndication ..................................................................... 44 *(page 7)*
- 6.5.4 ComM_DCM_ActiveDiagnostic ...................................................................... 44 *(page 7)*
- 6.5.5 ComM_DCM_InactiveDiagnostic.................................................................... 45 *(page 7)*
- 6.5.6 ComM_Nm_NetworkStartIndication................................................................ 45 *(page 7)*
- 6.5.7 ComM_Nm_NetworkMode ............................................................................. 46 *(page 7)*
- 6.5.8 ComM_Nm_PrepareBusSleep........................................................................ 46 *(page 7)*
- 6.5.9 ComM_Nm_BusSleepMode ........................................................................... 47 *(page 7)*
- 6.5.10 ComM_Nm_RestartIndication......................................................................... 47 *(page 7)*
- 6.6.1 Dcm_ComM_FullComModeEntered............................................................... 48 *(page 7)*
- 6.6.2 Dcm_ComM_SilentComModeEntered............................................................ 48 *(page 7)*
- 6.6.3 Dcm_ComM_NoComModeEntered ................................................................ 49 *(page 7)*
- 6.6.4 Appl_ComM_<CurrentModePortPrefix><UserName>_currentMode.............. 49 *(page 7)*
- 6.6.5 Rte_Switch_<CurrentModePortPrefix><UserName>_currentMode ............... 50 *(page 7)*
- 6.6.6 BswM_ComM_CurrentMode .......................................................................... 51 *(page 7)*
- 7.1.1 Activation of the ComM in GENy .................................................................... 53 *(page 8)*
- 8.1.4 ComM Service API Return Value COMM_UNINIT.......................................... 63 *(page 8)*
- 10 / 65 *(page 10)*
- 11 / 65 *(page 11)*
- 2 Component History *(page 11)*
- 4.00.00 Rework for AUTOSAR Release 3 *(page 11)*
- 4.10.00 ComM_RTE_ComMModeIndication function replaced by ComM user mode *(page 11)*
- 12 / 65 *(page 12)*
- 3 Introduction *(page 12)*
- 13 / 65 *(page 13)*
- 3.1 Architecture Overview *(page 13)*
- Can If Fr If Lin If *(page 13)*
- Li Tp *(page 13)*
- Com Dcmipdu *(page 13)*
- 14 / 65 *(page 14)*
- 4 Functional Description *(page 14)*
- 4.1 Features *(page 14)*
- 4.2 Initialization *(page 14)*
- 15 / 65 *(page 15)*
- 4.3 States *(page 15)*
- Uni Ni T *(page 15)*
- Uninit: *(page 15)*
- 16 / 65 *(page 16)*
- 17 / 65 *(page 17)*
- 4.4 Main Functions *(page 17)*
- 4.4.1 Communication Control Handling *(page 17)*
- 18 / 65 *(page 18)*
- Comm_No_Communication *(page 18)*
- 19 / 65 *(page 19)*
- Comm_Full_Communication, *(page 19)*
- 20 / 65 *(page 20)*
- 4.4.2 Mode Limitation *(page 20)*
- 21 / 65 *(page 21)*
- 22 / 65 *(page 22)*
- 4.4.3 Synchronous Wake Up *(page 22)*
- 4.4.4 Mode Indication *(page 22)*
- 23 / 65 *(page 23)*
- 4.5 Error Handling *(page 23)*
- 4.5.1 Development Error Reporting *(page 23)*
- 24 / 65 *(page 24)*
- Eters *(page 24)*
- V_Service *(page 24)*
- _Modechange *(page 24)*
- 25 / 65 *(page 25)*
- 4.5.1.1 Parameter Checking *(page 25)*
- Comm_E_Not_Inited *(page 25)*
- Comm_E_Wrong_Parameters *(page 25)*
- Comm_E_Error_In_Provided_Service *(page 25)*
- Comm_E_Notsupported_Modechange *(page 25)*
- 4.5.2 Production Code Error Reporting *(page 25)*
- 26 / 65 *(page 26)*
- Comm_E_Net_Start_Ind_Channel_<X> *(page 26)*
- 27 / 65 *(page 27)*
- 5 Integration *(page 27)*
- 5.1 Scope of Delivery *(page 27)*
- 5.1.1 Static Files *(page 27)*
- 5.1.2 Dynamic Files *(page 27)*
- 28 / 65 *(page 28)*
- 5.2 Include Structure *(page 28)*
- 5.3 Compiler Abstraction and Memory Mapping *(page 28)*
- 29 / 65 *(page 29)*
- Comm_Const *(page 29)*
- Comm_Var_Zero_Init *(page 29)*
- Comm_Code *(page 29)*
- Comm_Appl_Var *(page 29)*
- Comm_Var_Noinit_8Bit *(page 29)*
- Comm_Var_Noinit_16Bit *(page 29)*
- Comm_Var_Noinit_Unspecified *(page 29)*
- Comm_Appl_Var_Nvram *(page 29)*
- Comm_Start_Sec_Const_8Bit *(page 29)*
- Comm _Stop_Sec_Const_8Bit *(page 29)*
- Comm_Start_Sec_Const_Unspecified *(page 29)*
- Comm_Stop_Sec_Const_Unspecified *(page 29)*
- Comm_Start_Sec_Code *(page 29)*
- Comm_Stop_Sec_Code *(page 29)*
- Comm_Start_Sec_Var_Noinit_8Bit *(page 29)*
- Comm_Stop_Sec_Var_Noinit_8Bit *(page 29)*
- Comm_Start_Sec_Var_Noinit_16Bit *(page 29)*
- Comm_Stop_Sec_Var_ Noinit_16Bit *(page 29)*
- Comm_Start_Sec_Var_Noinit_Unspecified *(page 29)*
- Comm_Stop_Sec_Var_Noinit_Unspecified *(page 29)*
