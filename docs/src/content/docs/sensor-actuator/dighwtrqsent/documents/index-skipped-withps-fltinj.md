---
title: "Unit-Test Report ((skipped cases) with Power Steering with Fault Injection)"
description: "Tessy unit-test report summary"
---

> **Source document:** `DigHwTrqSENT/utp/Tessy/report/index_Skipped_WithPS_FLTINJ.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (7 pages).

**Pages:** 7 **Report tool:** TESSY

---

## Test report summary

This is an automatically generated unit-test report with **7 pages**. Only the summary is reproduced here; the full step-by-step report remains in the repository.

| Item | Value |
| --- | --- |
| Detail | Test Object "CBD_UnitTest/DigHwTrqSENT_FLTINJ/DigHwTrqSENT_SCom_WriteData" |
| Total Test Objects | 1 |
| Successful | 1 |
| Failed | 0 |
| Not Executed | 0 |
| Coverage | Statement Coverage, Branch Coverage, Decision Coverage, Modified Condition / |
| Detail | Used Test Environments
TI TMS 570 PLS UDE (Default) |
| Detail | Report created by TESSY V3.1.7 |

### Report excerpt (first pages)

```text
TEST OVERVIEW REPORT 2014-08-25, 17:23:56+0530
Project CBD_DigHwTrqSENT
© Report created by TESSY V3.1.7, report template V2.0 1
Summary Overall Test Object Results (including Coverage)
Total Test Objects: 1
Successful: 1
Failed: 0
Not Executed: 0
Date: 2014-08-25
Time: 17:23:56+0530
Selected Project Items
Test Object "CBD_UnitTest/DigHwTrqSENT_FLTINJ/DigHwTrqSENT_SCom_WriteData"
Used Test Environments
TI TMS 570 PLS UDE (Default)
Batch Operation Settings
Check Interface: No
Generate Driver: Yes
Execute Test: Yes
Create New Test Run: No
Instrumentation: Test Object and Called Functions
Coverage: Statement Coverage, Branch Coverage, Decision Coverage, Modified Condition / 
Decision Coverage, Multiple Condition Coverage
Test Case Results for Each Test Object (without Coverage)
The table above shows each test object on the x axis and the number of test cases of the respective test 
object on the y axis. Each bar is divided into passed, not executed and failed test cases. The test case results 
do not take into account any coverage result (i.e. if all test cases of a test object are passed in this table but 
the coverage is failed, the overall test object result will be failed).
TEST OVERVIEW REPORT 2014-08-25, 17:23:56+0530
Project CBD_DigHwTrqSENT
© Report created by TESSY V3.1.7, report template V2.0 2
Statement (C0) Coverage: Total Statements for Each Test Object
The table above shows each test object on the x axis and the number of statements of the respective test 
object on the y axis. Each bar is divided into reached statements (i.e. statements that have been executed 
during the test) and unreached statements.
Branch (C1) Coverage: Total Branches for Each Test Object
The table above shows each test object on the x axis and the number of branches of the respective test object 
on the y axis. Each bar is divided into reached branches (i.e. branches that have been executed during the 
test) and unreached branches.
TEST OVERVIEW REPORT 2014-08-25, 17:23:56+0530
Project CBD_DigHwTrqSENT
© Report created by TESSY V3.1.7, report template V2.0 3
Test Object List
The following table lists all test objects with their test case and coverage results. The cumulated results for modules, folders and test collections are also displayed, the 
indentation within the name column indicates the parent relationship of the elements.
Please note that only test objects are numbered within the first column. This number is referenced on the x axis within the overview charts for test case and coverage results 
available on previous pages (if included into the report).
No. Name C0 C1 Test Cases Result
 CBD_DigHwTrqSENT 100 % 100 % 1 of 1 passed
 CBD_UnitTest 100 % 100 % 1 of 1 passed
 DigHwTrqSENT_FLTINJ 100 % 100 % 1 of 1 passed
1 DigHwTrqSENT_SCom_WriteData 100 % 100 % 1 of 1 passed

TEST DETAILS REPORT 2014-08-25, 17:23:50+0530
DigHwTrqSENT_SCom_WriteData
© Report created by TESSY V3.1.7, report template V2.1 1
Project CBD_DigHwTrqSENT
Module DigHwTrqSENT_FLTINJ
Test Object DigHwTrqSENT_SCom_WriteData
Instrumentation: Test Object and Called Functions
Statement (C0) Coverage 100 %
Branch (C1) Coverage 100 %
Statistics
Total Testcases 1
Successful 1
Failed 0
Not Executed 0
Module Properties
Project Root Directory D:\Synergy_Work_Area\CBD_DigHwTrqSENT
Configuration File D:\Synergy_Work_Area\CBD_DigHwTrqSENT\UnitTestEnv\config
\TMS570_GCC_UDE_CCS4_Config.xml
Target Environment TI TMS 570 PLS UDE (Default)
Kind of Test Unit Test
Linker Options 
Source File(s)
File $(PROJECTROOT)\DigHwTrqSENT\src\Sa_DigHwTrqSENT.c 
Compiler Options -D_DATA_ACCESS= -Dconst= -DBC_DIGHWTRQSENT_FAULTINJECTIONPOINT=STD_ON -I$(PROJECTROOT)\DigHwTrqSENT\utp
\contract -I$(PROJECTROOT)\NxtrLib\include -I$(PROJECTROOT)\StdDef\include -I$(PROJECTROOT)\StdDef\include
\TMS570_HerculesRegs -I$(Compiler Install Path)\include
File $(PROJECTROOT)\NxtrLib\src\interpolation.c 
Compiler Options -D_DATA_ACCESS= -Dconst= -DBC_DIGHWTRQSENT_FAULTINJECTIONPOINT=STD_ON -I$(PROJECTROOT)\DigHwTrqSENT\utp
\contract -I$(PROJECTROOT)\NxtrLib\include -I$(PROJECTROOT)\StdDef\include -I$(PROJECTROOT)\StdDef\include
\TMS570_HerculesRegs -I$(Compiler Install Path)\include
Comments/Description/Specification
Name Text
Module 'DigHwTrqSENT_FLTINJ' ***********************************UNIT TEST DESCRIPTION****************************************
Name of Tester: Ankita Bhardwaj
Code File(s) Under Test: Sa_DigHwTrqSENT.c
Code File(s) Version: 8
Module Design Document: DigHwTrqSENT_MDD.docx
Module Design Document Version: 11
Data Dictionary Version: 8
Unit Test Plan Version: 5
Optimization Level: Level 2
Compiler (CodeGen) Version: TMS570_4.9.5
Model Type: Excel Macro
Model Version: Nexteer EPS Unit Test Tool 2.7d/ EPS Library 1.30
Total FLASH Used (Bytes): 1638
Total RAM Used (Bytes): 84
Total CALS Used (Bytes): 108
Special Test Requirements: 
Test Date: 8/25/2014
Comments: "NOTE1: Inline functions declared in GlobalMacro.h are not Unit Tested.
NOTE2:""CBD_Sandbox_dbg.map"" map file is embedded for reference.
NOTE3: Low MC/DC coverage in function ""DigHwTrqSENT_SCom_ClrTrqTrim"" as the path ""if( D_TRIMNOTPERFORMED_CNT_LGC == 
Rte_Pim_DigTrqTrim()->k_EOLHwTrqTrimPerformed_Cnt_Lgc ) "" at line number 1210 of source code cannot be made FALSE which has been 
called in function ""TrimNotPerfDiag"" as ""Rte_Pim_DigTrqTrim()->k_EOLHwTrqTrimPerformed_Cnt_Lgc "" gets updated with const 
""D_TRIMNOTPERFORMED_CNT_LGC""having value FALSE always."
*************************************************************************************************************
Attributes
Name Value
Compiler Install Path $(ProgramFiles)\Texas Instruments\ccsv4\tools\compiler\tms470_4.9.5
Float Precision 9
InitObjDir $(PROJECTROOT)\UnitTestEnv\static_build_files\obj
InitSrcDir $(PROJECTROOT)\UnitTestEnv\static_build_files\src
Linker File $(PROJECTROOT)\UnitTestEnv\static_build_files\sys_link.cmd
Makefile Template $(PROJECTROOT)\UnitTestEnv\config\Nexteer_ts_make_ude_ti_tms570_ps.tpl
```
