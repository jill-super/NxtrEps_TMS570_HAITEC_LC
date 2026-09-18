---
title: "TechnicalReference Asr Dcm"
description: "Converted from TechnicalReference_Asr_Dcm.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_Dcm.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (163 pages).

**Pages:** 163

---

This is a **163-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR DCM 
Technical Reference 
 
Vector 
Version 3.26.02 
 
 
 
 
 
 
 
 
 
 
 
Authors Mishel Shishmanyan, Jochen Breunich, Katrin Thurow 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
2 / 163 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Mishel Shishmanyan 2008-04-20 1.0 Reworks based on the new document 
template. 
Mishel Shishmanyan 2008-06-13 1.1 Extensions to DCM 3.03.00 
Removed unused chapters and sections. 
Modified: 
5.10.3 Configuration Aspects 
Mishel Shishmanyan 2008-07-18 1.2 Minor editorial changes. 
Added: 
6 Additional features beyond AUTOSAR 
DCM 3.0 
Mishel Shishmanyan 2008-08-20 3.4 Modified: 
Version jump to unify the different DCM 
generation documentations. 
8.5.1.2.11, 8.5.1.2.12, 8.5.1.2.13, 8.5.1.2.14 
– port interface change for service $2F. 
9.2.2 General DCM options 
 
 
Mishel Shishmanyan 2008-09-01 3.5 Modified: 
5.18.1 Functionality 
Table 8-23 Require Ports on BSW module 
side 
 
Added: 
5.18.1.1 Difference between single and 
multiple UUDT message transmission 
Mishel Shishmanyan 2008-10-08 3.6 Modified: 
5.16.2 Implementation Limitations 
Figure 8-1 DCM interactions with other 
BSW 
 
10.2.5 Jump into FBL on Request 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
3 / 163 
“Programming Session” ($10 $02) 
Mishel Shishmanyan 2008-11-21 3.7 Modified: 
5.13.3.2 GENy 
9.2.2General DCM options 
Mishel Shishmanyan 2008-12-15 3.8 Modified: 
Minor editorial changes. 
Table 8-23 Require Ports on BSW module 
side 
 
Added: 
Full description of all service ports required 
by DCM. 
8.5.1.3 Implementation Hints for Port Usage 
Mishel Shishmanyan 2009-01-23 3.9 Modified: 
1.2 Reference Documents 
 
Mishel Shishmanyan 2009-02-27 3.10 Added: 
8.5.1.2Require Ports – detailed description 
of all ports. 
 
Modified: 
8.3 Services Used by DCM – all services 
that DCM uses are now described. 
8.5.1.2Require Ports – all ports that DCM 
requires are now described. 
9.2.2General DCM options 
5.11EcuReset ($11) 
Mishel Shishmanyan 2009-03-27 3.11 Added: 
10.1.2 Compiler abstraction 
 
Modified: 
Table 1-3 Component history 
Table 8-3 Services used by the DCM 
 
Mishel Shishmanyan 2009-05-22 3.12 Modified: 
10.1.2 Compiler abstraction 
3.2 Initialization 
 
Added: 
Table 3-3 Dcm_Init 
Mishel Shishmanyan 2009-07-31 3.13 Modified: 
Minor editorial changes. 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
4 / 163 
Table 1-3 Component history 
Table 8-3 Services used by the DCM 
 
 
Added: 
3.3 VSG Configuration Set Pre-Selection 
 
6.3 Multi-Identity Support 
 
Mishel Shishmanyan 2009-08-31 3.14 
Jochen Breunich 
Mishel Shishmanyan 
2009-10-27 3.15 Added: 
6.4 Code Template 
 
Modified: 
4.1.2 Dynamic Files – Added new dynamic 
files Appl_Dcm.h/.c 
8.5.1.2 Require Ports – Corrected API 
descriptions 
 
Mishel Shishmanyan 2010-01-20 3.16 Added: 
7 Overview of all Services handled by DCM 
Modified: 
 
Minor editorial changes. 
Mishel Shishmanyan 2010-02-11 3.17 Added: 
New OEM support 
Mishel Shishmanyan 2010-03-31 3.18 Added: 
Support for DirectMemoryAccess services 
 
New ISO 14229-1 standard reference 
Katrin Thurow 2010-04-27 3.19 Added: 
New OEM support 
Table 5-18 Security Access Attributes in 
CANdela 
Used Service 
EcuM_GeneratorCompatibilityError 
Support Communication Control 
 
 
Modified: 
9.2 Configuration with GENy 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
5 / 163 
Mishel Shishmanyan 2010-07-28 3.20 Added: 
4.4Critical Sections 
 
Modified: 
Minor editorial changes. 
8.5.1.2.8<CallPrefix>DidServices_<DID>_R
eadData 
Mishel Shishmanyan 2010-08-09 3.21 Added: 
6.5 Support of Unspecified Services 
 
 
Modified: 
9.2.2 General DCM options 
Mishel Shishmanyan 2010-10-27 3.22 Added: 
New OEM support. 
 
Removed: 
 
Mishel Shishmanyan 2010-12-10 3.23 Added: 
3.5.1 Split task functions 
8.3.3 Jump To/From FBL 
9.2.1.1 Path placeholders 
 
Modified: 
5.22.2 Implementation Limitations 
Mishel Shishmanyan 2011-02-03 3.24 Minor editorial changes. 
 
Mishel Shishmanyan 2011-02-14 3.25 Modified: 
9.2.2 General DCM options 
Mishel Shishmanyan 2011-05-06 3.26 
Added: 
Chapters 5.1- 5.9 (OBD services) 
6.2 (WWH-)OBD Support 
7 Overview of all Services handled by DCM 
10.2.5.2 AR 4.0 like Jump to/from the FBL 
Modified: 
1.2 Reference Documents. 
Mishel Shishmanyan 2011-12-16 3.26.01 Added: 
8.5.1.2.24<CallPrefix>InfoTypeServices_<IN
FID>_ReadDataLength 
Modified: 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
6 / 163 
8.5.1.2.23<CallPrefix>InfoTypeServices_<IN
FID>_GetInfoTypeValue 
 
Mishel Shishmanyan 2012-10-10 3.26.02 Modified: 
Table 8-35 
 <CallPrefix>DidServices_<DID>_WriteDat
a – minor changes on return value and 
function descriptions. 
Table 8-36 
 <CallPrefix>DidServices_<DID>_ReturnC
ontrolToECU – added limitation to the 
DCM_E_PENDING return value usage. 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_DCM.pdf V3.0.0 
[2] AUTOSAR_SWS_DET.pdf V2.2.0 
[3] AUTOSAR_SWS_DEM.pdf V2.1.1 
V2.2.1 
[4] AUTOSAR_BasicSoftwareModules.pdf V1.0.0 
[5] ISO 14229-1 UDS 2010 
[6] ISO 15765-4 Requirements for emissions-related systems 2004 
[7] ISO 15031-5 Emissions-related diagnostic services 2004 
[8] Application Note AN-ISC-8-1118 – MICROSAR BSW Compatibility Check V1.0.0 
[9] ISO 27145-2 WWH-OBD CDD Emissions 2009 
[10] ISO 27145-3 WWH-OBD CMD 2009 
Table 1-2 Reference documents 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
7 / 163 
Contents 
1 Document Information ................................ ................................ ................................ ... 2 
1.1 History ................................ ................................ ................................ ............. 2 
1.2 Reference Documents ................................ ................................ ..................... 6 
2 Introduction ................................ ................................ ................................ .................. 21 
2.1 Architecture Overview ................................ ................................ ................... 22 
3 Functional Description ................................ ................................ ................................ 24 
3.1 Features ................................ ................................ ................................ ........ 24 
3.2 Initialization ................................ ................................ ................................ ... 24 
3.3 VSG Configuration Set Pre-Selection ................................ ............................ 25 
3.4 States ................................ ................................ ................................ ............ 27 
3.5 Main Functions ................................ ................................ .............................. 27 
3.5.1 Split task functions ................................ ................................ ........................ 27 
3.5.1.1 Dcm_TimerTask ................................ ................................ ............................ 28 
3.5.1.2 Dcm_StateTask ................................ ................................ ............................. 29 
3.6 Error Handling ................................ ................................ ............................... 29 
3.6.1 Development Error Reporting ................................ ................................ ........ 29 
3.6.2 Production Code Error Reporting ................................ ................................ .. 30 
4 Integration ................................ ................................ ................................ .................... 31 
4.1 Scope of Delivery ................................ ................................ .......................... 31 
4.1.1 Static Files ................................ ................................ ................................ ..... 31 
4.1.2 Dynamic Files................................ ................................ ................................ 31 
4.2 Include Structure ................................ ................................ ........................... 32 
4.2.1 For DCM versions older than 3.15.00 ................................ ............................ 32 
4.2.2 For DCM version 3.15.00 and newer ................................ ............................. 33 
4.3 Compiler Abstraction and Memory Mapping ................................ .................. 33 
4.4 Critical Sections ................................ ................................ ............................ 34 
4.5 Considerations Using Request- and ResponseData Pointers in a Call-
back ................................ ................................ ................................ .............. 35 
5 Diagnostic Service Implementation ................................ ................................ ............ 36 
5.1 RequestCurrentPowertrainDiagnosticData ($01) ................................ ........... 36 
5.1.1 Functionality ................................ ................................ ................................ .. 36 
5.1.2 Implementation Limitations ................................ ................................ ............ 36 
5.1.3 Configuration Aspects ................................ ................................ ................... 36 
5.1.3.1 CANdela ................................ ................................ ................................ ........ 36 

Technical Reference MICROSAR DCM 
2012, Vector Informatik GmbH Version: 3.26.02 
based on template version 3.1 
8 / 163 
5.1.3.2 GENy ................................ ................................ ................................ ............ 36 
5.2 RequestPowertrainFreezeFrameData ($02) ................................ .................. 36 
5.2.1 Functionality ................................ ................................ ................................ .. 36 
5.2.2 Implementation Specifics ................................ ................................ ............... 37 
5.2.3 Implementation Limitations ................................ ................................ ............ 38 
5.2.4 Configuration Aspects ................................ ................................ ................... 38 
5.2.4.1 CANdela ................................ ................................ ................................ ........ 38 
5.2.4.2 GENy ................................ ................................ ................................ ............ 38 
5.3 RequestEmissionRelatedDTC ($03) ................................ .............................. 38 
5.3.1 Functionality ................................ ................................ ................................ .. 38 
5.3.2 Implementation Specifics ................................ ................................ ............... 38 
5.3.3 Implementation Limitations ................................ ................................ ............ 40 
5.3.4 Configuration Aspects ................................ ................................ ................... 40 
5.3.4.1 CANdela ................................ ................................ ..................

## Extracted outline

- Microsar Dcm *(page 1)*
- 2 / 163 *(page 2)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 5.10.3 Configuration Aspects *(page 2)*
- 6 Additional features beyond AUTOSAR *(page 2)*
- Dcm 3.0 *(page 2)*
- 9.2.2 General DCM options *(page 2)*
- 5.18.1 Functionality *(page 2)*
- 5.18.1.1 Difference between single and *(page 2)*
- 5.16.2 Implementation Limitations *(page 2)*
- 10.2.5 Jump into FBL on Request *(page 2)*
- 3 / 163 *(page 3)*
- 5.13.3.2 GENy *(page 3)*
- 8.5.1.3 Implementation Hints for Port Usage *(page 3)*
- 1.2 Reference Documents *(page 3)*
- 8.3 Services Used by DCM – all services *(page 3)*
- 10.1.2 Compiler abstraction *(page 3)*
- 3.2 Initialization *(page 3)*
- 4 / 163 *(page 4)*
- 3.3 VSG Configuration Set Pre-Selection *(page 4)*
- 6.3 Multi-Identity Support *(page 4)*
- 6.4 Code Template *(page 4)*
- 4.1.2 Dynamic Files – Added new dynamic *(page 4)*
- 8.5.1.2 Require Ports – Corrected API *(page 4)*
- 7 Overview of all Services handled by DCM *(page 4)*
- 9.2 Configuration with GENy *(page 4)*
- 5 / 163 *(page 5)*
- 6.5 Support of Unspecified Services *(page 5)*
- 3.5.1 Split task functions *(page 5)*
- 8.3.3 Jump To/From FBL *(page 5)*
- 9.2.1.1 Path placeholders *(page 5)*
- 5.22.2 Implementation Limitations *(page 5)*
- 6.2 (WWH-)OBD Support *(page 5)*
- 10.2.5.2 AR 4.0 like Jump to/from the FBL *(page 5)*
- 1.2 Reference Documents. *(page 5)*
- 6 / 163 *(page 6)*
- V2.2.1 *(page 6)*
- [5]  Iso 14229-1 Uds 2010 *(page 6)*
- [10]  Iso 27145-3 Wwh-Obd Cmd 2009 *(page 6)*
- 7 / 163 *(page 7)*
- 3.3 VSG Configuration Set Pre-Selection ................................ ............................ 25 *(page 7)*
- 3.6.2 Production Code Error Reporting ................................ ................................ .. 30 *(page 7)*
- 4.2.1 For DCM versions older than 3.15.00 ................................ ............................ 32 *(page 7)*
- 4.2.2 For DCM version 3.15.00 and newer ................................ ............................. 33 *(page 7)*
- 4.3 Compiler Abstraction and Memory Mapping ................................ .................. 33 *(page 7)*
- 4.5 Considerations Using Request- and ResponseData Pointers in a Call- *(page 7)*
- 5.1 RequestCurrentPowertrainDiagnosticData ($01) ................................ ........... 36 *(page 7)*
- 8 / 163 *(page 8)*
- 5.2 RequestPowertrainFreezeFrameData ($02) ................................ .................. 36 *(page 8)*
- 5.3 RequestEmissionRelatedDTC ($03) ................................ .............................. 38 *(page 8)*
- 5.4 ClearEmissionRelatedDTC ($04) ................................ ................................ .. 41 *(page 8)*
- 5.5 RequestOnBoardMonitorTestResults ($06) ................................ ................... 41 *(page 8)*
- 5.6 RequestEmissionRelatedDTCsDetectedDuringCurrentOrLastDrivingCycle *(page 8)*
- 5.7 RequestControlOfOnBoardSystemTestOrComponent ($08) .......................... 47 *(page 8)*
- 9 / 163 *(page 9)*
- 5.8 RequestVehicleInformation ($09) ................................ ................................ .. 47 *(page 9)*
- 5.9 RequestEmissionRelatedDTCsWithPermanentStatus ($0A) ......................... 48 *(page 9)*
- 5.10 DiagnosticSessionControl ($10) ................................ ................................ .... 49 *(page 9)*
- 5.12 ClearDiagnosticInformation ($14) ................................ ................................ .. 54 *(page 9)*
- 5.13 ReadDiagnosticInformation ($19) ................................ ................................ .. 55 *(page 9)*
- 10 / 163 *(page 10)*
- 5.15 ReadMemoryByAddress ($23) ................................ ................................ ...... 58 *(page 10)*
- 5.18 ReadDataByPeriodicIdentifier ($2A) ................................ .............................. 64 *(page 10)*
- 5.18.1.1 Difference between single and multiple UUDT message transmission .......... 64 *(page 10)*
- 5.19 DynamicallyDefineDataIdentifier ($2C) ................................ .......................... 70 *(page 10)*
- 11 / 163 *(page 11)*
- 5.23 WriteMemoryByAddress ($3D) ................................ ................................ ...... 75 *(page 11)*
- 6 Additional features beyond AUTOSAR DCM 3.0 ................................ ........................ 78 *(page 11)*
- 6.1.1.1 AR 4.0 Like Memory Access Interface ................................ ........................... 78 *(page 11)*
- 6.2.2.1 Client Type and Service Group to Service Processor Unit Mapping .............. 80 *(page 11)*
- 12 / 163 *(page 12)*
- 6.2.2.3 Supported WWH-OBD services................................ ................................ ..... 84 *(page 12)*
- 6.2.2.4 Alternative OBD Interfaces to the DEM ................................ ......................... 85 *(page 12)*
- 6.4.2 Editing and Merging of the Code Template ................................ .................... 93 *(page 12)*
- 6.4.3 Template (Pseudo-) Implementations of Callback Functions ......................... 93 *(page 12)*
- 6.5 Support of Unspecified Services................................ ................................ .... 94 *(page 12)*
- 6.5.2 Implementation Specifics and Limitations ................................ ...................... 97 *(page 12)*
- 7.1 Implemented PIDs of ServiceId $01 ................................ .............................. 98 *(page 12)*
- 7.2 Implemented MIDs of ServiceId $06 ................................ .............................. 99 *(page 12)*
- 7.3 Implemented TIDs of ServiceId $08 ................................ .............................. 99 *(page 12)*
- 7.4 Implemented VIDs of ServiceId $09 ................................ .............................. 99 *(page 12)*
- 7.5 Implemented DIDs of ServiceId $22 ................................ ............................ 100 *(page 12)*
- 7.6 Implemented RIDs of ServiceId $31 ................................ ............................ 100 *(page 12)*
- 8.2 Services Provided by DCM ................................ ................................ .......... 102 *(page 12)*
- 13 / 163 *(page 13)*
- 8.3.2.1 Dcm_CheckUnspecifiedService ................................ ................................ .. 109 *(page 13)*
- 8.3.2.2 Dcm_HandleUnspecifiedService ................................ ................................ . 110 *(page 13)*
- 8.3.2.3 Dcm_PostHandleUnspecifiedService ................................ ........................... 111 *(page 13)*
- 8.4.1.1 Dcm_ComM_NoComModeEntered ................................ ............................. 115 *(page 13)*
- 8.4.1.2 Dcm_ComM_SilentComModeEntered ................................ ......................... 115 *(page 13)*
- 8.4.1.3 Dcm_ComM_FullComModeEntered ................................ ............................ 116 *(page 13)*
- 14 / 163 *(page 14)*
- 8.5.1.3 Implementation Hints for Port Usage ................................ ........................... 144 *(page 14)*
- 9.2.1 Common GENy usage hints ................................ ................................ ........ 147 *(page 14)*
- 9.2.3 CANdelaDiagnosticDocument import options ................................ .............. 153 *(page 14)*
- 9.2.4 Diagnostic Protocol Configuration ................................ ...............................  153 *(page 14)*
- 9.2.5 Diagnostic Connection Configuration ................................ .......................... 154 *(page 14)*
- 10.2.3 Multiple UUDT Message Transmission Support ................................ .......... 157 *(page 14)*
- 10.2.5 Jump into FBL on Request “Programming Session” ($10 $02) .................... 157 *(page 14)*
- 15 / 163 *(page 15)*
- 16 / 163 *(page 16)*
- 17 / 163 *(page 17)*
- 18 / 163 *(page 18)*
- 19 / 163 *(page 19)*
- 3.00 Creation. *(page 19)*
- 3.01 RAM/ROM optimizations and new configuration structure. *(page 19)*
- 3.02 RAM/ROM optimizations and new configuration structure. *(page 19)*
- 3.03 Full Link-time support, improvements, new features (see component header *(page 19)*
- 3.04 Support for NvM, IoHwAb, FBL, and VPM modules. *(page 19)*
- 3.05 Direct access to constants and A2L imported symbols. *(page 19)*
- 3.06 Direct access to fingerprint data. *(page 19)*
- 3.07 Minor changes and fixes only *(page 19)*
- 3.08 Security access delay time with NVRAM storage *(page 19)*
- 3.09 Automatic fingerprint and meta data OEM specific DID detection. *(page 19)*
- 3.10 Support for fingerprint write-operation. *(page 19)*
- 3.11 Improved memory access service optimization support by memory block *(page 19)*
- 3.12 Support for legislated OBD services. *(page 19)*
- 3.15 Service $31 (RoutineControl) service port extended to support dynamic *(page 19)*
- 4.00 Support for ISO14229-1 2009 *(page 19)*
