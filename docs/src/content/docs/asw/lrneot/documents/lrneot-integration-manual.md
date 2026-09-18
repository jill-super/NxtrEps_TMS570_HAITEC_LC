---
title: "LrnEOT Integration Manual"
description: "Converted from LrnEOT_Integration_Manual.docx"
---

> **Source document:** `LrnEOT/doc/LrnEOT_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 89 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Balani, Spandana **Revision:** 4

---

# Integration Manual –LrnEOT

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

Ap_LrnEOT_Cfg.h for checkpoint enable

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

DiagStsHwPosDis_Cnt_lgc

HandwheelAuthority_Uls_f32

HandwheelPosition_HwDeg_f32

HwTorque_HwNm_f32

MtrVelCRF_MtrRadpS_f32

## Required Global Data Outputs

CCWFound_Cnt_lgc

CCWPosition_HwDeg_f32

CWFound_Cnt_lgc

CWPosition_HwDeg_f32

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| LrnEOT_Init1() | None | Init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| LrnEOT_Per1 | Triggered on Timing Event | 10ms |
| LrnEOT_Scom_ResetEOT | triggered by server invocation for OperationPrototype <ResetEOT> of PortPrototype <LrnEOT_Scom> | On event |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| LRNEOT_START_SEC_VAR_CLEARED_32 |  |  |
| LRNEOT_START_SEC_VAR_CLEARED_BOOLEAN |  |  |

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
| 1 | Initial version | 01-May-14 | SB |
