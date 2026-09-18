---
title: "AvgFricLrn Integration Manual"
description: "Converted from AvgFricLrn_Integration_Manual.docx"
---

> **Source document:** `AvgFricLrn/doc/AvgFricLrn_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 93 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Balani, Spandana **Revision:** 13

---

# Integration Manual –AvgFricLrn

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| <Name of SWC> | <Addition of global data, function*. |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

< None>

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

Ap_AvgFricLrn_Cfg.h for checkpoint enable

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| <None> |  |  |

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

CRFMtrTrq_MtrNm_f32

DefeatFricLearning_Cnt_lgc

HwAng_HwDeg_f32

HwPosAuthority_Uls_f32

HwTrq_HwNm_f32

HwVel_HwRadpS_f32

LatAcc_g_f32

Temperature_DegC_f32

VehSpd_Kph_f32

VehicleSpeedValid_Cnt_lgc

## Required Global Data Outputs

EstFric_HwNm_f32

FricOffset_HwNm_f32

SatEstFric_HwNm_f32

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| AvgFricLrn_Init1() | None | Init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| AvgFricLrn_Per1 | triggered on TimingEvent | 10ms |
| AvgFricLrn_SCom_GetEOLFric | triggered by server invocation for OperationPrototype <GetEOLFric> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_GetOffsetOutputDefeat | triggered by server invocation for OperationPrototype <GetOffsetOutputDefeat> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_GetSelect | triggered by server invocation for OperationPrototype <GetSelect> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_InitLearnedTables | triggered by server invocation for OperationPrototype <InitLearnedTables> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_ResetToZero | triggered by server invocation for OperationPrototype <ResetToZero> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_SetEOLFric | triggered by server invocation for OperationPrototype <SetEOLFric> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_SetOffsetOutputDefeat | triggered by server invocation for OperationPrototype <SetOffsetOutputDefeat> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_SCom_SetSelect | triggered by server invocation for OperationPrototype <SetSelect> of PortPrototype <AvgFricLrn_SCom> |  |
| AvgFricLrn_Trns1 | triggered on entering of Mode <OFF> of ModeDeclarationGroupPrototype <Mode> of PortPrototype <SystemState> |  |

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| AVGFRICLRN_START_SEC_VAR_CLEARED_32 |  |  |
| AVGFRICLRN_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| AVGFRICLRN_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |

Table 1: ARM Cortex R4 Memory Usage

## Non  RTE NvM Blocks

| Block Name |
| --- |
| <NVM block used Non RTE functions > |

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

| Block Name |
| --- |
| <NVM block used in RTE functions > |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 12-May-14 | SB |
