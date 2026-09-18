---
title: "SignlCondn Integration Manual"
description: "Converted from SignlCondn_Integration_Manual.docx"
---

> **Source document:** `SgnlCond/doc/SignlCondn_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 84 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Balani, Spandana **Revision:** 3

---

# Integration Manual –SignlCondn

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

Ap_SignlCondn_Cfg.h for checkpoint enable

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

SrlComVehSpeed_Kph_f32

SrlCom_VehicleLonAccel_KphpS_f32

## Required Global Data Outputs

VehicleSpeed_Kph_f32

Vehicle_LonAccel_KphpS_f32

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| SignlCondn_Per1 | triggered on TimingEvent | 2ms |

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| SIGNLCONDN_START_SEC_VAR_NOINIT_32 |  |  |

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
