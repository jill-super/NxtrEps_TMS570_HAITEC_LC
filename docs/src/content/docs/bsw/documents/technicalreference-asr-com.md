---
title: "TechnicalReference Asr Com"
description: "Converted from TechnicalReference_Asr_Com.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_Com.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (195 pages).

**Pages:** 195

---

This is a **195-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR COM 
Technical Reference 
 
 
Version 2.11.01 
 
 
 
 
 
 
 
 
 
 
 
Authors Gunnar Meiss, Hartmut Hörner, Klaus Emmert, Hannes 
Haas, Michael Bissinger, Dominik Biber 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR COM 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Gunnar Meiss 2006-07-31 0.1 Creation 
Hartmut Hörner 2006-09-13 0.2 Update to new template version 
Klaus Emmert 2006-09-25 0.3 New Illustrations 
Hartmut Hörner 2006-10-13 0.4 Post build process figure updated, several minor 
changes based on review comments 
Hartmut Hörner 2006-10-24 0.5 Added configuration chapter and list of DET error 
codes. 
Hartmut Hörner 2006-11-06 1.0 Minor changes based on review comments. 
Gunnar Meiss 2007-01-08 1.1 ESCAN00018727, 
ESCAN00018724, 
ESCAN00018738, 
ESCAN00018721, 
ESCAN00018723 
Gunnar Meiss 2007-03-13 1.2 ESCAN00019913 
Hannes Haas 2007-04-26 1.2 ESCAN00019913: Added Signal Gateway 
Update to new template 
General rework 
Gunnar Meiss 2007-08-01 1.2 ESCAN00021344: Update EcuC Description 
Removed error message list 
Removed COM_IPDU_DIRECTION , 
COM_NETWORK_SIGNAL_DIRECTION 
Updated EcuC attribute names 
Updated EcuC Import/Export 
Updated GenSigSendType 
Michael Bissinger 2007-10-05 1.3 Added signal conversion description 
ESCAN00022013, 
ESCAN00022628, 
ESCAN00022050 
Michael Bissinger 2007-11-23 1.4 Added I-PDU callouts 
ESCAN00023159 
Added indication and Rx timeout flags 
ESCAN00023392 
Hannes Haas 2008-01-10 1.5 Added support for TP I-PDU communication 
©2011, Vector Informatik GmbH Version: 2.11.01 
based on template version 3.2 
2 / 195

Technical Reference MICROSAR COM 
©2011, Vector Informatik GmbH Version: 2.11.01 
based on template version 3.2 
3 / 195
Michael Bissinger 2008-02-13 1.6 Added Transmission Mode Selector chapter 3.7.2 
Added Transmit Signal Filters chapter 3.7.3 
Added new send type mappings to chapter 6.1 
ESCAN00024194 
Gunnar Meiss 2008-03-18 2.0 AUTOSAR 3 
Updated API Descriptions 
Restructured Documentation 
Gunnar Meiss 2008-07-07 2.1 Added Tms320 Limitation 
Updated API Description 
Updated EcuC Description 
Upgraded Technical Reference Template 
Updated Callout Description 
Gunnar Meiss 2008-07-21 2.2 Rework with CIWI 
Updated Chapter 6.5.2.1 Automatic routing 
relations 
Updated 7.2.2 Code Generator and Configuratior 
d Chapter 6.4Configuration in EcuC Data 
provided by COM 
Updated Chapter 6.5 Configuration with GENy 
Update
Base 
Updated Chapter 5.2 Services 
Gunnar Meiss 2008-11-28 2.3 
d Chapter 6.4 Configuration in EcuC Data 
 
Added Signal Invalidation API 
Updated Chapter 6.5 Configuration with GENy 
Update
Base 
Updated Chapter 5.2 Services provided by COM
Michael Bissinger nvalid Signal Values 2008-12-12 Added 3.8.3 Reception of I
Gunnar Meiss 2008-12-22 2.4 Added First Timeout Time 
Gunnar Meiss 2009-03-04 2.5 n and Memory 
0030888) 
Added 4.3 Compiler Abstractio
Mapping (ESCAN0
ESCAN00032806 
ESCAN00033565 
Dominik Biber 2009-11-13 2.6 ESCAN00038580 
ESCAN00038562 
Dominik Biber 2009-11-20 2.6 ESCAN00039294 Updated chapter 6.5.2.4 
Dominik Biber 2009-11-30 2.6 Documents Updated Chapter 1.2 Reference 
Updated Chapter 2 Introduction 
Dominik Biber 2010-03-04 2.6.1 Signalgroup support in LDF files 
Dominik Biber 2010-03-04 2.6.1 Support Optional Invalidation (F334) 

Technical Reference MICROSAR COM 
Dominik Biber 2010-04-19 2.7.0 ESCAN00039525 Add 'Service Ids' and 'Errors 
reported to DET' table 
ESCAN00042150 Support StateOn flag provider 
ESCAN00042149 Pre-compile optimization for flag 
provider macro access 
ESCAN00042386 Support preconfiguration of all 
parameters 
Dominik Biber 2010-05-03 2.8.0 ESCAN00040927 
ESCAN00041028 
ESCAN00042542 
ESCAN00042075 
ESCAN00042007 
ESCAN00039799 
Dominik Biber 2010-08-06 2.9.0 Added 3.7.5 Transmission Deadline Monitoring 
(ESCAN00043067, ESCAN00043739) 
Adapted 3.7.2 Transmission Mode Selector 
(ESCAN00043947) 
ESCAN00044396, ESCAN00044109, 
ESCAN00043651 
Dominik Biber 2010-09-27 2.10.0 Updated 3.1 Features 
Updated 3.3 States 
Added 3.7.1 Transmission of a Signal Group 
Added 3.8.1 Reception of a Signal Group 
Updated 6.4 Configuration in EcuC Data Base 
Updated 6.5.1 Com Parameters 
(ESCAN00044954, ESCAN00045321) 
Dominik Biber 2010-12-20 2.11.00 > Removed “TMS Trigger Enter False” 
(ESCAN00045552) 
> Changed description of Tx I-PDU callout call context 
in 5.5.2 Callout Functions (ESCAN00045253) 
> Support PduInfoType instead of the DataPtr 
(ESCAN00046124). 
Changed following API descriptions 
5.4.1 Com_RxIndication 
5.4.2 Com_TriggerTransmit 
5.5.2 Callout Functions 
> Support Dynamic DLC (ESCAN00047020) 
Added 3.8.4 Dynamic DLC 
> Added configuration restriction to 7.1.6 Transport 
Protocol API (CanTp) (ESCAN00046398) 
> Updated figure Figure 3-11 Minimum Delay Time 
(ESCAN00046068) 
> Added 3.3.2 Multiple I-PDU group reference 
(ESCAN00044036) 
©2011, Vector Informatik GmbH Version: 2.11.01 
based on template version 3.2 
4 / 195

Technical Reference MICROSAR COM 
Dominik Biber 2011-01-27 2.11.00 > Corrected definition of the signal filter 
F_MaskedNewDiffersMaskedOld (3.7.3 Transmit 
Signal Filters, ESCAN00047878) 
Dominik Biber 2011-02-21 2.11.00 > Added 3.3.1 I-PDU group Configuration and updated 
3.3.2 Multiple I-PDU group reference 
(ESCAN00048770) 
Dominik Biber 2011-07-13 2.11.01 > Added restrictions to signal group access APIs (3.8.1 
Reception of a Signal Group, 5.2.16 
Com_ReceiveShadowSignal, 3.7.1 Transmission of a 
Signal Group, 5.2.20 Com_UpdateShadowSignal, 
ESCAN00050107) 
> Changed description of main functions (3.4 Main 
Functions, ESCAN00051633) 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Source Title Version 
[1] AUTOSAR AUTOSAR_SWS_COM.pdf 3.0.1 
[2] AUTOSAR AUTOSAR_SWS_DET.pdf 2.2.0 
[3] AUTOSAR AUTOSAR_BasicSoftwareModules.pdf 1.1.0 
[4] Vector TechnicalReferencePostbuildProcess.pdf 0.2 
[5] Vector AN-ISC-8-1118_MICROSAR_BSW_Compatibility_Check.pdf 1.00.00 
Table 1-2 Reference documents 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
©2011, Vector Informatik GmbH Version: 2.11.01 
based on template version 3.2 
5 / 195

Technical Reference MICROSAR COM 
Contents 
1 Document Information..................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 5 
2 Introduction ....................................................................................................................1 4 
2.1 Architecture Overview..................................................................................... 15 
3 Functional Description .................................................................................................. 17 
3.1 Features.......................................................................................................... 17 
3.2 Initialization ..................................................................................................... 18 
3.3 States.............................................................................................................. 19 
3.3.1 I-PDU group Configuration ............................................................................. 20 
3.3.2 Multiple I-PDU group reference ...................................................................... 23 
3.4 Main Functions ............................................................................................... 26 
3.5 Error Handling................................................................................................. 27 
3.5.1 Development Error Reporting ......................................................................... 27 
3.5.2 Production Code Error Reporting ................................................................... 31 
3.6 Signal Types ................................................................................................... 32 
3.7 Transmission of a Signal................................................................................. 32 
3.7.1 Transmission of a Signal Group...................................................................... 34 
3.7.2 Transmission Mode Selector .......................................................................... 35 
3.7.3 Transmit Signal Filters .................................................................................... 36 
3.7.4 Minimum Send Distance of an I-PDU ............................................................. 37 
3.7.5 Transmission Deadline Monitoring.................................................................. 37 
3.8 Reception of a Signal...................................................................................... 39 
3.8.1 Reception of a Signal Group........................................................................... 40 
3.8.2 Reception Deadline Monitoring....................................................................... 41 
3.8.3 Reception of Invalid Signal Values.................................................................. 41 
3.8.4 Dynamic DLC.................................................................................................. 41 
3.9 Signal Gateway............................................................................................... 42 
3.9.1 Signal routing requirements............................................................................ 43 
3.9.2 Routing of signal groups ................................................................................. 43 
3.9.3 Routing of signals with update bits ................................................................. 43 
3.9.4 Adding and removing gateway signals ........................................................... 43 
3.9.5 Routing latency ............................................................................................... 43 
4 Integration....................................................................................................................... 45 
4.1 Scope of Delivery............................................................................................ 45 
©2011, Vector Informatik GmbH Version: 2.11.01 
based on template version 3.2 
6 / 195

Technical Reference MICROSAR COM 
4.1.1 Static Files ...................................................................................................... 45 
4.1.2 Dynamic Files ................................................................................................. 45 
4.2 Include Structure............................................................................................. 46 
4.3 Compiler Abstraction and Memory Mapping................................................... 46 
4.4 Critical Sections .............................................................................................. 47 
4.4.1 BSW Scheduler .............................................................................................. 47 
4.4.2 Vector Standard Library .................................................................................. 50 
4.5 Operating System Requirements.................................................................... 50 
5 API Description .............................................................................................................. 51 
5.1 Type Definitions .............................................................................................. 51 
5.2 Services provided by COM ............................................................................. 52 
5

## Extracted outline

- Microsar Com *(page 1)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- Escan00018724, *(page 2)*
- Escan00018738, *(page 2)*
- Escan00018721, *(page 2)*
- Escan00018723 *(page 2)*
- Com_Network_Signal_Direction *(page 2)*
- Escan00022013, *(page 2)*
- Escan00022628, *(page 2)*
- Escan00022050 *(page 2)*
- Escan00023159 *(page 2)*
- Escan00023392 *(page 2)*
- 2 / 195 *(page 2)*
- 3 / 195 *(page 3)*
- Escan00024194 *(page 3)*
- Escan00032806 *(page 3)*
- Escan00033565 *(page 3)*
- Escan00038562 *(page 3)*
- Escan00041028 *(page 4)*
- Escan00042542 *(page 4)*
- Escan00042075 *(page 4)*
- Escan00042007 *(page 4)*
- Escan00039799 *(page 4)*
- (Escan00043067, Escan00043739) *(page 4)*
- (Escan00043947) *(page 4)*
- Escan00044396, Escan00044109, *(page 4)*
- Escan00043651 *(page 4)*
- (Escan00044954, Escan00045321) *(page 4)*
- (Escan00045552) *(page 4)*
- (Escan00046124). *(page 4)*
- 5.4.1 Com_RxIndication *(page 4)*
- 5.4.2 Com_TriggerTransmit *(page 4)*
- 5.5.2 Callout Functions *(page 4)*
- (Escan00046068) *(page 4)*
- (Escan00044036) *(page 4)*
- 4 / 195 *(page 4)*
- 3.3.2 Multiple I-PDU group reference *(page 5)*
- (Escan00048770) *(page 5)*
- Escan00050107) *(page 5)*
- 1.2 Reference Documents *(page 5)*
- 5 / 195 *(page 5)*
- 3.5.2 Production Code Error Reporting ................................................................... 31 *(page 6)*
- 3.7.1 Transmission of a Signal Group...................................................................... 34 *(page 6)*
- 3.7.4 Minimum Send Distance of an I-PDU ............................................................. 37 *(page 6)*
- 3.7.5 Transmission Deadline Monitoring.................................................................. 37 *(page 6)*
- 3.8.2 Reception Deadline Monitoring....................................................................... 41 *(page 6)*
- 3.8.3 Reception of Invalid Signal Values.................................................................. 41 *(page 6)*
- 3.9.4 Adding and removing gateway signals ........................................................... 43 *(page 6)*
- 6 / 195 *(page 6)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 46 *(page 7)*
- 4.5 Operating System Requirements.................................................................... 50 *(page 7)*
- 5.2 Services provided by COM ............................................................................. 52 *(page 7)*
- 5.2.6 Com_EnableReceptionDM ............................................................................. 54 *(page 7)*
- 5.2.7 Com_DisableReceptionDM ............................................................................ 55 *(page 7)*
- 5.2.10 Com_GetConfigurationStringPtr ..................................................................... 56 *(page 7)*
- 5.2.14 Com_MainFunctionRouteSignals ................................................................... 58 *(page 7)*
- 5.2.16 Com_ReceiveShadowSignal .......................................................................... 59 *(page 7)*
- 5.2.20 Com_UpdateShadowSignal............................................................................ 61 *(page 7)*
- 7 / 195 *(page 7)*
- 6.1 Configuration in Dbc Data Base...................................................................... 72 *(page 8)*
- 6.2 Configuration in Ldf Data Base....................................................................... 78 *(page 8)*
- 6.3 Configuration in FIBEX Data Base.................................................................. 80 *(page 8)*
- 6.4 Configuration in EcuC Data Base ................................................................... 82 *(page 8)*
- 8 / 195 *(page 8)*
- 7.1.1.2 Com_Convert_SignedBusToEcu .................................................................. 165 *(page 9)*
- 7.1.1.3 Com_Convert_UnsignedBusToEcu .............................................................. 166 *(page 9)*
- 7.1.1.4 Com_Convert_SignedEcuToBus .................................................................. 167 *(page 9)*
- 7.1.1.5 Com_Convert_UnsignedEcuToBus .............................................................. 167 *(page 9)*
- 7.1.2.1 Com_GetRxSigIndicationFlag ...................................................................... 171 *(page 9)*
- 7.1.2.2 Com_ GetRxSigGrpIndicationFlag ............................................................... 171 *(page 9)*
- 7.1.2.4 Com_ClrRxSigGrpIndicationFlag.................................................................. 173 *(page 9)*
- 7.1.3.1 Com_GetRxSigTimeoutFlag ......................................................................... 177 *(page 9)*
- 7.1.3.2 Com_GetRxSigGrpTimeoutFlag ................................................................... 177 *(page 9)*
- 7.1.3.4 Com_ClrRxSigGrpTimeoutFlag .................................................................... 179 *(page 9)*
- 7.1.4.1 Com_GetRxSigStateOnFlag......................................................................... 182 *(page 9)*
- 7.1.4.2 Com_GetRxSigGrpStateOnFlag................................................................... 182 *(page 9)*
- 7.1.5 Com_IpduGroupTransmit ............................................................................. 184 *(page 9)*
- 7.1.6 Transport Protocol API (CanTp).................................................................... 184 *(page 9)*
- 7.1.8 Gateway: Rx signal timeout handling without update bits............................. 187 *(page 9)*
- 7.2.2 Code Generator and Configuratior ............................................................... 189 *(page 9)*
- 9 / 195 *(page 9)*
- 10 / 195 *(page 10)*
- 11 / 195 *(page 11)*
- 12 / 195 *(page 12)*
- 13 / 195 *(page 13)*
- 2 Introduction *(page 14)*
- 14 / 195 *(page 14)*
- 2.1 Architecture Overview *(page 15)*
- 15 / 195 *(page 15)*
- 16 / 195 *(page 16)*
- 3 Functional Description *(page 17)*
- 3.1 Features *(page 17)*
- 17 / 195 *(page 17)*
- 3.2 Initialization *(page 18)*
- 18 / 195 *(page 18)*
- 19 / 195 *(page 19)*
- 3.3 States *(page 19)*
- Com_Uninit *(page 19)*
- 3.3.1 I-PDU group Configuration *(page 20)*
- 20 / 195 *(page 20)*
- 21 / 195 *(page 21)*
- 22 / 195 *(page 22)*
- 23 / 195 *(page 23)*
- 24 / 195 *(page 24)*
- 25 / 195 *(page 25)*
- 3.4 Main Functions *(page 26)*
- 26 / 195 *(page 26)*
- 27 / 195 *(page 27)*
- 3.5 Error Handling *(page 27)*
- 3.5.1 Development Error Reporting *(page 27)*
- 1 COMServiceId_Init *(page 27)*
- 2 COMServiceId_DeInit *(page 27)*
- 3 COMServiceId_IpduGroupStart *(page 27)*
- 4 COMServiceId_IpduGroupStop *(page 27)*
- 5 COMServiceId_DisableReceptionDM *(page 27)*
- 6 COMServiceId_EnableReceptionDM *(page 27)*
- 7 COMServiceId_GetStatus *(page 27)*
- 8 COMServiceId_GetConfigurationId *(page 27)*
- 9 COMServiceId_GetVersionInfo *(page 27)*
