---
title: "DigHwTrqSENT Integration Manual"
description: "Converted from DigHwTrqSENT_Integration_Manual.docx"
---

> **Source document:** `DigHwTrqSENT/doc/DigHwTrqSENT_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 83 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Shankar, Vishnu **Revision:** 14

---

# Integration Manual - DigHwTrqSENT

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
| BC_DIGHWTRQSENT_FAULTINJECTIONPOINT | Fault injection points |  |

## Configuration Files to be provided by Integration Project

Sa_DigHwTrqSENT_Cfg.h for checkpoint enables

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

T1_HwNm_f32 from FDD ES-34B

T2_HwNm_f32 from FDD ES-34B

## Required Global Data Outputs

HwTorque_HwNm_f32

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigHwTrqSENT_Init1() | None | Init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigHwTrqSENT_Per1 | After update of T1_HwNm_f32 and T2_HwNm_f32 | 2 ms |
| DigHwTrqSENT_Per2 | None | 4 ms |
| DigHwTrqSENT_Per3 | None | 100 ms |
| DigHwTrqSENT_SCom_ClrTrqTrim | triggered by server invocation for OperationPrototype <ClrTrqTrim> of PortPrototype <DigHwTrqSENT_SCom> | On event |
| DigHwTrqSENT_SCom_SetTrqTrim | triggered by server invocation for OperationPrototype <SetTrqTrim> of PortPrototype <DigHwTrqSENT_SCom> | On event |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| DIGHWTRQSENT_START_SEC_VAR_CLEARED_32 |  |  |
| DIGHWTRQSENT_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |
| DIGHWTRQSENT_START_SEC_VAR_SAVED_ZONEH_32 |  | Zone H EEPROM |

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
| DigHwTrqSENTTrim |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 01-Jul-13 | KMC |
| 2 | Updated per Design Review CR 11619 – Corrected Runnable Names – Removed “Sa_” from Init, Per functions | 03-Mar-14 | SB |
| 3 | Turned on track changes and corrected rev 2 changes | 01-Apr-14 | SB |
| 4 | Implemented ES04C Rev 006 | 09-Jun-14 | SB |
