---
title: "TechnicalReference Asr CanTp"
description: "Converted from TechnicalReference_Asr_CanTp.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_CanTp.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (73 pages).

**Pages:** 73

---

This is a **73-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR CAN Transport Layer 
Technical Reference 
 
 
 
Version 1.18.01 
 
 
 
 
 
 
 
 
 
 
 
Authors Peter Herrmann 
Status Released 
 
 
 
 

Technical Reference MICROSAR CAN Transport Layer 
©2011, Vector Informatik GmbH Version: 1.18.01 
based on template version 3.9 
2/ 7 3
Document Information 
History 
Author Date Version Remarks 
Peter Herrmann 2006-12-07 1.0 Initial version 
Peter Herrmann 2007-06-19 1.3 Update to AUTOSAR Release 2.1.0 
Peter Herrmann 2008-01-18 1.4 Added database attributes 
Peter Herrmann 2008-01-22 1.5 Added pre-compile macros for Tx 
Confirmation and Rx Indication callbacks 
Peter Herrmann 2008-04-07 1.6 Adaptation to MICROSAR document 
template. 
Peter Herrmann 2008-07-31 1.7 Added description for optimizations: 
- dynamic channel assignment 
(DYN_CHANNEL_ASSIGNMENT), 
- single connection 
(SINGLE_CONN_OPTIMIZED) 
- single connection pre-compile 
(SINGLE_CONN_NOPB_OPTIMIZED) 
- addressing types 
(STANDARD_ADDRESSING, 
EXTENDED_ADDRESSING) 
- partial buffer provision 
(RX/TX_FULL_BUFFER_PROVISION) 
Peter Herrmann 2008-09-16 1.8 Burst transmission 
Peter Herrmann 2008-10-30 1.9 Version number updated 
Peter Herrmann 2008-11-26 1.10 Single connection optimization 
Peter Herrmann 2009-02-20 1.11 MainFunction Rx/Tx split. Additional user 
NSDU-ID (remapping). Additional 
SetSTmin, SetBS API. 
Peter Herrmann 2009-06-10 1.11.82 Conversion to MICROSAR Technical 
Reference. 
Added Multiple Configuration, Cancel 
Transmit Request. 
Peter Herrmann 2009-07-01 1.12.00 Mixed-11 addressing added. 
AUTOSAR Release 4 PduR API callout 
functions added. 
Peter Herrmann 2009-29-09 1.13.00 Corrected chapter 7.2.4 (Timing limitations 
for N_Br
, N_Cs). 
Peter Herrmann 2009-11-04 1.14.00 Added non AUTOSAR Spec. conform 
special feature to avoid all Pre-Pass 
indications to the DEM (see 7.1.9). 
Added special feature to 
accelerate the FF 
routing (see 7.1.10). 

Technical Reference MICROSAR CAN Transport Layer 
©2011, Vector Informatik GmbH Version: 1.18.01 
based on template version 3.9 
3/ 7 3
Peter Herrmann 2010-02-18 1.15.00 Additional AUTOSAR 4.x API: 
“CanTp_ChangeParameterRequest” and 
belonging callout function 
“PduR_CanTpChangeParameterConfirmati
on”. 
Additional Vector specified API 
“CanTp_ReadParameterRequest”. 
Added Callout description for 
“EcuM_GeneratorCompatibilityError”. 
Added description for the mapping of 
critical sections. 
Deleted obsolete 
CanTp_DlcErrorNotification callout function 
from CanIf 
Peter Herrmann 2010-08-13 1.16.00 Additional AUTOSAR 4.x API: 
“CanTp_CancelTransmitRequest” and 
“CanTp_CancelReceiveRequest”. 
Added description of postbuild parameters 
CanTpMaxNum(Rx/Tx)Sdus, 
CanTpMaxNum(Rx/Tx)Channels_PbLimit. 
Peter Herrmann 2010-11-03 1.17.00 Additional description for callout functions 
with possibly disabled interrupts. 
Deleted API function 
PduR_CanTpGetAvailableTxBuffer which 
is obsolete with AR 4.0 
Peter Herrmann 2011-02-25 1.18.00 Added further (AR4 and customer specific) 
extensions 
Peter Herrmann 2011-03-30 1.18.01 After logging and rework 

Technical Reference MICROSAR CAN Transport Layer 
©2011, Vector Informatik GmbH Version: 1.18.01 
based on template version 3.9 
4/ 7 3
Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_CANTransportLayer.pdf 3.0.0 
[2] AUTOSAR_SWS_CANInterface.pdf 4.0.0 
[3] AUTOSAR_SWS_PDURouter.pdf 3.0.0 
[4] /ISO/TF2/: ISO FDIS 15765-2; Road vehicles — Diagnostics on CAN — 
Part 2: Network layer services 
2009-09-06 
[5] AUTOSAR_SWS_DiagnosticEventManager.pdf 4.0.0 
[6] AUTOSAR_SWS_DevelopmentErrorTracer.pdf 3.0.0 
[7] AUTOSAR_SRS_BSWGeneral.pdf 3.0.0 
[8] AUTOSAR_TR_BSWModuleList.pdf 1.4.0 
[9] Application Note AN-ISC-8-1118 – MICROSAR BSW Compatibility 
Check 
 
[10] AUTOSAR_SWS_CAN_TP.pdf 2.3.0 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference MICROSAR CAN Transport Layer 
©2011, Vector Informatik GmbH Version: 1.18.01 
based on template version 3.9 
5/ 7 3
Contents 
1 Component History.......................................................................................................... 9 
2 Introduction ...................................................................................................................... 9 
2.1 Architecture Overview..................................................................................... 10 
2.2 CAN Transport Layer interactions....................................................................11 
2.2.1 Changes between AUTOSAR 3.x and AUTOSAR 4....................................... 12 
2.2.1.1 PduR API changes.......................................................................................... 12 
2.2.1.2 CanIf API changes ..........................................................................................13 
3 Functional Description .................................................................................................. 14 
3.1 Features.......................................................................................................... 14 
3.2 Initialization ..................................................................................................... 14 
3.3 States.............................................................................................................. 15 
3.4 Main Functions ............................................................................................... 16 
3.4.1 The CanTp_MainFunction .............................................................................. 16 
3.4.2 Buffer handling and data consistency............................................................. 16 
3.4.2.1 Critical sections............................................................................................... 17 
3.5 Error Handling................................................................................................. 18 
3.5.1 Development Error Reporting ......................................................................... 18 
3.5.2 Production Code Error Reporting ................................................................... 19 
4 Integration....................................................................................................................... 20 
4.1 Scope of Delivery............................................................................................ 20 
4.1.1 Static Files ...................................................................................................... 20 
4.1.1.1 Hook functions ................................................................................................ 20 
4.1.2 21 
4.1.3 Dynamic Files ................................................................................................. 21 
4.2 Include Structure............................................................................................. 21 
4.3 Compiler Abstraction and Memory Mapping................................................... 22 
5 API Description .............................................................................................................. 23 
5.1 Services provided by CANTP ......................................................................... 23 
5.1.1 CanTp_Init: (until AR 3) ................................................................................. 23 
5.1.2 CanTp_Init: with ConfigPointer (Vector extension to AR 3) ...........................24 
5.1.3 CanTp_Init: (since AR 4)................................................................................ 25 
5.1.4 CanTp_GetVersionInfo ................................................................................... 26 
5.1.5 CanTp_Shutdown ........................................................................................... 27 
5.1.6 CanTp_Transmit ............................................................................................. 28 

Technical Reference MICROSAR CAN Transport Layer 
©2011, Vector Informatik GmbH Version: 1.18.01 
based on template version 3.9 
6/ 7 3
5.1.7 CanTp_CancelTransmitRequest..................................................................... 30 
5.1.8 CanTp_CancelReceiveRequest ..................................................................... 31 
5.1.9 CanTp_MainFunction ..................................................................................... 32 
5.1.10 CanTp_MainFunctionRx ................................................................................. 33 
5.1.11 CanTp_MainFunctionTx ................................................................................. 33 
5.1.12 CanTp_SetSTmin ........................................................................................... 34 
5.1.13 CanTp_SetBS................................................................................................. 35 
5.1.14 CanTp_ChangeParameterRequest ................................................................ 36 
5.1.15 CanTp_ReadParameterRequest .................................................................... 37 
5.2 Services used by CANTP ............................................................................... 38 
5.3 Callback Functions ......................................................................................... 39 
5.3.1 CanTp_RxIndication ....................................................................................... 39 
5.3.2 CanTp_TxConfirmation................................................................................... 40 
5.4 Configurable Interfaces................................................................................... 41 
5.4.1 Notifications .................................................................................................... 41 
5.4.2 Callout Functions ............................................................................................ 42 
5.4.2.1 PduR_CanTpRxIndication .............................................................................. 42 
5.4.2.2 PduR_CanTpTxConfirmation.......................................................................... 43 
5.4.3 Callout Functions (until AUTOSAR Release 3)............................................... 45 
5.4.3.1 PduR_CanTpProvideRxBuffer (until AUTOSAR Release 3)..................... 45 
5.4.3.2 PduR_CanTpProvideTxBuffer (until AUTOSAR Release 3) .....................46 
5.4.4 Callout Functions (since AUTOSAR Release 4)............................................. 48 
5.4.4.1 PduR_CanTpStartOfReception (since AUTOSAR Release 4)........................ 48 
5.4.4.2 PduR_CanTpCopyRxData (since AUTOSAR Release 4)............................... 49 
5.4.4.3 PduR_CanTpCopyTxData (since AUTOSAR Release 4) ...............................50 
5.4.4.4 PduR_CanTpChangeParameterConfirmation ................................................ 51 
5.4.4.5 EcuM_GeneratorCompatibilityError................................................................ 52 
6 Configuration.................................................................................................................. 53 
6.1 Configuration in Data Base............................................................................. 53 
6.2 Configuration with GENy ................................................................................ 54 
6.2.1 Component Configuration............................................................................... 55 
6.2.1.1 General Parameters ....................................................................................... 55 
6.2.2 Channel Configuration .................................................................................... 59 
6.2.2.1 Rx Parameters...................................................................

## Extracted outline

- (Dyn_Channel_Assignment), *(page 2)*
- (Single_Conn_Optimized) *(page 2)*
- (Single_Conn_Nopb_Optimized) *(page 2)*
- (Standard_Addressing, *(page 2)*
- Extended_Addressing) *(page 2)*
- (Rx/Tx_Full_Buffer_Provision) *(page 2)*
- 2.2 CAN Transport Layer interactions....................................................................11 *(page 5)*
- 2.2.1 Changes between AUTOSAR 3.x and AUTOSAR 4....................................... 12 *(page 5)*
- 3.4.2 Buffer handling and data consistency............................................................. 16 *(page 5)*
- 3.5.2 Production Code Error Reporting ................................................................... 19 *(page 5)*
- 4.1.2 21 *(page 5)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 22 *(page 5)*
- 5.1 Services provided by CANTP ......................................................................... 23 *(page 5)*
- 5.1.2 CanTp_Init: with ConfigPointer  (Vector extension to AR 3) ...........................24 *(page 5)*
- 5.1.7 CanTp_CancelTransmitRequest..................................................................... 30 *(page 6)*
- 5.1.8 CanTp_CancelReceiveRequest ..................................................................... 31 *(page 6)*
- 5.1.14 CanTp_ChangeParameterRequest ................................................................ 36 *(page 6)*
- 5.1.15 CanTp_ReadParameterRequest .................................................................... 37 *(page 6)*
- 5.2 Services used by CANTP ............................................................................... 38 *(page 6)*
- 5.4.2.2 PduR_CanTpTxConfirmation.......................................................................... 43 *(page 6)*
- 5.4.3 Callout Functions (until AUTOSAR Release 3)............................................... 45 *(page 6)*
- 5.4.3.1 PduR_CanTpProvideRxBuffer       (until AUTOSAR Release 3)..................... 45 *(page 6)*
- 5.4.3.2 PduR_CanTpProvideTxBuffer       (until AUTOSAR Release 3) .....................46 *(page 6)*
- 5.4.4 Callout Functions (since AUTOSAR Release 4)............................................. 48 *(page 6)*
- 5.4.4.1 PduR_CanTpStartOfReception (since AUTOSAR Release 4)........................ 48 *(page 6)*
- 5.4.4.2 PduR_CanTpCopyRxData (since AUTOSAR Release 4)............................... 49 *(page 6)*
- 5.4.4.3 PduR_CanTpCopyTxData (since AUTOSAR Release 4) ...............................50 *(page 6)*
- 5.4.4.4 PduR_CanTpChangeParameterConfirmation ................................................ 51 *(page 6)*
- 5.4.4.5 EcuM_GeneratorCompatibilityError................................................................ 52 *(page 6)*
- 7.1.1 Dynamically supported connection channels.................................................. 63 *(page 7)*
- 7.1.5.1 CANTP initialization since AUTOSAR 4.......................................................... 64 *(page 7)*
- 7.1.7 Splitted CanTp_MainFunction......................................................................... 64 *(page 7)*
- 7.1.8 Dynamic Flow Control content........................................................................ 64 *(page 7)*
- 7.1.9 Suppress PRE_PASSED DEM events ........................................................... 64 *(page 7)*
- 7.1.10 Accelerate the routing of multi frames ............................................................ 65 *(page 7)*
- 7.1.11 Optimized ROM resource consumption.......................................................... 65 *(page 7)*
- 7.1.12 Detection of competing diagnostic tester access............................................ 65 *(page 7)*
- 7.1.14 Reception of Flow Control and Consecutive frames....................................... 66 *(page 7)*
- 7.1.14.1 Ignore FC frames with a reserved STmin content .......................................... 66 *(page 7)*
- 7.1.14.2 Ignore FC frames with a Flow Status not equal to FC.CTS or FC.WAIT ........66 *(page 7)*
- 7.1.14.3 Ignore Consecutive Frames (CF) with a wrong sequence Number (SN)........ 66 *(page 7)*
- 7.1.15 DEM to DET reporting is configurable ............................................................ 67 *(page 7)*
- 7.1.15.1 DEM event CANTP_E_(RX_/TX_)COM(M).................................................... 67 *(page 7)*
- 7.1.15.2 DEM event CANTP_E_OPER_NOT_SUPPORTED ...................................... 67 *(page 7)*
- 7.2.4 Runtime optimization for Timing Calculation................................................... 67 *(page 7)*
- 1 Component History *(page 9)*
- 2 Introduction *(page 9)*
- 10 / 73 *(page 10)*
- 2.1 Architecture Overview *(page 10)*
- 11 / 73 *(page 11)*
- 2.2 CAN Transport Layer interactions *(page 11)*
- 12 / 73 *(page 12)*
- 2.2.1 Changes between AUTOSAR 3.x and AUTOSAR 4 *(page 12)*
- 2.2.1.1 PduR API changes *(page 12)*
- 13 / 73 *(page 13)*
- 2.2.1.2 CanIf API changes *(page 13)*
- 14 / 73 *(page 14)*
- 3 Functional Description *(page 14)*
- 3.1 Features *(page 14)*
- 3.2 Initialization *(page 14)*
- 15 / 73 *(page 15)*
- 3.3 States *(page 15)*
- 16 / 73 *(page 16)*
- 3.4 Main Functions *(page 16)*
- 3.4.1 The CanTp_MainFunction *(page 16)*
- 3.4.2 Buffer handling and data consistency *(page 16)*
- 17 / 73 *(page 17)*
- 3.4.2.1 Critical sections *(page 17)*
- 18 / 73 *(page 18)*
- 3.5 Error Handling *(page 18)*
- 3.5.1 Development Error Reporting *(page 18)*
- 19 / 73 *(page 19)*
- 3.5.2 Production Code Error Reporting *(page 19)*
- Cantp_E_Com *(page 19)*
- 20 / 73 *(page 20)*
- 4 Integration *(page 20)*
- 4.1 Scope of Delivery *(page 20)*
- 4.1.1 Static Files *(page 20)*
- Autosar). *(page 20)*
- 4.1.1.1 Hook functions *(page 20)*
- 21 / 73 *(page 21)*
- 4.1.3 Dynamic Files *(page 21)*
- 4.2 Include Structure *(page 21)*
- 22 / 73 *(page 22)*
- 4.3 Compiler Abstraction and Memory Mapping *(page 22)*
- Cantp_Const *(page 22)*
- Cantp_Pbcfg *(page 22)*
- Cantp_Code *(page 22)*
- Cantp_Appl_Code *(page 22)*
- Cantp_Appl_Data *(page 22)*
- Cantp_Var_Noinit *(page 22)*
- Cantp_Var *(page 22)*
- Cantp_Start_Sec_Code *(page 22)*
- Cantp_Stop_Sec_Code *(page 22)*
- Cantp_Start_Sec_Var_Noinit_Unspecified *(page 22)*
- Cantp_Start_Sec_Const_16Bit *(page 22)*
- Cantp_Stop_Sec_Const_16Bit *(page 22)*
- Cantp_Start_Sec_Const_32Bit *(page 22)*
- Cantp_Stop_Sec_Const_32Bit *(page 22)*
- Cantp_Start_Sec_Const_Pbcfg_Root *(page 22)*
- Cantp_Start_Sec_Pbcfg_Root *(page 22)*
- Cantp_Start_Sec_Var_Noinit_8Bit *(page 22)*
- 23 / 73 *(page 23)*
- 5 API Description *(page 23)*
- 5.1 Services provided by CANTP *(page 23)*
- 5.1.1 CanTp_Init:  (until AR 3) *(page 23)*
- 24 / 73 *(page 24)*
- 5.1.2 CanTp_Init: with ConfigPointer  (Vector extension to AR 3) *(page 24)*
- 25 / 73 *(page 25)*
- 5.1.3 CanTp_Init:  (since AR 4) *(page 25)*
- 26 / 73 *(page 26)*
- 5.1.4 CanTp_GetVersionInfo *(page 26)*
- 27 / 73 *(page 27)*
- 5.1.5 CanTp_Shutdown *(page 27)*
- 28 / 73 *(page 28)*
- 5.1.6 CanTp_Transmit *(page 28)*
- 29 / 73 *(page 29)*
- 30 / 73 *(page 30)*
- 5.1.7 CanTp_CancelTransmitRequest *(page 30)*
- 31 / 73 *(page 31)*
