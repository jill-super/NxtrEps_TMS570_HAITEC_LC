---
title: "TechnicalReference Asr NvM"
description: "Converted from TechnicalReference_Asr_NvM.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_NvM.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (84 pages).

**Pages:** 84

---

This is a **84-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR NVM 
Technical Reference 
 
 
Version 3.07.00 
 
 
 
 
 
 
 
 
 
 
 
Authors Manfred Duschinger 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR NVM 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Christian Kaiser 2007-08-20 1.4 AUTOSAR 2.1, 
updated for EAD3.1 usage, 
conversion to new template 
Christian Kaiser 2007-12-06 3.01.00 Change of the document's versioning 
scheme to correspond to the module's 
major and minor, 
update of parameter description in 
chapter 'Graphical Configuration of NvM' 
and service port generation description, 
remove of DATASET ROM, feature not 
supported anymore, 
remove of introduction paragraphs from 
'Description of Memory Mapping and 
Compiler Abstraction', not subject of this 
document, 
simplified 'Block Management Types' 
naming, 
formal changes 
Christian Kaiser 2008-01-11 3.01.01 New chapter to clarify the dependency on 
the CRC library, 
stated explicitly that DET is optional, 
corrected default values 
Manfred Duschinger, 
Heike Bischof 
2008-05-23 3.02.00 AUTOSAR 3, 
conversion to Technical Reference 
Manfred Duschinger 2008-12-08 3.03.00 ESCAN00027300: Description of 
NvM_ServiceIdType in 
SingleBlockCallbackFunction and 
MultiBlockCallbackFunction 
Description and expected caller context 
of NvM_SetBlockLockStatus-API 
reworked. 
Chapter 4.4.17 ‘Concurrent access to NV 
data for DCM’ added. 
Chapter 4.4.5.2: Write order at redundant 
blocks added. 
Expansion of glossary. 
Chapter 7.2.2: Description of ‘Dataset 
Selection Bits’ added. 
©2011, Vector Informatik GmbH Version: 3.07.00 
based on template version 3.01 
2/ 8 4

Technical Reference MICROSAR NVM 
Manfred Duschinger 2009-02-25 3.03.01 ESCAN00031177: Manufacturer specific 
requirements attribute for traceability 
resons 
Manfred Duschinger 2009-03-24 3.03.02 ESCAN00032480: Missing information in 
documentation: 
Chapter 6.4.5: ‘Description of 
NvM_RequestResultType added’. 
Chapters 6.4.15 and 6.4.16: ‘Services are 
multiblock requests’. 
Manfred Duschinger 2009-06-03 3.04.00 ESCAN00032480: Update of History of 
version 3.03.02: Updated changed 
chapters. 
Chapter 6.2: ‘Block ID 0 is only allowed 
for API NvM_GetErrorStatus()’ 
ESCAN00033075: Chapter 4.5.1.1: 
DataIndex Check in NvM_ReadBlock() 
added. DataIndex Check was also added 
to NvM_InvalidateNvBlock() and 
NvM_EraseNvBlock(). 
ESCAN00033900: Chapter 4.4.17: 
“Priority Handling of DCM-Blocks” 
ESCAN00035089: Chapters 4.1, 7.2.2 
“Callbacks NvM_JobEndNotification, 
NvM_JobErrorNotification implemented” 
ESCAN00034073: Chpaters 2, 4.4.5.1, 
7.2.2 “Crc Handling is configurable: Either 
an internal buffer is used or Crc is stored 
at the end of RAM Block.” 
ESCAN00035891: Chapter 7.1.1 
“Integrate SWC-Generation into CFG 
Pro's Generation process” 
Chapter 3.1: update AUTOSAR 
architecture figure. 
Christian Kaiser 2010-01-25 3.04.01 ESCAN00039648 – Rebuilt document; 
made hyperlinks working. Updated Logo; 
No changes in content. 
Christian Kaiser 2010-03-26 3.05.00 Updated Component history 
Whole document: “EAD” Æ “DaVinci 
Configurator” 
Added Ch. 7.3 “Attributes only 
configurable using GCE” 
Updated Ch. 5.6.1 – “RAM Usage” 
ESCAN00040662: Chapter 4.4.3: Added 
note about restricted access to RAM 
block during job execution. 
ESCAN00035134: Chapter 5.1.2 
reworked 
©2011, Vector Informatik GmbH Version: 3.07.00 
based on template version 3.01 
3/ 8 4

Technical Reference MICROSAR NVM 
ESCAN00039749: Ch. 4.4.10, 8.2.4: 
Guaranteed CRC values; Ch 6.4.7: note 
about asynchronous CRC calculation 
ESCAN00031315: added Ch. 4.2.1, Ch 
8.2.3; updated Ch. 7.2.5 
ESCAN00042745 – corrected Ch. 4.5.2 
Manfred Duschinger 2011-01-25 3.07.00 ESCAN00047171: Ch. 6.4.18: 
NvM_KillWriteAll; Abbreviations: ECUM 
ESCAN00045141: Ch. 4.4.5.1: 
information about names of Block 
Handles 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_NVRAMManager.pdf V 2.2.0 
[2] AUTOSAR_SWS_DET.pdf V 2.2.0 
[3] AUTOSAR_SWS_DEM.pdf V 2.2.1 
[4] AUTOSAR_BasicSoftwareModules.pdf V 1.2.0 
Table 1-2 Reference documents 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
©2011, Vector Informatik GmbH Version: 3.07.00 
based on template version 3.01 
4/ 8 4

Technical Reference MICROSAR NVM 
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 4 
2 Component History....................................................................................................... 11 
3 Introduction ................................................................................................................... 12 
3.1 Architecture Overview..................................................................................... 13 
4 Functional Description ................................................................................................. 15 
4.1 Features.......................................................................................................... 15 
4.2 Initialization ..................................................................................................... 15 
4.2.1 Block Size Checks .......................................................................................... 16 
4.2.2 Start-up ........................................................................................................... 17 
4.2.3 Initialization of the Data Blocks....................................................................... 17 
4.3 States.............................................................................................................. 18 
4.4 Main Functions ............................................................................................... 18 
4.4.1 Hardware Independence ................................................................................ 18 
4.4.2 Synchronous Requests................................................................................... 18 
4.4.3 Asynchronous Requests................................................................................. 18 
4.4.4 API Configuration Classes and additional API Services ................................. 19 
4.4.5 Block Handling................................................................................................ 20 
4.4.5.1 NV Blocks and Block Handles ........................................................................ 20 
4.4.5.2 Different Types of NV Blocks .......................................................................... 21 
4.4.5.3 Permanent and non-permanent RAM Blocks ................................................. 22 
4.4.5.4 ROM Defaults ................................................................................................. 23 
4.4.5.5 Checksum....................................................................................................... 23 
4.4.6 Prioritized or non-prioritized Queuing of asynchronous Requests.................. 23 
4.4.7 Asynchronous Job-End Polling....................................................................... 23 
4.4.8 Asynchronous Job-End Notification................................................................ 23 
4.4.9 Immediate Priority Jobs and Cancellation of current Jobs.............................. 24 
4.4.10 Asynchronous CRC Calculation ..................................................................... 24 
4.4.11 Write Protection .............................................................................................. 25 
4.4.12 Erase and Invalidate ....................................................................................... 25 
4.4.13 Init Callbacks .................................................................................................. 25 
4.4.14 Define Locking/ Unlocking Services ............................................................... 25 
4.4.15 Interrupts......................................................................................................... 26 
4.4.16 Data Corruption .............................................................................................. 26 
©2011, Vector Informatik GmbH Version: 3.07.00 
based on template version 3.01 
5/ 8 4

Technical Reference MICROSAR NVM 
4.4.17 Concurrent access to NV data for DCM.......................................................... 26 
4.4.18 Removed Functionality ................................................................................... 26 
4.4.19 Changed Functionality .................................................................................... 27 
4.5 Error Handling................................................................................................. 27 
4.5.1 Development Error Reporting ......................................................................... 27 
4.5.1.1 Parameter Checking ....................................................................................... 28 
4.5.2 Production Code Error Reporting ................................................................... 29 
5 Integration .....................................................................................................................3 1 
5.1 Scope of Delivery............................................................................................ 31 
5.1.1 Static Files ...................................................................................................... 31 
5.1.2 Dynamic Files ................................................................................................. 32 
5.2 Include Structure............................................................................................. 32 
5.3 Compiler Abstraction and Memory Mapping................................................... 33 
5.4 Dependencies on SW Modules ...................................................................... 34 
5.4.1 OSEK / AUTOSAR OS.................................................................................... 34 
5.4.2 DEM................................................................................................................ 34 
5.4.3 DET................................................................................................................. 34 
5.4.4 MEMIF ............................................................................................................ 34 
5.4.5 CRC Library .................................................................................................... 34 
5.4.6 Callback Functions ......................................................................................... 34 
5.4.7 RTE................................................................................................................. 35 
5.5 Integration Steps............................................................................................. 35 
5.6 Estimating Resource Consumption ................................................................ 35 
5.6.1 RAM Usage .................................................................................................... 36 
5.6.2 ROM Usage .................................................................................................... 36 
5.6.3 NV Usage ....................................................................................................... 36 
6 API Description ...............................................................................................

## Extracted outline

- Microsar Nvm *(page 1)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 2008-05-23 3.02.00 Autosar 3, *(page 2)*
- 7.2.2 “Crc Handling is configurable: Either *(page 3)*
- 1.2 Reference Documents *(page 4)*
- 4.4.4 API Configuration Classes and additional API Services ................................. 19 *(page 5)*
- 4.4.5.3 Permanent and non-permanent RAM Blocks ................................................. 22 *(page 5)*
- 4.4.6 Prioritized or non-prioritized Queuing of asynchronous Requests.................. 23 *(page 5)*
- 4.4.7 Asynchronous Job-End Polling....................................................................... 23 *(page 5)*
- 4.4.8 Asynchronous Job-End Notification................................................................ 23 *(page 5)*
- 4.4.9 Immediate Priority Jobs and Cancellation of current Jobs.............................. 24 *(page 5)*
- 4.4.10 Asynchronous CRC Calculation ..................................................................... 24 *(page 5)*
- 4.4.14 Define Locking/ Unlocking Services ............................................................... 25 *(page 5)*
- 4.4.17 Concurrent access to NV data for DCM.......................................................... 26 *(page 6)*
- 4.5.2 Production Code Error Reporting ................................................................... 29 *(page 6)*
- 5.3 Compiler Abstraction and Memory Mapping................................................... 33 *(page 6)*
- 5.4 Dependencies on SW Modules ...................................................................... 34 *(page 6)*
- 5.6 Estimating Resource Consumption ................................................................ 35 *(page 6)*
- 6.4 Services provided by NVM ............................................................................. 40 *(page 6)*
- 6.4.7 NvM_SetRamBlockStatus............................................................................... 44 *(page 6)*
- 7.1 Software Component Template....................................................................... 59 *(page 7)*
- 7.1.3 Dependencies on Configuration of NVM Attributes......................................... 62 *(page 7)*
- 7.2 Configuration of NVM Attributes ..................................................................... 63 *(page 7)*
- 7.3 Attributes only configurable using GCE .......................................................... 78 *(page 8)*
- 8.2.2 Concurrent access to NV data........................................................................ 80 *(page 8)*
- 8.2.3 RAM-/ROM Block Size checks ....................................................................... 80 *(page 8)*
- 8.2.4 Calculated CRC value does not depend on number of calculation steps ....... 80 *(page 8)*
- 10 / 84 *(page 10)*
- 2 Component History *(page 11)*
- 11 / 84 *(page 11)*
- 3 Introduction *(page 12)*
- Microsar Nvm! *(page 12)*
- 12 / 84 *(page 12)*
- 3.1 Architecture Overview *(page 13)*
- 13 / 84 *(page 13)*
- 14 / 84 *(page 14)*
- 4 Functional Description *(page 15)*
- 4.1 Features *(page 15)*
- 4.2 Initialization *(page 15)*
- 15 / 84 *(page 15)*
- 4.2.1 Block Size Checks *(page 16)*
- 16 / 84 *(page 16)*
- 4.2.2 Start-up *(page 17)*
- 4.2.3 Initialization of the Data Blocks *(page 17)*
- 17 / 84 *(page 17)*
- 4.3 States *(page 18)*
- 4.4 Main Functions *(page 18)*
- 4.4.1 Hardware Independence *(page 18)*
- 4.4.2 Synchronous Requests *(page 18)*
- 4.4.3 Asynchronous Requests *(page 18)*
- 18 / 84 *(page 18)*
- 4.4.4 API Configuration Classes and additional API Services *(page 19)*
- 19 / 84 *(page 19)*
- 4.4.5 Block Handling *(page 20)*
- 4.4.5.1 NV Blocks and Block Handles *(page 20)*
- 20 / 84 *(page 20)*
- 4.4.5.2 Different Types of NV Blocks *(page 21)*
- 21 / 84 *(page 21)*
- 4.4.5.3 Permanent and non-permanent RAM Blocks *(page 22)*
- 22 / 84 *(page 22)*
- 4.4.5.4 ROM Defaults *(page 23)*
- 4.4.5.5 Checksum *(page 23)*
- 4.4.6 Prioritized or non-prioritized Queuing of asynchronous Requests *(page 23)*
- 4.4.7 Asynchronous Job-End Polling *(page 23)*
- 4.4.8 Asynchronous Job-End Notification *(page 23)*
- 23 / 84 *(page 23)*
- 4.4.9 Immediate Priority Jobs and Cancellation of current Jobs *(page 24)*
- 4.4.10 Asynchronous CRC Calculation *(page 24)*
- 24 / 84 *(page 24)*
- 4.4.11 Write Protection *(page 25)*
- 4.4.12 Erase and Invalidate *(page 25)*
- 4.4.13 Init Callbacks *(page 25)*
- 4.4.14 Define Locking/ Unlocking Services *(page 25)*
- 25 / 84 *(page 25)*
- 4.4.15 Interrupts *(page 26)*
- 4.4.16 Data Corruption *(page 26)*
- 4.4.17 Concurrent access to NV data for DCM *(page 26)*
- 4.4.18 Removed Functionality *(page 26)*
- 26 / 84 *(page 26)*
- 4.4.19 Changed Functionality *(page 27)*
- 4.5 Error Handling *(page 27)*
- 4.5.1 Development Error Reporting *(page 27)*
- 27 / 84 *(page 27)*
- Ected *(page 28)*
- Ata_Idx *(page 28)*
- 4.5.1.1 Parameter Checking *(page 28)*
- 28 / 84 *(page 28)*
- 4.5.2 Production Code Error Reporting *(page 29)*
- 29 / 84 *(page 29)*
- 30 / 84 *(page 30)*
- 5 Integration *(page 31)*
- 5.1 Scope of Delivery *(page 31)*
- 5.1.1 Static Files *(page 31)*
- 31 / 84 *(page 31)*
- 32 / 84 *(page 32)*
- 5.1.2 Dynamic Files *(page 32)*
- 5.2 Include Structure *(page 32)*
- 5.3 Compiler Abstraction and Memory Mapping *(page 33)*
- Nvm_Private_Code *(page 33)*
- Nvm_Private_Cons *(page 33)*
- Nvm_Private_Data *(page 33)*
- Nvm_Fast_Data *(page 33)*
- Nvm_Public_Code *(page 33)*
- Nvm_Public_Const *(page 33)*
- Nvm_Appl_Code *(page 33)*
- Nvm_Appl_Const *(page 33)*
- Nvm_Appl_Data *(page 33)*
- Nvm_Config_Cons *(page 33)*
- Nvm_Config_Data *(page 33)*
- Nvm_Start_Sec_Code *(page 33)*
- Nvm_Start_Sec_ *(page 33)*
- Var_Noinit_Unspecified *(page 33)*
- Nvm_Start_Sec_Var_Noinit_8 *(page 33)*
- Nvm_Start_Sec_Var_Unspecif *(page 33)*
- Nvm_Start_Sec_Var_Fast_8Bi *(page 33)*
- Const_Unspecified *(page 33)*
- Nvm_Start_Sec_Const_8Bit *(page 33)*
- Nvm_Start_Sec_Const_16Bit *(page 33)*
- Const_Descriptor_Table *(page 33)*
