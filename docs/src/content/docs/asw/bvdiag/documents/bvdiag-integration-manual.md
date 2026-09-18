---
title: "BVDiag Integration Manual"
description: "Converted from BVDiag_Integration_Manual.docx"
---

> **Source document:** `BVDiag/doc/BVDiag_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 82 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Julien, Jared **Revision:** 7

---

# Integration Manual - BVDIAG

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| <None> |  |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

< None>

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| <None> |  |  |

## Configuration Files to be provided by Integration Project

Ap_BVDiag_Cfg.h for checkpoint enables

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| B1_BATTVOLTDIAG | This parameter will be turned ON only if customer requires $B1 NTC<br />STD_ON : Enables NTC $B1 logic<br />STD_Off : Disables NTC $B1 logic |  |

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

Batt_Volt_f32 from SER

CCLMSAActive_Cnt_lgc (Note : Only required for BMW as per its SER)

## Required Global Data Outputs

Sets BatteryVoltage Diagnostics

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| None | None | Init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| BVDiag_Per1 |  | 10ms |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| BVDIAG_START_SEC_VAR_CLEARED_32 |  |  |

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
| 1 | Initial version | 13-Sep-13 | NRAR |
