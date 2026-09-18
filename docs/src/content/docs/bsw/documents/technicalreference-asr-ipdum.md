---
title: "TechnicalReference ASR IpduM"
description: "Converted from TechnicalReference_ASR_IpduM.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/HLDD/BSW/TechnicalReference_ASR_IpduM.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (44 pages).

**Pages:** 44

---

This is a **44-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

MICROSAR I-PDU Multiplexer 
Technical Reference 
 
 
Version 1.2.0 
 
 
 
 
 
 
 
 
 
 
 
Authors Safiulla Shakir 
Status Released 
 
 
 
 
 

Technical Reference MICROSAR I-PDU Multiplexer 
1 Document Information 
1.1 History 
Author Date Version Remarks 
Safiulla Shakir 26.03.2009 1.0 Initial version 
Safiulla Shakir 28.06.2010 1.1.0 Updated to support IPDUM 
system description 3.1.4 
format 
Safiulla Shakir 02.02.2011 1.2.0 ESCAN00046128 
Table 1-1 History of the document 
1.2 Reference Documents 
No. Title Version 
[1] AUTOSAR_SWS_IPDUM.pdf 1.2.1 
[2] AUTOSAR_SWS_IPDUM.doc 1.3.0 
[3] AUTOSAR_BasicSoftwareModules.pdf 1.0.0 
[4] AUTOSAR_SWS_IPDUM ASR3.2.pdf 1.3.0 
Table 1-2 Reference documents 
 
 
 
Please note 
We have configured the programs in accordance with your specifications in the 
questionnaire. Whereas the programs do support other configurations than the one 
specified in your questionnaire, Vector’s release of the programs delivered to your 
company is expressly restricted to the configuration you have specified in the 
questionnaire. 
 
 
Info 
[2] is a draft version of AUTOSAR release 4.0. 
 
©2011, Vector Informatik GmbH Version: 1.2.0 
based on template version 3.6 
2/ 4 4

Technical Reference MICROSAR I-PDU Multiplexer 
Contents 
1 Document Information..................................................................................................... 2 
1.1 History............................................................................................................... 2 
1.2 Reference Documents ...................................................................................... 2 
2 Introduction ...................................................................................................................... 7 
2.1 Architecture Overview....................................................................................... 8 
3 Functional Description .................................................................................................. 10 
3.1 Features.......................................................................................................... 10 
3.2 Initialization ..................................................................................................... 10 
3.3 States...............................................................................................................11 
3.4 Main Functions ................................................................................................11 
3.5 Error Handling..................................................................................................11 
3.5.1 Development Error Reporting ..........................................................................11 
3.5.2 Production Error Reporting ............................................................................. 12 
4 Integration....................................................................................................................... 13 
4.1 Scope of Delivery............................................................................................ 13 
4.1.1 Static Files ...................................................................................................... 13 
4.1.2 Dynamic Files ................................................................................................. 13 
4.2 Include Structure............................................................................................. 13 
4.3 Compiler Abstraction and Memory Mapping................................................... 13 
4.4 Critical Sections .............................................................................................. 14 
4.4.1 BSW Scheduler .............................................................................................. 14 
4.4.2 Vector Standard Library .................................................................................. 15 
5 API Description .............................................................................................................. 16 
5.1 Services provided by IPDUM.......................................................................... 16 
5.1.1 IpduM_InitMemory .......................................................................................... 16 
5.1.2 IpduM_Init ....................................................................................................... 16 
5.1.3 IpduM_RxIndication ........................................................................................ 17 
5.1.4 IpduM_Transmit.............................................................................................. 17 
5.1.5 IpduM_TxConfirmation ................................................................................... 18 
5.1.6 IpduM_TriggerTransmit................................................................................... 19 
5.1.7 IpduM_MainFunction ...................................................................................... 20 
5.1.8 IpduM_GetVersionInfo .................................................................................... 20 
5.2 Services used by IPDUM................................................................................ 20 
©2011, Vector Informatik GmbH Version: 1.2.0 
based on template version 3.6 
3/ 4 4

Technical Reference MICROSAR I-PDU Multiplexer 
6 Configuration.................................................................................................................. 22 
6.1 EcuC configuration with GENy ....................................................................... 22 
6.1.1 General parameters........................................................................................ 23 
6.1.2 Link time and Post build configuration ............................................................ 24 
6.1.3 Multiplexing and De-multiplexing .................................................................... 25 
6.1.4 Tx Pathway ..................................................................................................... 27 
6.1.5 Transmission Confirmations ........................................................................... 28 
6.2 ECU Configuration parameters:...................................................................... 30 
6.2.1.1 IPduMConfig ................................................................................................... 30 
6.2.1.2 IPduMRxPathway ........................................................................................... 30 
6.2.1.3 IPduMRxIndication.......................................................................................... 30 
6.2.1.4 IPduMBitField ................................................................................................. 31 
6.2.1.5 IPduMRxDynamicPart .................................................................................... 31 
6.2.1.6 IPduMCopyBitField ......................................................................................... 32 
6.2.1.7 IPduMBitField ................................................................................................. 32 
6.2.1.8 IPduMRxStaticPart.......................................................................................... 33 
6.2.1.9 IPduMCopyBitField ......................................................................................... 33 
6.2.1.10 IPduMBitField ................................................................................................. 34 
6.2.1.11 IPduMTxPathway............................................................................................ 34 
6.2.1.12 IPduMTxConfirmation ..................................................................................... 34 
6.2.1.13 IPduMDynamicTxConfirmation ....................................................................... 35 
6.2.1.14 IPduMTxRequest ............................................................................................ 35 
6.2.1.15 IPduMBitField ................................................................................................. 36 
6.2.1.16 IPduMTxDynamicPart..................................................................................... 37 
6.2.1.17 IPduMCopyBitField ......................................................................................... 37 
6.2.1.18 IPduMBitField ................................................................................................. 38 
6.2.1.19 IPduMTxStaticPart .......................................................................................... 38 
6.2.1.20 IPduMCopyBitField ......................................................................................... 39 
6.2.1.21 IPduMBitField ................................................................................................. 39 
6.2.1.22 IPduMGeneral................................................................................................. 39 
6.2.1.23 IPduMplexCh .................................................................................................. 41 
7 AUTOSAR Standard Compliance.................................................................................. 42 
7.1 Deviations ....................................................................................................... 42 
7.2 Additions/ Extensions ..................................................................................... 42 
7.3 Limitations....................................................................................................... 42 
8 Glossary and Abbreviations.......................................................................................... 43 
8.1 Glossary.......................................................................................................... 43 
8.2 Abbreviations .................................................................................................. 43 
©2011, Vector Informatik GmbH Version: 1.2.0 
based on template version 3.6 
4/ 4 4

Technical Reference MICROSAR I-PDU Multiplexer 
9 Contact........................................................................................................................ .... 44 
 
©2011, Vector Informatik GmbH Version: 1.2.0 
based on template version 3.6 
5/ 4 4

Technical Reference MICROSAR I-PDU Multiplexer 
Illustrations 
Figure 2-1 AUTOSAR architecture ................................................................................ 8 
Figure 2-2 IPDUM Interfaces to adjacent modules........................................................ 9 
Figure 3-1 DET Activation.............................................................................................11 
Figure 6-1 GENy component selection........................................................................ 23 
Figure 6-2 Static part activation ................................................................................... 24 
Figure 6-3 Link time and post build parameters .......................................................... 24 
Figure 6-4 Copy bit field configuration of a dynamic part ............................................ 25 
Figure 6-5 Copy bit field configuration of a static part ................................................. 26 
Figure 6-6 Dynamic part layout selection .................................................................... 26 
Figure 6-7 Tx Pathway configuration parameters........................................................ 27 
Figure 6-8 Dynamic part confirmation configuration.................................................... 29 
Figure 6-9 Static part confirmation configuration ......................................................... 29 
 
Tables 
Table 1-1 History of the document ............................................................................... 2 
Table 1-2 Reference documents .................................................................................. 2 
Table 3-1 Supported SWS features ..................................

## Extracted outline

- 1 Document Information *(page 2)*
- 1.1 History *(page 2)*
- 1.2 Reference Documents *(page 2)*
- 4.3 Compiler Abstraction and Memory Mapping................................................... 13 *(page 3)*
- 5.1 Services provided by IPDUM.......................................................................... 16 *(page 3)*
- 5.2 Services used by IPDUM................................................................................ 20 *(page 3)*
- 6.1 EcuC configuration with GENy ....................................................................... 22 *(page 4)*
- 6.1.2 Link time and Post build configuration ............................................................ 24 *(page 4)*
- 6.2 ECU Configuration parameters:...................................................................... 30 *(page 4)*
- 2 Introduction *(page 7)*
- 2.1 Architecture Overview *(page 8)*
- 3 Functional Description *(page 10)*
- 3.1 Features *(page 10)*
- 3.2 Initialization *(page 10)*
- 10 / 44 *(page 10)*
- 3.3 States *(page 11)*
- 3.4 Main Functions *(page 11)*
- 3.5 Error Handling *(page 11)*
- 3.5.1 Development Error Reporting *(page 11)*
- 11 / 44 *(page 11)*
- 3.5.2 Production Error Reporting *(page 12)*
- 12 / 44 *(page 12)*
- 4 Integration *(page 13)*
- 4.1 Scope of Delivery *(page 13)*
- 4.1.1 Static Files *(page 13)*
- 4.1.2 Dynamic Files *(page 13)*
- 4.2 Include Structure *(page 13)*
- 4.3 Compiler Abstraction and Memory Mapping *(page 13)*
- 13 / 44 *(page 13)*
- Ipdum_Code *(page 14)*
- Ipdum_Pbcfg *(page 14)*
- Ipdum_Var_Init *(page 14)*
- Ipdum_Var_Noinit *(page 14)*
- Ipdum_ Pbcfg _Root *(page 14)*
- Ipdum_ Appl_Data *(page 14)*
- Ipdum_Start_Sec_Code *(page 14)*
- Ipdum_Stop_Sec_Code *(page 14)*
- Ipdum_Start_Sec_Pbcfg *(page 14)*
- Ipdum_Stop_Sec_Pbcfg *(page 14)*
- Ipdum_Start_Sec_Pbcfg_Root *(page 14)*
- Ipdum_Stop_Sec_Pbcfg_Root *(page 14)*
- Ipdum_Start_Sec_Var_Init_Unspecified *(page 14)*
- Ipdum_Stop_Sec_Var_Init_Unspecified *(page 14)*
- Ipdum_Start_Sec_Var_Noinit_8Bit *(page 14)*
- Ipdum_Stop_Sec_Var_Noinit_8Bit *(page 14)*
- Ipdum_Start_Sec_Var_Noinit_Unspecified *(page 14)*
- Ipdum_Stop_Sec_Var_Noinit_Unspecified *(page 14)*
- 4.4 Critical Sections *(page 14)*
- 4.4.1 BSW Scheduler *(page 14)*
- Schm_Ea_Suspendallinterrupts. *(page 14)*
- 14 / 44 *(page 14)*
- 4.4.2 Vector Standard Library *(page 15)*
- 15 / 44 *(page 15)*
- 5 API Description *(page 16)*
- 5.1 Services provided by IPDUM *(page 16)*
- 5.1.1 IpduM_InitMemory *(page 16)*
- 5.1.2 IpduM_Init *(page 16)*
- 16 / 44 *(page 16)*
- 5.1.3 IpduM_RxIndication *(page 17)*
- Ipdum_Appl_Data) *(page 17)*
- Ipdum_Rxind_Para) *(page 17)*
- Std_On. *(page 17)*
- 5.1.4 IpduM_Transmit *(page 17)*
- 17 / 44 *(page 17)*
- 5.1.5 IpduM_TxConfirmation *(page 18)*
- 18 / 44 *(page 18)*
- 5.1.6 IpduM_TriggerTransmit *(page 19)*
- Ipdum_Tt_Type Ipdum_Tt_Para) *(page 19)*
- 19 / 44 *(page 19)*
- 5.1.7 IpduM_MainFunction *(page 20)*
- 5.1.8 IpduM_GetVersionInfo *(page 20)*
- 5.2 Services used by IPDUM *(page 20)*
- 20 / 44 *(page 20)*
- 21 / 44 *(page 21)*
- 6 Configuration *(page 22)*
- 6.1 EcuC configuration with GENy *(page 22)*
- 22 / 44 *(page 22)*
- 6.1.1 General parameters *(page 23)*
- 23 / 44 *(page 23)*
- 6.1.2 Link time and Post build configuration *(page 24)*
- 24 / 44 *(page 24)*
- 6.1.3 Multiplexing and De-multiplexing *(page 25)*
- 25 / 44 *(page 25)*
- 26 / 44 *(page 26)*
- 6.1.4 Tx Pathway *(page 27)*
- 27 / 44 *(page 27)*
- Ipdum. *(page 28)*
- 6.1.5 Transmission Confirmations *(page 28)*
- 28 / 44 *(page 28)*
- 29 / 44 *(page 29)*
- 6.2 ECU Configuration parameters: *(page 30)*
- 6.2.1.1 IPduMConfig *(page 30)*
- 6.2.1.2 IPduMRxPathway *(page 30)*
- 6.2.1.3 IPduMRxIndication *(page 30)*
- 30 / 44 *(page 30)*
- 31 / 44 *(page 31)*
- 1...1 Refer *(page 31)*
- 6.2.1.4 IPduMBitField *(page 31)*
- 6.2.1.5 IPduMRxDynamicPart *(page 31)*
- 1...1 Integ *(page 31)*
- 32 / 44 *(page 32)*
- 6.2.1.6 IPduMCopyBitField *(page 32)*
- 6.2.1.7 IPduMBitField *(page 32)*
- 33 / 44 *(page 33)*
- 6.2.1.8 IPduMRxStaticPart *(page 33)*
- 6.2.1.9 IPduMCopyBitField *(page 33)*
- 6.2.1.10 IPduMBitField *(page 34)*
- 6.2.1.11 IPduMTxPathway *(page 34)*
- 6.2.1.12 IPduMTxConfirmation *(page 34)*
- 34 / 44 *(page 34)*
- 35 / 44 *(page 35)*
- 0...1 Refer *(page 35)*
- 6.2.1.13 IPduMDynamicTxConfirmation *(page 35)*
- 6.2.1.14 IPduMTxRequest *(page 35)*
- 36 / 44 *(page 36)*
- 0...1 Integ *(page 36)*
- 1...1 Enum *(page 36)*
- Erati *(page 36)*
- 6.2.1.15 IPduMBitField *(page 36)*
- 6.2.1.16 IPduMTxDynamicPart *(page 37)*
