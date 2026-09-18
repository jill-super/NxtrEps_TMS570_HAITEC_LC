---
title: "StaMd Integration Manual"
description: "Converted from StaMd_Integration_Manual.docx"
---

> **Source document:** `StaMd/doc/StaMd_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 81 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Osteen, Bobby **Revision:** 13

---

# Integration Manual - StaMd

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| ECUStatup.c | StaMd_Init0 needs to be called from EcuStartup_Init2 via a trusted wrapper after Nvm ‘read all’ is complete, by calling Call_StaMd_Init0. <br />ECUStartup needs to also include the Ap_StaMd.h header file. <br />The StaMd_Init0 is defined outside of the RTE and is responsible for updating Type H memory across applications at start up.  StaMd_Init0 needs to be added to a non-trusted function list in a trusted application in the O.S. |
| NtWrap.c, .h, O.S changes | Add trusted function call to NtWrap : <br /><br />/* Trusted wrapper Function */<br />void TRUSTED_NtWrapS_StaMd_Init0<br />(TrustedFunctionIndexType FunctionIndex, TrustedFunctionParameterRefType FunctionParams)  <br />{<br />   StaMd_Init0();<br />} <br />…<br />void Call_StaMd_Init0(void)<br />{<br />   (void) CallTrustedFunction<br />   (NtWrapS_StaMd_Init0,<br />   (TrustedFunctionParameterRefType)0);<br />} |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

extern FUNC(void, MCU_CODE) **Mcu_PerformReset**(void);

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| <None> |  |  |

## Configuration Files to be provided by Integration Project

**Ap_****StaMd_Cfg.h**

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| TypeHDataSize | Total size of all Type H data in bytes |  |
| StaMdCPEnable | This container contains the configuration (parameters) for the StaMd Watchdog checkpoints. |  |
| StaMdTODType | This container defines the configuration for the type of TOD implementation used:<br />TOD_2msToggle<br />TOD_SteadyState (*common setting)<br />TOD_None |  |
| StaMdNvMWriteAllAPI | This container defines the API used for the NvM Write All function. (*common setting is NvMProxy_WriteAll if the NvM proxy is used). |  |
| StaMdNvMGetErrorStatusAPI | This container defines the API used for the NvM Get Error Status function. (*common setting is NvMProxy_GetErrorStatus if the NvM proxy is used). |  |
| StaMdTrnsDiagMgrShtDwnTaskActivation | This container defines the DiagMgr shutdown function. If StaMdCoreOsAppRef matches the application referenced for DiagMgrDemIfOsAppRef in DiagMgr then the generated output will be a client/server call and this field is ignored. If they do not match, then a task activation call is created and the task defined in this field is activated. <br />NOTE: Typical setting is Task_TrnsB_9 for the application 9 transition function, from which the StaMd9_Trns_DemShutdown function is called in some programs. |  |
| GenerateExcludeOsAppRef | This parameter defines the application(s) which do not require a States and Modes component. |  |
| StaMdCoreOsAppRef | This parameter defines the application which contains the core States and Modes component. |  |
| StaMdsComOsAppRef | This parameter defines the application which interfaces with the serial communications functions. |  |
| StaMdSysCovOsAppRef | This parameter defines the application which performs the states and modes systematic coverage. |  |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| <None> |  |  |  |

### Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| <None> |  |  |

# Integration

## Required Global Data Inputs

## Required Global Data Outputs

## Specific Include Path present

The **…****StaMd****/include** patch needs to be added to the include search path of the CCS project. Typical setting: **"${****workspace_loc****:/FORD_S550_P552/****StaMd****/include}"**

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| None | None | Init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
|  |  | 10ms |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| STAMD_START_SEC_VAR_SAVED_ZONEHGS_32<br />STAMD_START_SEC_VAR_SAVED_ZONEHGS_8 |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |

Table 1: ARM Cortex R4 Memory Usage

## Non  RTE NvM Blocks

| Block Name |
| --- |
| <None > |

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 12-Dec-13 | BDO |
| 2 | Updated to FDD ES10B version 13 to address anomaly 5388.           CR11347 | 07-Feb-14 | BDO |
