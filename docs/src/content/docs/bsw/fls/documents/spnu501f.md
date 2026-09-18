---
title: "SPNU501F"
description: "Converted from SPNU501F.pdf"
---

> **Source document:** `Fls/doc/SPNU501F.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (51 pages).

**Pages:** 51

---

This is a **51-page** reference document. The beginning of the document is reproduced below, followed by an automatically extracted outline. Refer to the original file for figures, tables and the complete text.

## Beginning of the document

F021 Flash API
Version 2.01.00
Reference Guide
Literature Number: SPNU501F
December 2012 – Revised May 2014

Contents
1 Introduction......................................................................................................................... 4
1.1 Reference Material....................................................................................................... 4
1.2 Function Listing Format ................................................................................................. 4
2 F021 Flash API Overview ...................................................................................................... 6
2.1 Introduction................................................................................................................ 6
2.2 API Overview ............................................................................................................. 6
2.3 Using API.................................................................................................................. 7
3 API Functions .................................................................................................................... 10
3.1 Flash State Machine Functions ....................................................................................... 10
3.2 Asynchronous Functions .............................................................................................. 16
3.3 Program Functions ..................................................................................................... 18
3.4 Read Functions ......................................................................................................... 20
3.5 Informational Functions ................................................................................................ 29
3.6 Utility Functions ......................................................................................................... 32
3.7 User Definable Functions.............................................................................................. 33
4 API Macros ........................................................................................................................ 34
4.1 FAPI_CHECK_FSM_READY_BUSY ................................................................................ 34
4.2 FAPI_CLEAR_FSM_DONE_EVENT................................................................................. 34
4.3 FAPI_GET_FSM_STATUS............................................................................................ 35
4.4 FAPI_SUSPEND_FSM ................................................................................................ 36
4.5 FAPI_WRITE_EWAIT .................................................................................................. 37
4.6 FAPI_WRITE_LOCKED_FSM_REGISTER ......................................................................... 37
5 Recommended FSM Flows .................................................................................................. 37
5.1 New Devices From Factory ........................................................................................... 37
5.2 Recommended Erase Flows .......................................................................................... 38
5.3 Recommended Program Flow ........................................................................................ 40
Appendix A Flash State Machine Commands................................................................................. 41
A.1 Flash State Machine Commands.................................................................................... 41
Appendix B Typedefs and Enumerations....................................................................................... 42
B.1 Type Definitions ....................................................................................................... 42
B.2 Enumerations .......................................................................................................... 42
Appendix C Flash Validation Procedure ........................................................................................ 47
Appendix D Parallel Signature Analysis (PSA) algorithm................................................................. 48
Appendix E Revision History ....................................................................................................... 49
2 Table of Contents SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated

www.ti.com
List of Figures
1 FMSTAT Register .......................................................................................................... 35
2 Recommended Sector Erase Flow....................................................................................... 38
3 Recommended Bank Erase Flow ........................................................................................ 39
4 Recommended Program Flow............................................................................................ 40
List of Tables
1 Summary of Flash State Machine Functions............................................................................. 6
2 Summary of Asynchronous Command Functions ....................................................................... 6
3 Summary of Program Functions ........................................................................................... 6
4 Summary of Read Functions ............................................................................................... 7
5 Summary of Information Functions........................................................................................ 7
6 Summary of User Defined Functions...................................................................................... 7
7 Summary of Utility Functions............................................................................................... 7
8 FMSTAT Register Field Descriptions.................................................................................... 35
9 Flash State Machine Commands ........................................................................................ 41
10 API Version History ........................................................................................................ 49
11 Document Revision History ............................................................................................... 50
3SPNU501F – December 2012 – Revised May 2014 List of Figures
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated

Reference Guide
SPNU501F – December 2012 – Revised May 2014
1 Introduction
Background
This reference guide provides a detailed description of Texas Instruments' F021 Flash API functions that
can be used to erase, program and verify F021 Flash on TI devices.
1.1 Reference Material
Use this guide in conjunction with the F021 Flash Module chapter in the device-specific technical
reference manual and data sheet that is being used. For additional options for programming and erasing
the Flash, see the Advanced F021 Flash API Erase/Program Usage (SPNA148).
1.2 Function Listing Format
This is the general format of an entry for a function, compiler intrinsic, or macro.
A short description of what function function_name() does.
Synopsis
Provides a prototype for function function_name().
<return_type> function_name(
<type_1> parameter_1,
<type_2> parameter_2,
<type_n> parameter_n
)
Parameters
parameter_1 [in] Pointer to x
parameter_2 [out] Handle for y
parameter_n [in/out] Pointer to z
Parameter passing is categorized as follows:
• In — Means the function uses one or more values in the parameter that you give it without storing any
changes.
• Out — Means the function saves one or more of the values in the parameter that you give it. You can
examine the saved values to find out useful information about your application.
• In/out — Means the function changes one or more of the values in the parameter that you give it and
saves the result. You can examine the saved values to find out useful information about your
application.
Description
Describes the function function_name(). This section also describes any special characteristics or
restrictions that might apply:
• Function blocks or might block under certain conditions
• Function has pre-conditions that might not be obvious
• Function has restrictions or special behavior
All trademarks are the property of their respective owners.
4 SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated

www.ti.com Introduction
Return Value
Specifies any value or values returned by function function_name().
See Also
Lists other functions or data types related to function function_name().
Example
Provides an example (or a reference to an example) that illustrates the use of function function_name().
5SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated

F021 Flash API Overview www.ti.com
2 F021 Flash API Overview
2.1 Introduction
The F021 Flash API is a library of routines that when called with the proper parameters in the proper
sequence, erases, programs, or verifies Flash memory on Texas Instruments microcontrollers using the
F021 (65nm) process. On ARM Cortex devices, these routines must be run in a privileged mode (a mode
other than user) to allow access to the Flash memory controller registers. The API verifies for the selected
bank, that the appropriate RWAIT or EWAIT value is set for the specified system frequency.
2.2 API Overview
Table 1. Summary of Flash State Machine Functions
API Function Description
Fapi_disableAutoEccCalculation() (1) Disables auto generation of ECC when data is written into an FWPWRITEx
register.
Fapi_disableBanksForOtpWrite() Disables all banks from programming customer OTP
Fapi_disableFsmDoneEvent() Disables the generation of an FSM_Done event at the end of a program or erase
operation.
Fapi_enableAutoEccCalculation() (1) Enables auto generation of ECC when data is written into an FWPWRITEx register.
Fapi_enableBanksForOtpWrite() Enables banks to allow programming of customer OTP
Fapi_enableEepromBankSectors() Enables the sectors in EEPROM bank for program and erase operations
Fapi_enableFsmDoneEvent() Enables the generation of an FSM_Done event at the end of a program or erase
operation.
Fapi_enableMainBankSectors() Enables the sectors in Main banks for program and erase operations
Fapi_initializeFlashBanks() Required Bank initialization before any erase, program, or verify API function.
Fapi_isAddressEcc() Determines if address falls in Flash memory controller ECC ranges
Fapi_remapEccAddress() Remaps an ECC address to corresponding main address
Fapi_remapMainAddress() Remaps an Main address to corresponding ECC address
Fapi_setActiveFlashBank() Sets the active bank for a erase or program command
(1) This function is only available on devices with the L2FMC Flash Controller.
Table 2. Summary of Asynchronous Command Functions
API Function Description
Fapi_issueAsyncCommand() Issues a command to FSM for operations that do not require an address
Fapi_issueAsyncCommandWithAddress() Issues a command to FSM for operations that require an address
Table 3. Summary of Program Functions
API Function Description
Sets up the required registers for programming and issues the command to theFapi_issueProgrammingCommand() FSM
Fapi_issueProgrammingCommandForEccAdd Remaps an ECC address to the main data space and then call
ress() Fapi_issueProgrammingCommand()
6 SPNU501F – December 2012 – Revised May 2014
Submit Documentation Feedback
Copyright © 2012–2014, Texas Instruments Incorporated

www.ti.com F021 Flash API Overview
Table 4. Summary of Read Functions
API Function Description
Fapi_doVerify() Verifies specified Flash memory range against supplied values
Fapi_doVerifyByByte() Verifies specified Flash 

## Extracted outline

- 2 Table of Contents SPNU501F – December 2012 – Revised May 2014 *(page 2)*
- 1 Introduction *(page 4)*
- 1.1 Reference Material *(page 4)*
- 1.2 Function Listing Format *(page 4)*
- 4 SPNU501F – December 2012 – Revised May 2014 *(page 4)*
- 2 F021 Flash API Overview *(page 6)*
- 2.1 Introduction *(page 6)*
- 2.2 API Overview *(page 6)*
- 6 SPNU501F – December 2012 – Revised May 2014 *(page 6)*
- 2.3 Using API *(page 7)*
- 2.3.1 Initialization Flow *(page 7)*
- 2.3.1.1 Before Using Any Erase, Program or Read Flash API Function *(page 7)*
- 2.3.1.2 Bank Setup *(page 8)*
- 2.3.1.3 On System Frequency Change *(page 8)*
- 2.3.2 Flash Addressing *(page 8)*
- 2.3.3 Building With the API *(page 8)*
- 2.3.3.1 Object Library Files *(page 8)*
- 2.3.3.2 Distribution Files *(page 8)*
- 8 SPNU501F – December 2012 – Revised May 2014 *(page 8)*
- 2.3.4 Executing API From Flash *(page 9)*
- 2.3.5 Memory Regions Required to be Readable *(page 9)*
- 3 API Functions *(page 10)*
- 3.1 Flash State Machine Functions *(page 10)*
- 3.1.1 Fapi_disableAutoEccCalculation() *(page 10)*
- 3.1.2 Fapi_disableBanksForOtpWrite() *(page 10)*
- 10 SPNU501F – December 2012 – Revised May 2014 *(page 10)*
- 3.1.3 Fapi_disableFsmDoneEvent() *(page 11)*
- 3.1.4 Fapi_enableAutoEccCalculation() *(page 11)*
- 3.1.5 Fapi_enableBanksForOtpWrite() *(page 12)*
- 3.1.6 Fapi_enableEepromBankSectors() *(page 12)*
- 12 SPNU501F – December 2012 – Revised May 2014 *(page 12)*
- 3.1.7 Fapi_enableFsmDoneEvent() *(page 13)*
- 3.1.8 Fapi_enableMainBankSectors() *(page 13)*
- 3.1.9 Fapi_isAddressEcc() *(page 14)*
- 3.1.10 Fapi_initializeFlashBanks() *(page 14)*
- Ti Otp) *(page 14)*
- 14 SPNU501F – December 2012 – Revised May 2014 *(page 14)*
- 3.1.11 Fapi_remapEccAddress() *(page 15)*
- 3.1.12 Fapi_remapMainAddress() *(page 15)*
- 3.1.13 Fapi_setActiveFlashBank() *(page 16)*
- 3.2 Asynchronous Functions *(page 16)*
- 3.2.1 Fapi_issueAsyncCommand() *(page 16)*
- 16 SPNU501F – December 2012 – Revised May 2014 *(page 16)*
- 3.2.2 Fapi_issueAsyncCommandWithAddress() *(page 17)*
- 3.3 Program Functions *(page 18)*
- 3.3.1 Fapi_issueProgrammingCommand() *(page 18)*
- 18 SPNU501F – December 2012 – Revised May 2014 *(page 18)*
- 3.3.2 Fapi_issueProgrammingCommandForEccAddress() *(page 19)*
- 3.4 Read Functions *(page 20)*
- 3.4.1 Fapi_doBlankCheck() *(page 20)*
- 20 SPNU501F – December 2012 – Revised May 2014 *(page 20)*
- 3.4.2 Fapi_doBlankCheckByByte() *(page 21)*
- 3.4.3 Fapi_doVerify() *(page 22)*
- 22 SPNU501F – December 2012 – Revised May 2014 *(page 22)*
- 3.4.4 Fapi_doVerifyByByte() *(page 23)*
- 3.4.5 Fapi_doPsaVerify() *(page 24)*
- 24 SPNU501F – December 2012 – Revised May 2014 *(page 24)*
- 3.4.6 Fapi_calculatePsa() *(page 25)*
- 3.4.7 Fapi_doMarginRead() *(page 26)*
- 26 SPNU501F – December 2012 – Revised May 2014 *(page 26)*
- 3.4.8 Fapi_doMarginReadByByte() *(page 27)*
- 3.4.9 Fapi_flushPipeline() *(page 28)*
- 28 SPNU501F – December 2012 – Revised May 2014 *(page 28)*
- 3.5 Informational Functions *(page 29)*
- 3.5.1 Fapi_getLibraryInfo() *(page 29)*
- 3.5.2 Fapi_getDeviceInfo() *(page 30)*
- 30 SPNU501F – December 2012 – Revised May 2014 *(page 30)*
- 3.5.3 Fapi_getBankSectors() *(page 31)*
- 3.6 Utility Functions *(page 32)*
- 3.6.1 Fapi_calculateFletcherChecksum() *(page 32)*
- 3.6.2 Fapi_calculateEcc() *(page 32)*
- 32 SPNU501F – December 2012 – Revised May 2014 *(page 32)*
- 3.6.3 Fapi_waitDelay() -- Deprecated *(page 33)*
- 3.7 User Definable Functions *(page 33)*
- 3.7.1 Fapi_serviceWatchdogTimer() *(page 33)*
- 4 API Macros *(page 34)*
- 4.1 FAPI_CHECK_FSM_READY_BUSY *(page 34)*
- 4.2 FAPI_CLEAR_FSM_DONE_EVENT *(page 34)*
- 34 SPNU501F – December 2012 – Revised May 2014 *(page 34)*
- 4.3 FAPI_GET_FSM_STATUS *(page 35)*
- 31 24 *(page 35)*
- 23 16 *(page 35)*
- 15 14 13 12 11 10 9 8 *(page 35)*
- 7 6 5 4 3 2 1 0 *(page 35)*
- Ers Pgm Inv-Dat Cstat Voltstat Esusp Psusp Slock *(page 35)*
- 15 Reserved Read returns 0. Writes have no effect. *(page 35)*
- 14 ILA When set, indicates that an illegal address is detected. Three conditions can set illegal address *(page 35)*
- 13 Reserved Read returns 0. Writes have no effect. *(page 35)*
- 11 Reserved Read returns 0. Writes have no effect. *(page 35)*
- 10 EV allowed number of erase pulses are given for erase operation. During Erase verify command, this *(page 35)*
- 9 Reserved Read returns 0. Writes have no effect. *(page 35)*
- 8 BUSY When set, this bit indicates that a program, erase, or suspend operation is being processed. *(page 35)*
- 7 ERS operation. This bit is set when erasing starts and is cleared when erasing is complete. It is also *(page 35)*
- 3 VOLTSTAT supply dipped below the lower limit allowable during a program or erase operation. This bit is *(page 36)*
- 2 ESUSP erase suspend operation. This bit remains set until the erase resume command has been issued or *(page 36)*
- 1 PSUSP a program suspend operation. This bit remains set until the program resume command has been *(page 36)*
- 0 SLOCK sector was locked for erasing and the programming either by the sector protect bit or by OTP write *(page 36)*
- 4.4 FAPI_SUSPEND_FSM *(page 36)*
- 36 SPNU501F – December 2012 – Revised May 2014 *(page 36)*
- 4.5 FAPI_WRITE_EWAIT *(page 37)*
- 4.6 FAPI_WRITE_LOCKED_FSM_REGISTER *(page 37)*
- 5 Recommended FSM Flows *(page 37)*
- 5.1 New Devices From Factory *(page 37)*
- Check_Fsm_Ready_Busy *(page 38)*
- Get_Fsm_Status *(page 38)*
- 5.2 Recommended Erase Flows *(page 38)*
- 38 SPNU501F – December 2012 – Revised May 2014 *(page 38)*
- 5.3 Recommended Program Flow *(page 40)*
- 40 SPNU501F – December 2012 – Revised May 2014 *(page 40)*
- 42 Typedefs and Enumerations SPNU501F – December 2012 – Revised May 2014 *(page 42)*
- 44 Typedefs and Enumerations SPNU501F – December 2012 – Revised May 2014 *(page 44)*
- Rwait/Ewait */ *(page 46)*
- 46 Typedefs and Enumerations SPNU501F – December 2012 – Revised May 2014 *(page 46)*
- 48 Parallel Signature Analysis (PSA) algorithm SPNU501F – December 2012 – Revised May 2014 *(page 48)*
- 1.00.0 Initial Revision *(page 49)*
- 1.00.1 Added missing extern reference for Fapi_getBankSectors() *(page 49)*
- 50 Revision History SPNU501F – December 2012 – Revised May 2014 *(page 50)*
- Important Notice *(page 51)*
