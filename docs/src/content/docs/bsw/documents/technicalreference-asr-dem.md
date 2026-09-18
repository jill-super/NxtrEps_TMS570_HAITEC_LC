---
title: "TechnicalReference Asr Dem"
description: "Converted from TechnicalReference_Asr_Dem.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_Dem.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (127 pages).

**Pages:** 127

---

This is a **127-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR Diagnostic Event Manager 
(DEM) 
Technical Reference 
 
Vector 
Version 2.2.0 
 
 
 
 
 
 
 
 
 
 
 
Authors P. Speidel, A. Ditte, S. Hübner 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR Diagnostic Event Manager (DEM) 
1 Document Information 
1.1 History 
Author Date Version Remarks 
P. Stöhr 2008-04-08 1.0 Created for OEM “Vector” base of 
TechnicalReference_DEM_<OEM>.doc 
P . Stöhr 2008-06-18 1.0.1 Updated to AUTOSAR Release 3 
P . Stöhr 2008-06-19 1.0.2 Added reference [8] 
P . Stöhr 2008-06-27 1.0.3 Modified description of configuration 
P . Stöhr 2009-01-08 2.0.10 Modified include structure, added chapter NvRAM 
Demand, added FreezeFrame descriptions, updated 
description of configuration, added description of 
scheduling DEM and DCM 
P . Stöhr 2009-02-16 2.0.13 Added internal OccurrenceCounter implementation 
A. Ditte 2009-04-14 2.0.14 Added description for event de-bouncing 
Added DEM_E_INV_TIMER_SLOT_VAL in chapter 4.6.1 
S. Hübner 2009-08-21 2.1.2 Update R7, DEM 2.08.00 
Added Variant Handling (Single Identity/VSG mode) 
B. Freiberger 2009-11-11 2.1.3 Add detailed description of AUTOSAR APIs 
P . Speidel 2010-03-03 2.1.4 Add information to “post-build settings” description, 
Add ApiId of Xxx_DemGetExtededDtataRecford in 
chapter 4.6.1, 
Update caller context information, 
Updated indicator description (configuration of 
IndicatorBit is now possible in CANdela and GENy) 
S. Hübner 2010-08-23 2.1.5 Release Dem in config variant link-time, only 
S. Hübner 2010-12-01 2.2.0 Due sleep/wakeup constraints, no check any more for 
NV-Block status in Dem 2.14.00, see chapter 4.2 for 
mandatory configuration/initialization. 
GENy (Diag_AsrDem.dll 3.3.0.0) now separates 
Internal/External Events (Event Destination) from 
creation of PortInterface (Event Kind). Reworked 
chapter 8.1.1, 8.2.12.5 and 10.1 
Table 1-1 History of the Document 
 
©2010, Vector Informatik GmbH Version: 2.2.0 
based on template version 3.2 
2 / 127

Technical Reference MICROSAR Diagnostic Event Manager (DEM) 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR - Specification of Diagnostics Event Manager 
(AUTOSAR_SWS_DEM.pdf) 
V2.2.1 
[2] AUTOSAR – Specification of Development Error Tracer 
(AUTOSAR_SWS_DET.pdf) 
V2.2.0 
[3] AUTOSAR – Specification of Diagnostic Communication Manager 
(AUTOSAR_SWS_DCM.pdf) 
V3.0.0 
[4] AUTOSAR – Specification of NVRAM Manager 
(AUTOSAR_SWS_NVRAMManager.pdf) 
V2.2.0 
[5] AUTOSAR – Specification of Standard Types 
(AUTOSAR_SWS_StandardTypes.pdf) 
V1.2.0 
[6] AUTOSAR_BasicSoftwareModules.pdf V1.0.0 
[7] ISO 14229-1:2006 Road vehicles – Unified diagnostic services (UDS) – Part 1: 
Specification and Requirements 
- 
[8] Vector internal PostBuild_GeneralProcedure.pdf V1.x 
[9] Application Note AN-ISC-8-1118, Vector GmbH 
MICROSAR BSW Compatibility Check 
V1.0 
Table 1-2 Reference Documents 
©2010, Vector Informatik GmbH Version: 2.2.0 
based on template version 3.2 
3 / 127

Technical Reference MICROSAR Diagnostic Event Manager (DEM) 
Contents 
1 Document Information..................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 3 
2 Component History........................................................................................................ 12 
3 Introduction ....................................................................................................................1 3 
3.1 Architecture Overview..................................................................................... 13 
4 Functional Description .................................................................................................. 15 
4.1 Features.......................................................................................................... 15 
4.2 Initialization ..................................................................................................... 16 
4.3 States.............................................................................................................. 17 
4.4 Main Functions ............................................................................................... 18 
4.5 Event De-bouncing ......................................................................................... 20 
4.5.1 Via Counter Based Algorithm.......................................................................... 20 
4.5.2 Via Time Based Algorithm............................................................................... 20 
4.6 Error Handling................................................................................................. 21 
4.6.1 Development Error Reporting ......................................................................... 21 
4.6.1.1 Parameter Checking ....................................................................................... 28 
4.6.2 Production Code Error Reporting ................................................................... 31 
5 Integration....................................................................................................................... 32 
5.1 Scope of Delivery............................................................................................ 32 
5.1.1 Static Files ...................................................................................................... 32 
5.1.2 Dynamic Files ................................................................................................. 32 
5.2 Include Structure............................................................................................. 33 
5.3 Compiler Abstraction and Memory Mapping................................................... 34 
5.4 Critical Sections .............................................................................................. 35 
5.4.1 Startup Phase ................................................................................................. 35 
5.4.2 Call of Callback Functions .............................................................................. 36 
5.5 Call Context .................................................................................................... 36 
5.6 Scheduling of DEM and DCM......................................................................... 37 
5.7 NvRAM Demand............................................................................................. 37 
6 API Description .............................................................................................................. 39 
6.1 Type Definitions .............................................................................................. 39 
6.2 Services Provided by DEM ............................................................................. 39 
©2010, Vector Informatik GmbH Version: 2.2.0 
based on template version 3.2 
4 / 127

Technical Reference MICROSAR Diagnostic Event Manager (DEM) 
6.2.1 Dem_GetVersionInfo ...................................................................................... 39 
6.2.2 Interface ECU State Manager Ù DEM ........................................................... 39 
6.2.2.1 Dem_PreInit.................................................................................................... 39 
6.2.2.2 Dem_Init ......................................................................................................... 41 
6.2.2.3 Dem_Shutdown .............................................................................................. 41 
6.2.2.4 Dem_InitDiagnosticVariant.............................................................................. 42 
6.2.3 Interface SW-Components via RTE Ù DEM .................................................. 44 
6.2.3.1 Dem_SetEventStatus...................................................................................... 44 
6.2.3.2 Dem_ResetEventStatus.................................................................................. 45 
6.2.3.3 Dem_PrestoreFreezeFrame ........................................................................... 46 
6.2.3.4 Dem_ClearPrestoredFreezeFrame ................................................................ 47 
6.2.3.5 Dem_SetOperationCycleState........................................................................ 47 
6.2.3.6 Dem_GetEventStatus ..................................................................................... 49 
6.2.3.7 Dem_GetEventFailed ..................................................................................... 50 
6.2.3.8 Dem_GetEventTested..................................................................................... 50 
6.2.3.9 Dem_GetDTCOfEvent .................................................................................... 52 
6.2.3.10 Dem_SetValueByOemId................................................................................. 52 
6.2.3.11 Dem_SetEnableCondition .............................................................................. 52 
6.2.3.12 Dem_GetFaultDetectionCounter .................................................................... 53 
6.2.3.13 Dem_GetIndicatorStatus................................................................................. 53 
6.2.3.14 Dem_GetOccurrenceCounter ......................................................................... 55 
6.2.4 Interface BSW-Components Ù DEM ............................................................. 56 
6.2.4.1 Dem_ReportErrorStatus ................................................................................. 56 
6.2.5 Interface DCM Ù DEM................................................................................... 57 
6.2.5.1 Access DTCs and Status Information ............................................................. 57 
6.2.5.1.1 Dem_SetDTCFilter ......................................................................................... 58 
6.2.5.1.2 Dem_SetDTCFilterForRecords....................................................................... 59 
6.2.5.1.3 Dem_SetViewFilter ......................................................................................... 60 
6.2.5.1.4 Dem_GetStatusOfDTC ................................................................................... 60 
6.2.5.1.5 Dem_GetDTCStatusAvailabilityMask.............................................................. 61 
6.2.5.1.6 Dem_GetNumberOfFilteredDTC .................................................................... 61 
6.2.5.1.7 Dem_GetNextFilteredDTC.............................................................................. 62 
6.2.5.1.8 Dem_GetDTCByOccurrenceTime .................................................................. 63 
6.2.5.1.9 Dem_GetViewIDOfDTC.................................................................................. 64 
6.2.5.1.10 Dem_GetNextFilteredRecord ......................................................................... 64 
6.2.5.1.11 Dem_GetNextFilteredDTCAndFDC................................................................ 65 
6.2.5.1.12 Dem_GetNextFilteredDTCAndSeverity .......................................................... 66 
6.2.5.1.13 Dem_GetTranslationType ............................................................................... 66 
6.2.5.1.14 Dem_GetSeverityOfDTC ................................................................................ 67 
6.2.5.2 Access Extended Data Records and FreezeFrame Data ............................... 68 
6.2.5.2.1 Dem_DisableDTCRecordUpdate.................................................................... 68 
©2010, Vector Informatik GmbH Version: 2.2.0 
based on template version 3.2 
5 / 127

Technical Reference MICROSAR Diagnostic Event Manager (DEM) 
6.2.5.2.2 Dem_EnableDTCRecordUpdate ..................................................

## Extracted outline

- (Dem) *(page 1)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 2 / 127 *(page 2)*
- 1.2 Reference Documents *(page 3)*
- V2.2.1 *(page 3)*
- V2.2.0 *(page 3)*
- V3.0.0 *(page 3)*
- V1.2.0 *(page 3)*
- 3 / 127 *(page 3)*
- 4.6.2 Production Code Error Reporting ................................................................... 31 *(page 4)*
- 5.3 Compiler Abstraction and Memory Mapping................................................... 34 *(page 4)*
- 5.6 Scheduling of DEM and DCM......................................................................... 37 *(page 4)*
- 6.2 Services Provided by DEM ............................................................................. 39 *(page 4)*
- 4 / 127 *(page 4)*
- 6.2.2 Interface ECU State Manager Ù DEM ........................................................... 39 *(page 5)*
- 6.2.3 Interface SW-Components via RTE Ù DEM .................................................. 44 *(page 5)*
- 6.2.3.4 Dem_ClearPrestoredFreezeFrame ................................................................ 47 *(page 5)*
- 6.2.3.5 Dem_SetOperationCycleState........................................................................ 47 *(page 5)*
- 6.2.3.12 Dem_GetFaultDetectionCounter .................................................................... 53 *(page 5)*
- 6.2.4 Interface BSW-Components Ù DEM ............................................................. 56 *(page 5)*
- 6.2.5.1 Access DTCs and Status Information ............................................................. 57 *(page 5)*
- 6.2.5.2 Access Extended Data Records and FreezeFrame Data ............................... 68 *(page 5)*
- 5 / 127 *(page 5)*
- 6.5.1.1 Rte_Call_Dem_<ConfiguredName>_InitMonitorForEvent.............................. 83 *(page 6)*
- 6.5.1.2 Rte_Call_Dem_<ConfiguredName>_EventStatusChanged ........................... 84 *(page 6)*
- 6.5.1.3 Rte_Call_Dem_<ConfiguredName>_DTCStatusChanged ............................. 86 *(page 6)*
- 6.5.2.1 Rte_Call_Dem_<ConfiguredName>_GetDataValueByDataIdentifier ............. 87 *(page 6)*
- 6.5.2.2 Rte_Call_Dem_<ConfiguredName>_GetExtendedDataRecord..................... 88 *(page 6)*
- 6 / 127 *(page 6)*
- 7.1.3 Vehicle System Group (VSG) Mode ............................................................... 94 *(page 7)*
- 8.1 Configuration with CANdelaStudio.................................................................. 97 *(page 7)*
- 8.1.2 Freeze Frame Types (Snapshot Records)...................................................... 99 *(page 7)*
- 8.2.2.2 Vehicle System Group (VSG) Mode ............................................................. 103 *(page 7)*
- 8.2.2.3 Automatic Configuration via CANdelaStudio Files........................................ 104 *(page 7)*
- 8.2.4 Main Configuration Window.......................................................................... 106 *(page 7)*
- 8.2.6 Software Component Template..................................................................... 107 *(page 7)*
- 7 / 127 *(page 7)*
- 8.2.13 Software Component Template..................................................................... 121 *(page 8)*
- 9.1.1 APIs and Features not Supported ................................................................ 122 *(page 8)*
- 9.1.2 AUTOSAR Defined APIs that Differ in this Implementation .......................... 122 *(page 8)*
- 9.1.2.2 Service Dem_SetEventStatus....................................................................... 122 *(page 8)*
- 9.1.2.3 Service Dem_ResetEventStatus................................................................... 122 *(page 8)*
- 9.1.2.4 Service Dem_SetOperationCycleState......................................................... 122 *(page 8)*
- 9.1.2.5 Service Dem_ReportErrorStatus................................................................... 122 *(page 8)*
- 9.1.2.6 Interface Rte_Call_Dem_<ConfiguredName>_DTCStatusChanged ............ 122 *(page 8)*
- 9.2.1 Development Error Reporting – Include Structure ........................................ 123 *(page 8)*
- 9.2.2 Development Error Reporting – Internal Debug Codes ................................ 123 *(page 8)*
- 9.2.3 Service Dem_GetOccurrenceCounter .......................................................... 123 *(page 8)*
- 9.2.4 Name Description of Configurable Interfaces (Notifications) ........................ 123 *(page 8)*
- 9.2.5 Interface *(page 8)*
- 9.2.6 Port Names Length Limitation....................................................................... 123 *(page 8)*
- 9.3.1 Limits Checked During Configuration ........................................................... 124 *(page 8)*
- 8 / 127 *(page 8)*
- 9 / 127 *(page 9)*
- 10 / 127 *(page 10)*
- 11 / 127 *(page 11)*
- 2 Component History *(page 12)*
- 12 / 127 *(page 12)*
- 3 Introduction *(page 13)*
- 3.1 Architecture Overview *(page 13)*
- 13 / 127 *(page 13)*
- Ecu-Sm *(page 14)*
- Dcmdem *(page 14)*
- Nvram *(page 14)*
- 14 / 127 *(page 14)*
- 4 Functional Description *(page 15)*
- 4.1 Features *(page 15)*
- E_Not_Ok). *(page 15)*
- 15 / 127 *(page 15)*
- 16 / 127 *(page 16)*
- 4.2 Initialization *(page 16)*
- 1 In multiple identity mode (see chapter 7.1) the active configuration must be chosen before calling *(page 16)*
- 8.2.11 NvRam Block IDs *(page 17)*
- 4.3 States *(page 17)*
- 17 / 127 *(page 17)*
- 4.4 Main Functions *(page 18)*
- 18 / 127 *(page 18)*
- 19 / 127 *(page 19)*
- 20 / 127 *(page 20)*
- 4.5 Event De-bouncing *(page 20)*
- 4.5.1 Via Counter Based Algorithm *(page 20)*
- 4.5.2 Via Time Based Algorithm *(page 20)*
- 21 / 127 *(page 21)*
- 219 220191817 *(page 21)*
- 4.6 Error Handling *(page 21)*
- 4.6.1 Development Error Reporting *(page 21)*
- Address *(page 22)*
- Config *(page 22)*
- Active_Variant *(page 22)*
- 22 / 127 *(page 22)*
- 23 / 127 *(page 23)*
- Overflow *(page 23)*
- 24 / 127 *(page 24)*
- Dem_E_Param_ *(page 24)*
- 25 / 127 *(page 25)*
- 26 / 127 *(page 26)*
- Many_Indicator *(page 26)*
- Ailable *(page 26)*
- 27 / 127 *(page 27)*
- Variant *(page 27)*
- 4.6.1.1 Parameter Checking *(page 28)*
- Dem_Dev_Error_Detect. *(page 28)*
- 28 / 127 *(page 28)*
- 29 / 127 *(page 29)*
- 30 / 127 *(page 30)*
- 4.6.2 Production Code Error Reporting *(page 31)*
- 31 / 127 *(page 31)*
- 5 Integration *(page 32)*
- 5.1 Scope of Delivery *(page 32)*
- 5.1.1 Static Files *(page 32)*
- 5.1.2 Dynamic Files *(page 32)*
- 32 / 127 *(page 32)*
- 33 / 127 *(page 33)*
- 5.2 Include Structure *(page 33)*
- {Dem_Dev_Error_Detect} *(page 33)*
- 5.3 Compiler Abstraction and Memory Mapping *(page 34)*
- Dem_Code *(page 34)*
- Dem_Var_Noinit_Fast *(page 34)*
- Dem_Var *(page 34)*
