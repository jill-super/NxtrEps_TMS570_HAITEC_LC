---
title: "TechnicalReference DrvCanAsr Tms470 Dcan"
description: "Converted from TechnicalReference_DrvCanAsr_Tms470_Dcan.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_DrvCanAsr_Tms470_Dcan.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (57 pages).

**Pages:** 57

---

This is a **57-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR CAN Driver 
Technical Reference 
 
Texas Instruments 
Tms470 / Tms570 
Dcan 
 
Version 1.10.00 
 
 
 
 
 
 
 
 
 
 
Authors Georg Pflügel, Sebastian Gärtner, 
Mihai Olariu, Robert Schelkle 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 2 
1. Document Information 
1.1 History 
Platforms 
Author Date Version Remarks 
Georg Pflügel 2007-01-12 1.00 Initial version. 
Georg Pflügel 2007-11-15 1.01 CAN-Driver Update to ASR2.1. 
Georg Pflügel 2008-08-05 1.02 CAN-Driver Update to ASR3 
Sebastian 
Gärtner 
2009-09-11 1.03 CAN-Driver Update to R7. 
Sebastian 
Gärtner 
2009-12-14 1.04 Local power-down mode added. 
Mihai Olariu 2010-07-28 1.05 CAN-Driver Update to R9. 
Description for DCAN Issue#22. 
Georg Pflügel 2011-03-08 1.06 Description of mailbox objects updated 
Georg Pflügel 2011-07-06 1.07 Description for the TMS570LS30316U added 
Georg Pflügel 2011-08-24 1.08 Description for GeneratorGeny added 
Georg Pflügel 2012-07-19 1.09 Update to R14 
Robert Schelkle 2013-01-16 1.10 Update to template 2.05.01 
Adapt Overrun/Overwrite description 
Table 1-1 History of the Document 
 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_CAN_DRIVER.pdf 2.4.6 + 
3.0.0 + 
4.0.0 
[2] AUTOSAR_BasicSoftwareModules.pdf V1.0.0 
[3] AUTOSAR_SWS BSW Scheduler V1.1.0 
[4] AUTOSAR_SWS_CAN_Interface.pdf 3.2.7 + 
4.0.0 + 
5.0.0 
[5] AN-ISC-8-1118 MICROSAR BSW Compatibility Check V1.0.0 
Table 1-2 Reference Documents 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 3 
 
1.3 Scope of the Document 
This document describes the functionality, API and configuration of the MICROSAR CAN 
driver as specified in [1]. The CAN driver is a hardware abstraction layer with a 
standardized interface to the CAN Interface layer. 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 4 
Contents 
1. Document Information ................................ ................................ ................................ ... 2 
1.1 History ................................ ................................ ................................ ...................... 2 
1.2 Reference Documents ................................ ................................ .............................. 2 
1.3 Scope of the Document ................................ ................................ ............................ 3 
2. Hardware Overview ................................ ................................ ................................ ........ 6 
3. Introduction ................................ ................................ ................................ .................... 7 
3.1 Architecture Overview ................................ ................................ .............................. 7 
4. Functional Description ................................ ................................ ................................ .. 9 
4.1 Features ................................ ................................ ................................ ................... 9 
4.2 Initialization ................................ ................................ ................................ ............ 13 
4.3 Communication ................................ ................................ ................................ ...... 13 
4.4 States / Modes ................................ ................................ ................................ ....... 15 
4.5 Re-Initialization ................................ ................................ ................................ ....... 15 
4.6 CAN Interrupt Locking ................................ ................................ ............................ 16 
4.7 Main Functions ................................ ................................ ................................ ....... 16 
4.8 Error Handling ................................ ................................ ................................ ........ 16 
5. Integration ................................ ................................ ................................ .................... 21 
5.1 Scope of Delivery ................................ ................................ ................................ ... 21 
5.2 Include Structure ................................ ................................ ................................ .... 22 
5.3 Critical Sections ................................ ................................ ................................ ..... 22 
5.4 Compiler Abstraction and Memory Mapping ................................ ........................... 24 
5.5 Hardware Specific Hints ................................ ................................ ......................... 25 
6. API Description ................................ ................................ ................................ ............ 26 
6.1 Interrupt Service Routines provided by CAN ................................ .......................... 26 
6.2 Services provided by CAN ................................ ................................ ...................... 28 
6.3 Services used by CAN ................................ ................................ ........................... 40 
7. Configuration................................ ................................ ................................ ................ 42 
7.1 Pre-Compile Parameters ................................ ................................ ........................ 42 
7.2 Link-Time Parameters ................................ ................................ ............................ 43 
7.3 Post-Build Parameters ................................ ................................ ........................... 43 
7.4 Configuration with GENy ................................ ................................ ........................ 44 
7.5 Configuration with da DaVinci Configurator ................................ ............................ 54 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 5 
8. AUTOSAR Standard Compliance ................................ ................................ ................ 55 
8.1 Limitations / Restrictions ................................ ................................ ......................... 55 
8.2 Vector Extensions ................................ ................................ ................................ .. 55 
9. Glossary and Abbreviations ................................ ................................ ........................ 56 
9.1 Glossary ................................ ................................ ................................ ................. 56 
9.2 Abbreviations ................................ ................................ ................................ ......... 56 
10. Contact ................................ ................................ ................................ .......................... 57 
 
Illustrations 
Figure 3-1 AUTOSAR architecture ................................ ................................ ............... 7 
Figure 3-2 Interfaces to adjacent modules of the CAN ................................ ................. 8 
Figure 5-1 Include Structure (AUTOSAR) ................................ ................................ .. 22 
Figure 6-1 Select OS Type ................................ ................................ ......................... 26 
Figure 7-1 Platform settings ................................ ................................ ....................... 44 
Figure 7-2 Init Structure Dialog ................................ ................................ .................. 52 
Figure 7-3 Setup Filter Dialog ................................ ................................ .................... 53 
Figure 7-4 Baud Rate Dialog ................................ ................................ ..................... 54 
 
Tables 
Table 1-1 History of the Document ................................ ................................ ............. 2 
Table 1-2 Reference Documents ................................ ................................ ................ 2 
Table 2-1 Supported Hardware Overview ................................ ................................ ... 6 
Table 4-1 Supported features ................................ ................................ ................... 12 
Table 4-2 Hardware mailbox layout ................................ ................................ .......... 14 
Table 4-3 Errors reported to DET ................................ ................................ ............. 17 
Table 4-4 API from which the Errors are reported ................................ ..................... 17 
Table 4-5 Errors reported to DEM ................................ ................................ ............. 18 
Table 4-6 Hardware Loop Check ................................ ................................ .............. 19 
Table 5-1 Static files ................................ ................................ ................................ . 21 
Table 5-2 Generated files ................................ ................................ ......................... 21 
Table 5-3 Critical Section Codes ................................ ................................ .............. 24 
Table 5-4 Compiler abstraction and memory mapping ................................ .............. 25 
Table 6-1 Services used by the CAN ................................ ................................ ........ 41 
Table 7-1 Platform Parameter description................................ ................................ . 44 
Table 7-2 Controller Parameter description ................................ .............................. 51 
Table 7-3 Filter Parameter description ................................ ................................ ...... 53 
Table 7-4 Baud rate Parameter description ................................ .............................. 54 
Table 9-1 Glossary ................................ ................................ ................................ ... 56 
Table 9-2 Abbreviations ................................ ................................ ............................ 56 
 
 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 6 
2. Hardware Overview 
The following table summarizes information about the CAN Driver. It gives you detailed 
information about the derivatives and compilers. As very important information the 
documentations of the hardware manufacturers are listed. The CAN Driver is based upon 
these documents in the given version. 
 
Derivative Compiler Hardware Manufacturer Document Version 
TMS470PSF761 TI TMS470PSF761 DesignSpec.pdf Revision 0.8 
TMS570PSFC61 TI TMS570PSFC61_Specification_044.pdf Revision 0.44 
TMS570PSFC66 TI TMS570PSFC66_design_specification_22.pdf Revision 2.2 
TMS570LS30316U TI Gladiator_design_specification_GM_Auto.pdf Version 2.5.1 
Table 2-1 Supported Hardware Overview 
Derivative: This can be a single information or a list of derivatives, the CAN Driver can be used on. 
Compiler: List of Compilers the CAN Driver is working with 
Hardware Manufacturer Document Name: List of hardware documentation the CAN Driver is based on. 
Version: To be able to reference to this hardware documentation its version is very important. 
 

Technical Reference MICROSAR CAN Driver 
2013, Vector Informatik GmbH Version: 1.10.00 Page 7 
3. Introduction 
This document describes the functionality, API and 

## Extracted outline

- 1.1 History *(page 2)*
- 1.2 Reference Documents *(page 2)*
- 3.0.0 + *(page 2)*
- 4.0.0 + *(page 2)*
- 1.3 Scope of the Document *(page 3)*
- 5.4 Compiler Abstraction and Memory Mapping ................................ ........................... 24 *(page 4)*
- 6.1 Interrupt Service Routines provided by CAN ................................ .......................... 26 *(page 4)*
- 3.1 Architecture Overview *(page 7)*
- ... Can X *(page 8)*
- 4.1 Features *(page 9)*
- 4.2 Initialization *(page 13)*
- 4.3 Communication *(page 13)*
- 4.3.1 Mailbox Layout *(page 14)*
- 1 – n Tx Full CAN 0 - (MaxObj-3) *(page 14)*
- 4.3.2 Acceptance Filter for BasicCAN *(page 14)*
- 4.3.3 Remote Frames *(page 14)*
- 4.4 States / Modes *(page 15)*
- Can_T_Start *(page 15)*
- Can_T_Stop *(page 15)*
- Can_T_Sleep *(page 15)*
- Can_T_Wakeup *(page 15)*
- 4.4.1 Start Mode (Normal Running Mode) *(page 15)*
- 4.4.2 Stop Mode *(page 15)*
- 4.4.3 Sleep Mode *(page 15)*
- 4.4.4 Bus Off *(page 15)*
- 4.5 Re-Initialization *(page 15)*
- 4.6 CAN Interrupt Locking *(page 16)*
- 4.7 Main Functions *(page 16)*
- 4.8 Error Handling *(page 16)*
- 4.8.1 Development Error Reporting *(page 16)*
- Can_E_Datalost *(page 16)*
- Can_E_Param_Baudrate *(page 16)*
- Can_E_Rxqueue *(page 17)*
- Can_E_Timeout_Det *(page 17)*
- Can_Hw_Access_Id *(page 17)*
- 4.8.1.1 Parameter Checking *(page 17)*
- Can_Dev_Error_Detect. *(page 17)*
- 4.8.1.2 Overrun/Overwrite Notification *(page 18)*
- 4.8.2 Production Code Error Reporting *(page 18)*
- == Std_On. *(page 18)*
- Can_E_Timeout *(page 18)*
- 4.8.2.1 Hardware Loop Check / Timeout Monitoring *(page 18)*
- Microsar4: *(page 19)*
- 4.8.3 CAN RAM Check *(page 19)*
- 4.8.4 Hardware Specific *(page 20)*
- 5.1 Scope of Delivery *(page 21)*
- 5.1.1 Static Files *(page 21)*
- 5.1.2 Dynamic Files *(page 21)*
- 5.2 Include Structure *(page 22)*
- Api). *(page 22)*
- 5.3 Critical Sections *(page 22)*
- 5.4 Compiler Abstraction and Memory Mapping *(page 24)*
- Can_ Code *(page 24)*
- Can_Static_ Code *(page 24)*
- Can_ Const *(page 24)*
- Can_ Const_Pbcfg *(page 24)*
- Can_Var_Noinit *(page 24)*
- Can_ Var_Init *(page 24)*
- Can_ Int_Ctrl *(page 24)*
- Can_ Reg_Cancell *(page 24)*
- Can_ Rx_Tx_Data *(page 24)*
- Can_ Appl_Code *(page 24)*
- Can_ Appl_Const *(page 24)*
- Can_ Appl_Var *(page 24)*
- Can_Start_Sec_Code *(page 24)*
- Can_Stop_Sec_Code *(page 24)*
- Can_Start_Sec_Static_Code *(page 24)*
- Can_Stop_Sec_Static_Code *(page 24)*
- Can_Start_Sec_Const_8Bit *(page 24)*
- Can_Stop_Sec_Const_8Bit *(page 24)*
- Can_Start_Sec_Const_16Bit *(page 24)*
- Can_Stop_Sec_Const_16Bit *(page 24)*
- Can_Start_Sec_Const_32Bit *(page 24)*
- Can_Stop_Sec_Const_32Bit *(page 24)*
- Can_Start_Sec_Const_Unspecified *(page 25)*
- Can_Stop_Sec_Const_Unspecified *(page 25)*
- Can_Start_Sec_Pbcfg *(page 25)*
- Can_Stop_Sec_Pbcfg *(page 25)*
- Can_Start_Sec_Pbcfg_Root *(page 25)*
- Can_Stop_Sec_Pbcfg_Root *(page 25)*
- Can_Start_Sec_Var_Noinit_Unspecified *(page 25)*
- Can_Stop_Sec_Var_Noinit_Unspecified *(page 25)*
- Can_Start_Sec_Var_Init_Unspecified *(page 25)*
- Can_Stop_Sec_Var_Init_Unspecified *(page 25)*
- Can_Start_Sec_Code_Appl *(page 25)*
- Can_Stop_Sec_Code_Appl *(page 25)*
- 5.5 Hardware Specific Hints *(page 25)*
- 1.1.1 Initialisation of the VIM-register *(page 25)*
- 1.1.2 Hardware specific topics *(page 25)*
- 6.1 Interrupt Service Routines provided by CAN *(page 26)*
- 6.1.1 OSEK (OS) *(page 26)*
- 6.1.2 AutoSar (OS) *(page 26)*
- 6.1.3 None (OS) *(page 27)*
- 6.1.4 Type of Interrupt Function *(page 27)*
- 6.1.5 CanIsr_<CH> *(page 27)*
- 1 interrupts. *(page 27)*
- 6.2 Services provided by CAN *(page 28)*
- 6.2.1 Can_GetVersionInfo *(page 28)*
- 6.2.2 Can_Init *(page 28)*
- 6.2.3 Can_InitController *(page 29)*
- Microsar3: *(page 29)*
- Microsar401: *(page 29)*
- 6.2.4 Can_SetControllerMode *(page 29)*
- 6.2.5 Can_Write *(page 30)*
- Can_Busy *(page 30)*
- 6.2.6 Can_DisableControllerInterrupts *(page 30)*
- 6.2.7 Can_EnableControllerInterrupts *(page 31)*
- 6.2.8 Can_MainFunction_Write *(page 31)*
- 6.2.9 Can_MainFunction_Read *(page 31)*
- 6.2.10 Can_MainFunction_BusOff *(page 32)*
- 6.2.11 Can_MainFunction_Wakeup *(page 32)*
- 6.2.12 Can_MainFunction_Mode (MICROSAR4x only) *(page 33)*
- 6.2.13 Can_ChangeBaudrate (MICROSAR403 only) *(page 33)*
- 6.2.14 Can_CheckBaudrate (MICROSAR403 only) *(page 33)*
- 6.2.15 Can_InitMemory (None AUTOSAR API) *(page 34)*
- 6.2.16 Can_InitStruct (None AUTOSAR API) *(page 34)*
- 6.2.17 Can_Cbk_CheckWakeup, Can_CheckWakeup *(page 35)*
- 6.2.18 ApplCanTimerStart (None AUTOSAR API) *(page 35)*
- 6.2.19 ApplCanTimerLoop (None AUTOSAR API) *(page 35)*
- 6.2.20 ApplCanTimerEnd (None AUTOSAR API) *(page 36)*
