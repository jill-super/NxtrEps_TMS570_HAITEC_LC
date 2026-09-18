---
title: "TechnicalReference Asr IoHwAb"
description: "Converted from TechnicalReference_Asr_IoHwAb.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_Asr_IoHwAb.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (48 pages).

**Pages:** 48

---

This is a **48-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR IOHWAB 
Technical Reference 
 
 
Version 2.02.02 
 
 
 
 
 
 
 
 
 
 
 
Authors Christoph Ederer 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR IOHWAB 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Christian Marchl 2007-02-09 1.00.00 Initial version 
Christian Marchl 2007-08-09 1.01.00 Typos corrected; Added 
description for component 
name field 
Christian Marchl 2007-12-13 1.01.01 Version adapted according to 
new version scheme 
Christoph Ederer 2008-05-21 2.00.00 Transfer of the document to 
new Technical Reference 
template; Adapted 
descriptions and screenshots 
to new software version 
Christoph Ederer 2008-07-11 2.00.01 Update of document due to 
changes in DCM interface 
and RTE usage 
Christoph Ederer 2009-01-14 2.01.00 Update of the naming of 
graphical elements in the 
configuration, Screenshots 
reworked, DCM subfunctions 
reworked, Added description 
of default value in 
configuration 
Christoph Ederer 2009-03-23 2.01.01 Updated development error 
detection in GUI description, 
toolchain naming updated, 
hints added to chapter 4.1.2 
Christoph Ederer 2009-07-21 2.02.00 Updated description of the 
generation process (user 
blocks, autom. SWC 
generation), updated 
AUTOSAR figure, added 
information on user defined 
signals 
Christoph Ederer 2009-09-25 2.02.01 Reworked description of DCM
interface 
Christoph Ederer 2010-11-26 2.02.02 - Added chapter 4.4 Critical 
Sections 
- GUI description updated 
- Added information about 
necessary make process 
modifications to 4.1.2 
(ESCAN00047210) 
©2010, Vector Informatik GmbH Version: 2.02.02 
based on template version 3.1 
2/ 4 8

Technical Reference MICROSAR IOHWAB 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_IO_HWAbstraction.pdf V2.0.0 
[2] AUTOSAR_SWS_DET.pdf V2.2.0 
[3] AUTOSAR_BasicSoftwareModules.pdf V1.2.0 
Table 1-2 Reference documents 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector´s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
 
 
©2010, Vector Informatik GmbH Version: 2.02.02 
based on template version 3.1 
3/ 4 8

Technical Reference MICROSAR IOHWAB 
Contents 
1 Document Information.................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 3 
2 Introduction ..................................................................................................................... 8 
2.1 Architecture Overview....................................................................................... 9 
3 Functional Description ................................................................................................. 11 
3.1 Features...........................................................................................................11 
3.2 Initialization ......................................................................................................11 
3.3 States.............................................................................................................. 12 
3.4 Main Functions ............................................................................................... 12 
3.5 Error Handling................................................................................................. 12 
3.5.1 Development Error Reporting ......................................................................... 12 
3.5.1.1 Parameter Checking ....................................................................................... 13 
3.5.2 Production Code Error Reporting ................................................................... 13 
4 Integration .....................................................................................................................1 4 
4.1 Scope of Delivery............................................................................................ 14 
4.1.1 Static Files ...................................................................................................... 14 
4.1.2 Dynamic Files ................................................................................................. 14 
4.2 Include Structure............................................................................................. 16 
4.3 Compiler Abstraction and Memory Mapping................................................... 16 
4.4 Critical Sections .............................................................................................. 17 
4.5 Generated Template Files............................................................................... 17 
4.5.1 Generated services in template files............................................................... 18 
5 API Description ............................................................................................................. 20 
5.1 Interfaces Overview ........................................................................................ 20 
5.2 Type Definitions .............................................................................................. 21 
5.3 Services provided by IOHWAB ....................................................................... 22 
5.3.1 IoHwAb_Init .................................................................................................... 22 
5.3.2 IoHwAb_GetVersionInfo ................................................................................. 22 
5.4 Generated API functions................................................................................. 23 
5.4.1 IoHwAb_Set<CalSignalName>....................................................................... 23 
5.4.2 IoHwAb_Get<CalSignalName> ...................................................................... 24 
5.4.3 IoHwAb_DCM_<CalSignalName>.................................................................. 25 
5.4.4 IoHwAb_DCM_Read<CalSignalName> ......................................................... 26 
©2010, Vector Informatik GmbH Version: 2.02.02 
based on template version 3.1 
4/ 4 8

Technical Reference MICROSAR IOHWAB 
5.4.5 IoHwAb_Diag<CalSignalName>..................................................................... 27 
5.4.6 IoHwAb_Input<UserDefSignalName> ............................................................ 28 
5.4.7 IoHwAb_DCM_Input<UserDefSignalName> .................................................. 29 
5.4.8 IoHwAb_DCM_Read<UserDefSignalName> ................................................. 30 
5.4.9 IoHwAb_Output<UserDefSignalName> ......................................................... 31 
5.4.10 IoHwAb_DCM_Output<UserDefSignalName> ............................................... 32 
5.4.11 IoHwAb_<SignalHandlerName>..................................................................... 33 
5.5 Services used by IOHWAB ............................................................................. 33 
5.6 Callback Functions ......................................................................................... 34 
5.7 Configurable Interfaces................................................................................... 34 
5.7.1 Notifications .................................................................................................... 34 
5.8 Service Ports .................................................................................................. 34 
5.8.1 Client Server Interface .................................................................................... 34 
5.8.1.1 Provide Ports .................................................................................................. 34 
5.8.1.2 Require Ports.................................................................................................. 35 
5.9 Software Component Template....................................................................... 35 
5.9.1 Generation ...................................................................................................... 35 
5.9.2 Import to the DaVinci modeling tool................................................................ 35 
6 Configuration ................................................................................................................ 37 
6.1 Configuration of IOHWAB with DaVinci Configurator...................................... 37 
6.1.1 Start configuration of the IOHWAB ................................................................. 37 
6.1.2 Tab ‘IoHwAb Configuration’ ............................................................................ 37 
6.1.2.1 Node ‘IoHwAbCalSignals’............................................................................... 37 
6.1.2.1.1 Node ‘IoHwAbDiscrete’................................................................................... 38 
6.1.2.2 Node ‘IoHwAbUserDefSignals’ ....................................................................... 39 
6.1.2.2.1 Node ‘IoHwAbUserDefPort’ ............................................................................ 39 
6.1.2.3 Node ‘IoHwAbHandlers’.................................................................................. 41 
6.1.2.3.1 Node ‘IoHwAbHandler’ ................................................................................... 42 
6.1.2.4 Node IoHwAbDataTypeSizes.......................................................................... 42 
6.1.3 Tab ‘General Settings’..................................................................................... 42 
6.1.3.1 Area ‘Error Detection – Development Mode’ .................................................. 42 
6.1.3.2 Area ‘Interrupt Services’ ................................................................................. 43 
6.1.3.3 Area ‘Common Settings’ ................................................................................. 44 
6.1.3.4 Area ‘Include List’ ........................................................................................... 45 
6.1.4 Tab ‘Module API’ ............................................................................................. 45 
6.1.4.1 Area ‘API Optimization’................................................................................... 45 
7 AUTOSAR Standard Compliance................................................................................. 46 
8 Glossary and Abbreviations ........................................................................................ 47 
©2010, Vector Informatik GmbH Version: 2.02.02 
based on template version 3.1 
5/ 4 8

Technical Reference MICROSAR IOHWAB 
8.1 Glossary.......................................................................................................... 47 
8.2 Abbreviations .................................................................................................. 47 
9 Contact........................................................................................................................... 48 
 
©2010, Vector Informatik GmbH Version: 2.02.02 
based on template version 3.1 
6/ 4 8

Technical Reference MICROSAR IOHWAB 
Illustrations 
Figure 2-1 AUTOSAR architecture..................................................................................... 9 
Figure 2-2 Interfaces to adjacent modules of the IOHWAB ............................................. 10 
Figure 4-1 Include structure ............................................................................................. 16 
Figure 5-1 IOHWAB interactions with other BSW ............................................................ 20 
Figure 5-2 Import 

## Extracted outline

- Microsar Iohwab *(page 1)*
- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- (Escan00047210) *(page 2)*
- 1.2 Reference Documents *(page 3)*
- 3.5.2 Production Code Error Reporting ................................................................... 13 *(page 4)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 16 *(page 4)*
- 4.5.1 Generated services in template files............................................................... 18 *(page 4)*
- 5.3 Services provided by IOHWAB ....................................................................... 22 *(page 4)*
- 5.4.1 IoHwAb_Set<CalSignalName>....................................................................... 23 *(page 4)*
- 5.4.2 IoHwAb_Get<CalSignalName> ...................................................................... 24 *(page 4)*
- 5.4.3 IoHwAb_DCM_<CalSignalName>.................................................................. 25 *(page 4)*
- 5.4.4 IoHwAb_DCM_Read<CalSignalName> ......................................................... 26 *(page 4)*
- 5.4.5 IoHwAb_Diag<CalSignalName>..................................................................... 27 *(page 5)*
- 5.4.6 IoHwAb_Input<UserDefSignalName> ............................................................ 28 *(page 5)*
- 5.4.7 IoHwAb_DCM_Input<UserDefSignalName> .................................................. 29 *(page 5)*
- 5.4.8 IoHwAb_DCM_Read<UserDefSignalName> ................................................. 30 *(page 5)*
- 5.4.9 IoHwAb_Output<UserDefSignalName> ......................................................... 31 *(page 5)*
- 5.4.10 IoHwAb_DCM_Output<UserDefSignalName> ............................................... 32 *(page 5)*
- 5.4.11 IoHwAb_<SignalHandlerName>..................................................................... 33 *(page 5)*
- 5.5 Services used by IOHWAB ............................................................................. 33 *(page 5)*
- 5.9 Software Component Template....................................................................... 35 *(page 5)*
- 5.9.2 Import to the DaVinci modeling tool................................................................ 35 *(page 5)*
- 6.1 Configuration of IOHWAB with DaVinci Configurator...................................... 37 *(page 5)*
- 6.1.1 Start configuration of the IOHWAB ................................................................. 37 *(page 5)*
- 6.1.2.4 Node IoHwAbDataTypeSizes.......................................................................... 42 *(page 5)*
- 6.1.3.1 Area ‘Error Detection – Development Mode’ .................................................. 42 *(page 5)*
- 2 Introduction *(page 8)*
- 2.1 Architecture Overview *(page 9)*
- 10 / 48 *(page 10)*
- 3 Functional Description *(page 11)*
- 3.1 Features *(page 11)*
- 3.2 Initialization *(page 11)*
- 11 / 48 *(page 11)*
- 3.3 States *(page 12)*
- 3.4 Main Functions *(page 12)*
- 3.5 Error Handling *(page 12)*
- 3.5.1 Development Error Reporting *(page 12)*
- 12 / 48 *(page 12)*
- 3.5.1.1 Parameter Checking *(page 13)*
- 3.5.2 Production Code Error Reporting *(page 13)*
- 13 / 48 *(page 13)*
- 4 Integration *(page 14)*
- 4.1 Scope of Delivery *(page 14)*
- 4.1.1 Static Files *(page 14)*
- 4.1.2 Dynamic Files *(page 14)*
- 14 / 48 *(page 14)*
- 15 / 48 *(page 15)*
- 4.2 Include Structure *(page 16)*
- 4.3 Compiler Abstraction and Memory Mapping *(page 16)*
- 16 / 48 *(page 16)*
- Iohwab_Code *(page 17)*
- Iohwab_Var *(page 17)*
- Iohwab_Appl_Data *(page 17)*
- Iohwab_Appl_Code *(page 17)*
- Iohwab_Const *(page 17)*
- Iohwab_Start_Sec_Code *(page 17)*
- Iohwab_Stop_Sec_Code *(page 17)*
- Iohwab_Start_Sec_Const_32Bit *(page 17)*
- Iohwab_Stop_Sec_Const_32Bit *(page 17)*
- Iohwab_Start_Sec_Var_Zero_Init_Unspecified *(page 17)*
- Iohwab_Stop_Sec_Var_Zero_Init_Unspecified *(page 17)*
- 4.4 Critical Sections *(page 17)*
- 4.5 Generated Template Files *(page 17)*
- * Do Not Change This Comment! </Userblock> Do Not Change This Comment *(page 17)*
- 17 / 48 *(page 17)*
- /* A */ *(page 18)*
- * Do Not Change This Comment!  <Userblock … >             Do Not Change This Comment! *(page 18)*
- /* B */ *(page 18)*
- * Do Not Change This Comment!  </Userblock>               Do Not Change This Comment! *(page 18)*
- /* C */ *(page 18)*
- 4.5.1 Generated services in template files *(page 18)*
- Change This Comment *(page 18)*
- 18 / 48 *(page 18)*
- Comment! *(page 19)*
- * Do Not Change This Comment!       <</Userblock>>     Do Not Change This Comment! *(page 19)*
- 19 / 48 *(page 19)*
- 5 API Description *(page 20)*
- 5.1 Interfaces Overview *(page 20)*
- 20 / 48 *(page 20)*
- 5.2 Type Definitions *(page 21)*
- Std_High *(page 21)*
- 21 / 48 *(page 21)*
- 5.3 Services provided by IOHWAB *(page 22)*
- 5.3.1 IoHwAb_Init *(page 22)*
- 5.3.2 IoHwAb_GetVersionInfo *(page 22)*
- 22 / 48 *(page 22)*
- 5.4 Generated API functions *(page 23)*
- 5.4.1 IoHwAb_Set<CalSignalName> *(page 23)*
- 23 / 48 *(page 23)*
- 5.4.2 IoHwAb_Get<CalSignalName> *(page 24)*
- 24 / 48 *(page 24)*
- 5.4.3 IoHwAb_DCM_<CalSignalName> *(page 25)*
- 25 / 48 *(page 25)*
- 5.4.4 IoHwAb_DCM_Read<CalSignalName> *(page 26)*
- 26 / 48 *(page 26)*
- 5.4.5 IoHwAb_Diag<CalSignalName> *(page 27)*
- 27 / 48 *(page 27)*
- 5.4.6 IoHwAb_Input<UserDefSignalName> *(page 28)*
- 28 / 48 *(page 28)*
- 5.4.7 IoHwAb_DCM_Input<UserDefSignalName> *(page 29)*
- 29 / 48 *(page 29)*
- 5.4.8 IoHwAb_DCM_Read<UserDefSignalName> *(page 30)*
- 30 / 48 *(page 30)*
- 5.4.9 IoHwAb_Output<UserDefSignalName> *(page 31)*
- 31 / 48 *(page 31)*
- 5.4.10 IoHwAb_DCM_Output<UserDefSignalName> *(page 32)*
- 32 / 48 *(page 32)*
- 5.4.11 IoHwAb_<SignalHandlerName> *(page 33)*
- 5.5 Services used by IOHWAB *(page 33)*
- 33 / 48 *(page 33)*
- 5.6 Callback Functions *(page 34)*
- Iohwab. *(page 34)*
- 5.7 Configurable Interfaces *(page 34)*
- 5.7.1 Notifications *(page 34)*
- 5.8 Service Ports *(page 34)*
- 5.8.1 Client Server Interface *(page 34)*
- 5.8.1.1 Provide Ports *(page 34)*
- 34 / 48 *(page 34)*
- 5.8.1.2 Require Ports *(page 35)*
