---
title: "TechnicalReference Asr PduR"
description: "Converted from TechnicalReference_Asr_PduR.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_PduR.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (106 pages).

**Pages:** 106

---

This is a **106-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR PDU Router 
Technical Reference 
 
 
Version 3.10.02 
 
 
 
 
 
 
 
 
 
 
 
Authors Hartmut Hörner, Hannes Haas, Erich Schondelmaier, 
Gunnar Meiss 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR PDU Router 
2012, Vector Informatik GmbH Version: 3.10.02 
based on template version 4.6 
2 / 106 
Document Information 
History 
Author Date Version Remarks 
Hartmut Hörner 2006-02-01 0.1 Initial version 
Hartmut Hörner 2006-03-13 0.2 Pre-compile variants added in chapter 3.6 
Configuration Phases 
Hartmut Hörner 2006-03-17 0.3 Added chapter with required API functions 
Hannes Haas 2006-06-14 2.0 Adapted to AUTOSAR version 2.0 
Hannes Haas 2006-07-30 2.1 Added LIN IF support 
Hannes Haas 2006-11-22 2.2 Added CAN TP support 
Added Post-Build support 
Hannes Haas 2007-04-26 2.3 New Template 
Simplified post-build configuration procedure 
Revision of all chapters 
Hannes Haas 2007-11-20 2.4 Removed non-selectable post-build configuration 
Added Interface Gateway with Callouts 
Hannes Haas 2008-01-08 2.5 Added TP Gateway and memory allocation 
Added Glossary 
Adapted to AUTOSAR 3 
Added include structure 
Added J1939TP support 
Hannes Haas 2008-03-26 3.0 Corrected return values of callout functions 
ESCAN00024680: described PDU handle concept 
Updated to SWS version 2.2.1 
TP Gateway Ring-Buffer support 
ESCAN00025586: changed file and GENy module 
name 
Hannes Haas 2008-05-16 3.1 Minor improvements in all chapters 
GENy GUI update 
Added generator version check 
Hannes Haas 2008-06-26 3.2 Minor improvements in all chapters 
Adaptations to new GUI 
Hannes Haas 2008-09-25 3.3 ESCAN00028028: Memory mapping limitations 
Object Explorer 
Added CRC check for configuration data 
ESCAN00029973: Adapted GUI according to 
AUTOSAR short names 
Hannes Haas 2008-11-19 3.4 Intra ECU Communication 
Erich Schondelmaier 2008-03-26 3.5 Added IpduM support 

Technical Reference MICROSAR PDU Router 
2012, Vector Informatik GmbH Version: 3.10.02 
based on template version 4.6 
3 / 106 
Hannes Haas 2009-08-03 3.6 TP Layer Routing using AUTOSAR 4.0 API 
Gunnar Meiss 2009-08-30 3.6 Timeout in Intra ECU Communication 
 2009-08-12 3.6 Added LIN TP support 
Added MOST IF support 
Added MOST TP support 
Gunnar Meiss 2009-10-12 3.7 Added SoAd support 
Added Dobt support 
Erich Schondelmaier 2010-01-08 3.8 Added Nm support 
Added Service Ids 
Erich Schondelmaier 2010-03-30 3.9 Updated 6.2.4 TP Buffers 
Erich Schondelmaier 2010-04-29 Renamed J1939 to J1939Tp 
Added 3.14 AUTOSAR 4.0 CAN TP API 
Added 3.13 AUTOSAR 3.0 TP API with ISO timing 
optimization 
Gunnar Meiss 2010-08-23 Updated to new Template 
Added PduR_EnableRouting and 
PduR_DisableRouting 
Added PduR_<UpTp>CancelReceiveRequest 
Added PduR_<UpTp>CancelTransmitRequest 
Added PduR_<UpTp>ChangeParameterRequest 
for CanTp and FrTp 
Added PduR_<UpTp>ReadParameterRequest 
Added chapter 6.5 Configuration in EcuC Data 
Base 
Erich Schondelmaier 2010-09-23 Added new BSWMD Parameter 
Change Functional Description of PduR_Init 
Updated AUTOSAR 3.0 TP API with ISO timing 
optimization 
Gunnar Meiss 2010-10-19 3.10.00 Added Rx for CanNm and FrNm 
Erich Schondelmaier 2010-12-20 Added description for Balance Routing time of 
Physical TP Routings 
Added chapter Tp error handling 
Updated API descriptions 
Gunnar Meiss 2011-02-18 Added Cdd 
Added Dynamic DLC Routing 
Gunnar Meiss 2012-08-10 3.10.01 AR3-2457: Dynamic DLC with TriggerTransmit 
based Communication Interfaces 
Added partial deviation of PDUR350 (Can), 
PDUR372 (Fr), PDUR394 (LIN) 
Erich Schondelmaier 2012-10-31 3.10.02 Added decription of ESCAN00062517 

Technical Reference MICROSAR PDU Router 
2012, Vector Informatik GmbH Version: 3.10.02 
based on template version 4.6 
4 / 106 
 
Reference Documents 
No. Source Title Version 
[1] AUTOSAR AUTOSAR_PDU_Router.pdf 2.2.1 
[2] AUTOSAR AUTOSAR_SWS_DET.pdf 2.2.0 
[3] AUTOSAR AUTOSAR_SWS_DEM.pdf 2.2.1 
[4] AUTOSAR AUTOSAR_BasicSoftwareModules.pdf 1.3.0 
[5] AUTOSAR AUTOSAR_SRS_Gateway.pdf 2.0.3 
[6] AUTOSAR AUTOSAR_SWS_PDU_Router.doc 3.8.1 
(draft) 
[7] Vector Technical Reference Post-Build Tool Chain 
 
 
 
 
 
 
 
Caution 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
 
 

Technical Reference MICROSAR PDU Router 
2012, Vector Informatik GmbH Version: 3.10.02 
based on template version 4.6 
5 / 106 
Contents 
1 Component History ................................ ................................ ................................ ...... 12 
2 Introduction ................................ ................................ ................................ .................. 14 
2.1 Architecture Overview ................................ ................................ ................... 15 
3 Functional Description ................................ ................................ ................................ 16 
3.1 Features ................................ ................................ ................................ ........ 16 
3.2 Initialization ................................ ................................ ................................ ... 17 
3.3 States ................................ ................................ ................................ ............ 18 
3.4 Main Functions ................................ ................................ .............................. 18 
3.5 Error Handling ................................ ................................ ............................... 19 
3.5.1 Development Error Reporting ................................ ................................ ........ 19 
3.5.2 Production Code Error Reporting ................................ ................................ .. 20 
3.6 Configuration Phases ................................ ................................ .................... 21 
3.6.1 Link-time ................................ ................................ ................................ ....... 21 
3.6.2 Link-time for post-build capable configurations ................................ .............. 22 
3.6.3 Post-build ................................ ................................ ................................ ...... 22 
3.7 Memory allocation ................................ ................................ ......................... 24 
3.8 Interface Layer Gateway ................................ ................................ ............... 25 
3.8.1 Dynamic Dlc Routing ................................ ................................ ..................... 25 
3.9 Low-Level routing of TP N-PDUs ................................ ................................ ... 26 
3.10 Buffer Types ................................ ................................ ................................ .. 26 
3.10.1 Buffer overwrite routing (queue size < 2) ................................ ....................... 26 
3.10.1.1 Timing aspects ................................ ................................ .............................. 27 
3.10.1.2 Direct data provision ................................ ................................ ...................... 27 
3.10.1.3 Trigger transmit data provision ................................ ................................ ...... 27 
3.10.2 FiFo queued routing (queue size >= 2) ................................ .......................... 27 
3.10.2.1 Timing aspects ................................ ................................ .............................. 27 
3.10.2.2 Example for the FiFo queue handling ................................ ............................ 28 
3.11 Transport Protocol Gateway ................................ ................................ .......... 28 
3.12 AUTOSAR 3.0 TP API ................................ ................................ ................... 29 
3.13 AUTOSAR 3.0 TP API with ISO timing optimization ................................ ...... 30 
3.14 AUTOSAR 4.0 CAN TP API ................................ ................................ ........... 32 
3.15 Tp error handling ................................ ................................ ........................... 32 
3.16 TP Intra ECU Communication ................................ ................................ ....... 32 
4 Integration ................................ ................................ ................................ .................... 35 
4.1 Scope of Delivery ................................ ................................ .......................... 35 

Technical Reference MICROSAR PDU Router 
2012, Vector Informatik GmbH Version: 3.10.02 
based on template version 4.6 
6 / 106 
4.1.1 Static Files ................................ ................................ ................................ ..... 35 
4.1.2 Dynamic Files................................ ................................ ................................ 36 
4.2 Include Structure ................................ ................................ ........................... 37 
4.3 Critical Sections ................................ ................................ ............................ 38 
4.4 Application Access ................................ ................................ ........................ 38 
5 API Description ................................ ................................ ................................ ............ 39 
5.1 Services provided by PDUR ................................ ................................ .......... 39 
5.1.1 PduR_Init ................................ ................................ ................................ ...... 39 
5.1.2 PduR_InitMemory ................................ ................................ ......................... 39 
5.1.3 PduR_GetVersionInfo ................................ ................................ .................... 40 
5.1.4 PduR_GetConfigurationId ................................ ................................ ............. 40 
5.1.5 PduR_MainFunction ................................ ................................ ...................... 41 
5.1.6 PduR_EnableRouting ................................ ................................ .................... 41 
5.1.7 PduR_DisableRouting ................................ ................................ ................... 42 
5.1.7.1 PduR_CanTpStartOfReception ................................ ................................ ..... 42 
5.1.8 PduR_CanTpCopyRxData ................................ ................................ ............ 43 
5.1.9 PduR_CanTpCopyTxData ................................ ................................ ............. 44 
5.1.10 PduR_CddDobtSetCanTpState ................................ ................................ ..... 46 
5.1.11 Provided Interfaces to Lower Communication Interface Layers ..................... 46 
5.1.11.1 PduR_<LoIf>RxIndication ................................ ................................ ............. 46 
5.1.11.2 PduR_<LoIf>TxConfirmation ................................ ................................ ......... 47 
5.1.11.3 PduR_<LoIf>TriggerTransmit ................................ ................................ ........ 47 
5.1.12 Provided Interfaces to Lower Transport Protocol Layers ............................... 48 
5.1.12.1 PduR_<LoTp>ProvideRxBuffer ................................ ................................ ..... 48 
5.1.12.2 PduR_<LoTp>RxIndication ................................ ................................ ........... 49 
5.1.12.3 PduR_<LoTp>ProvideTxBuffer................................ ................................ ...... 50 
5.1.12.4 PduR_<LoTp>TxConfirmation ................................ ................................ ..

## Extracted outline

- 2 / 106 *(page 2)*
- 3 / 106 *(page 3)*
- 4 / 106 *(page 4)*
- 5 / 106 *(page 5)*
- 3.5.2 Production Code Error Reporting ................................ ................................ .. 20 *(page 5)*
- 3.6.2 Link-time for post-build capable configurations ................................ .............. 22 *(page 5)*
- 3.9 Low-Level routing of TP N-PDUs ................................ ................................ ... 26 *(page 5)*
- 3.10.1 Buffer overwrite routing (queue size < 2) ................................ ....................... 26 *(page 5)*
- 3.10.2 FiFo queued routing (queue size >= 2) ................................ .......................... 27 *(page 5)*
- 3.10.2.2 Example for the FiFo queue handling ................................ ............................ 28 *(page 5)*
- 3.13 AUTOSAR 3.0 TP API with ISO timing optimization ................................ ...... 30 *(page 5)*
- 3.14 AUTOSAR 4.0 CAN TP API ................................ ................................ ........... 32 *(page 5)*
- 3.16 TP Intra ECU Communication ................................ ................................ ....... 32 *(page 5)*
- 6 / 106 *(page 6)*
- 5.1 Services provided by PDUR ................................ ................................ .......... 39 *(page 6)*
- 5.1.7.1 PduR_CanTpStartOfReception ................................ ................................ ..... 42 *(page 6)*
- 5.1.8 PduR_CanTpCopyRxData ................................ ................................ ............ 43 *(page 6)*
- 5.1.9 PduR_CanTpCopyTxData ................................ ................................ ............. 44 *(page 6)*
- 5.1.10 PduR_CddDobtSetCanTpState ................................ ................................ ..... 46 *(page 6)*
- 5.1.11 Provided Interfaces to Lower Communication Interface Layers ..................... 46 *(page 6)*
- 5.1.12 Provided Interfaces to Lower Transport Protocol Layers ...............................  48 *(page 6)*
- 5.1.12.5 PduR_<LoTp>ChangeParameterConfirmation ................................ .............. 52 *(page 6)*
- 5.1.13 Provided Interfaces to Upper Layers ................................ ............................. 53 *(page 6)*
- 5.1.14 Provided Interfaces to Upper Transport Protocol Layers ...............................  54 *(page 6)*
- 5.1.14.1 PduR_<UpTp>ChangeParameterRequest ................................ .................... 54 *(page 6)*
- 5.1.14.2 PduR_<UpTp>ReadParameterRequest ................................ ........................ 55 *(page 6)*
- 5.1.14.3 PduR_<UpTp>CancelReceiveRequest ................................ ......................... 56 *(page 6)*
- 5.1.14.4 PduR_<UpTp>CancelTransmitRequest ................................ ........................ 56 *(page 6)*
- 5.3 Dependencies to other BSW Modules used by PDUR ................................ ... 58 *(page 6)*
- 7 / 106 *(page 7)*
- 6.2.2 Automatic Routing Path Configuration ................................ ........................... 65 *(page 7)*
- 6.2.2.1 Interface and Transport Protocol API Forwarding ................................ .......... 65 *(page 7)*
- 6.2.2.3 Transport Protocol Gateway Routing Paths ................................ ................... 66 *(page 7)*
- 6.2.3 Manual Gateway Routing Path Configuration ................................ ................ 67 *(page 7)*
- 6.2.3.4 Transport Protocol Gateway Routing Paths ................................ ................... 70 *(page 7)*
- 6.3.1.1 Creating Intra ECU communication TP I-PDUs................................ .............. 78 *(page 7)*
- 6.3.1.2 Removing Intra ECU communication TP I-PDUs ................................ ........... 79 *(page 7)*
- 6.3.1.3 Intra ECU communication Properties ................................ ............................ 79 *(page 7)*
- 6.5 Configuration in EcuC Data Base ................................ ................................ .. 81 *(page 7)*
- 8 / 106 *(page 8)*
- 9 / 106 *(page 9)*
- 10 / 106 *(page 10)*
- 11 / 106 *(page 11)*
- 12 / 106 *(page 12)*
- 1 Component History *(page 12)*
- 2.00.00 > Support for AUTOSAR release 2.0 *(page 12)*
- 2.01.00 > LIN Interface support added *(page 12)*
- 2.02.00 > Post-build configuration *(page 12)*
- 2.03.00 > Support for AUTOSAR release 2.1 *(page 12)*
- 2.04.00 > Interface layer gateway *(page 12)*
- 2.05.00 > Support for AUTOSAR release 3 (partially) *(page 12)*
- 3.00.00 > API change for COM <-> CanTp API forwarding *(page 12)*
- 3.01.00 > Minor improvements (see source code history) *(page 12)*
- 3.02.00 > Support for TMS320 *(page 12)*
- 3.03.00 > Interface for application  access to interface and TP layer PDUs (optional *(page 12)*
- 3.04.00 > CRC Check of configuration data *(page 12)*
- 3.05.00 > Intra ECU communication for TP PDUs *(page 12)*
- 3.06.00 > IPDUM support added *(page 12)*
- 3.07.00 > MOST Interface support added *(page 12)*
- 3.08.00 > Multiple Configuration *(page 12)*
- 3.09.00 > LIN TP support  added *(page 12)*
- 3.10.00 > SoAd TP support added *(page 12)*
- 3.11.00 > API forwarding between COM and CanNm, FrNm layer *(page 12)*
- 13 / 106 *(page 13)*
- 3.12.00 > Minor Changes *(page 13)*
- 3.13.00 > Minor Changes *(page 13)*
- 3.14.00 > TP Receive Cancellation for CanTp, LinTp, FrTp *(page 13)*
- 3.15.00 > Support Rx for CanNm and FrNm *(page 13)*
- 3.15.09 > AR3-2457: Dynamic DLC with TriggerTransmit based Communication *(page 13)*
- 14 / 106 *(page 14)*
- 2 Introduction *(page 14)*
- 15 / 106 *(page 15)*
- 2.1 Architecture Overview *(page 15)*
- 16 / 106 *(page 16)*
- 3 Functional Description *(page 16)*
- 3.1 Features *(page 16)*
- 17 / 106 *(page 17)*
- 3.2 Initialization *(page 17)*
- 18 / 106 *(page 18)*
- 3.3 States *(page 18)*
- Pdur_Uninit *(page 18)*
- Pdur_Online *(page 18)*
- 3.4 Main Functions *(page 18)*
- 19 / 106 *(page 19)*
- 3.5 Error Handling *(page 19)*
- 3.5.1 Development Error Reporting *(page 19)*
- Pdur_E_Tp_Tx_Req_Reject *(page 19)*
- Pdur_E_Tp_Buffer_Size_Lim *(page 19)*
- 20 / 106 *(page 20)*
- Pdur_E_Ul_Buffer_Underr *(page 20)*
- Pdur_E_Routing_Table_Id_I *(page 20)*
- Nvalid *(page 20)*
- Pdur_Inconsistent_Sizeof *(page 20)*
- Pduidtype *(page 20)*
- 3.5.2 Production Code Error Reporting *(page 20)*
- 21 / 106 *(page 21)*
- 3.6 Configuration Phases *(page 21)*
- 3.6.1 Link-time *(page 21)*
- 22 / 106 *(page 22)*
- 3.6.2 Link-time for post-build capable configurations *(page 22)*
- 3.6.3 Post-build *(page 22)*
- 23 / 106 *(page 23)*
- 24 / 106 *(page 24)*
- 3.7 Memory allocation *(page 24)*
- 25 / 106 *(page 25)*
- 3.8 Interface Layer Gateway *(page 25)*
- 3.8.1 Dynamic Dlc Routing *(page 25)*
- Direct *(page 25)*
- Trigger_Transmit *(page 25)*
- 26 / 106 *(page 26)*
- 3.9 Low-Level routing of TP N-PDUs *(page 26)*
- 3.10 Buffer Types *(page 26)*
- 3.10.1 Buffer overwrite routing (queue size < 2) *(page 26)*
- 27 / 106 *(page 27)*
- 3.10.1.1 Timing aspects *(page 27)*
- 3.10.1.2 Direct data provision *(page 27)*
- 3.10.1.3 Trigger transmit data provision *(page 27)*
- 3.10.2 FiFo queued routing (queue size >= 2) *(page 27)*
- 3.10.2.1 Timing aspects *(page 27)*
- 28 / 106 *(page 28)*
