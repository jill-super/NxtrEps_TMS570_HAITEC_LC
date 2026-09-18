---
title: "AbsHwPos TcI2cVd Integration Manual"
description: "Converted from AbsHwPos_TcI2cVd_Integration_Manual.docx"
---

> **Source document:** `AbsHwPos_TcI2cVd/doc/AbsHwPos_TcI2cVd_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 99 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Balani, Spandana **Revision:** 9

---

# Integration Manual – Absolute Handwheel Position – Turns Counter, I2C, and Vehicle Dynamics

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| <Name of SWC> | <Addition of global data, function*. |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

None

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

Ap_AbsHwPos_Cfg.h   (generated using Ap_AbsHwPos_Cfg.h.tt)

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| AbsHwPosGeneral\AbsHwPosCPEnable | Enable checkpoints if needed | AbsHwPos |

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

CumMechMtrPosCRF_Deg_f32

AlignedCumMechMtrPosCRF_Deg_f32

TurnsCntrValidity_Cnt_u08

I2CHwAbsPos_HwDeg_f32

I2CHwAbsPosValid_Cnt_lgc

_HwDeg_f32

_Uls_f32

ComplError_HwDeg_f32

DiagStatusHwPosReducedPerf_Cnt_lgc

ManufMode_Cnt_enum

## Required Global Data Outputs

HandwheelPosition_HwDeg_f32

HandwheelAuthority_Uls_f32

RelHwPos_HwDeg_f32

HwPosSource_Cnt_u16

SrlComHwPos_HwDeg_f32

SrlComHwPosStatus_Cnt_u16

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| AbsHwPos_Init1 | Called from RTE before first call of periodic function | RTE at init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| AbsHwPos_Per1 | Call before 2ms periodic that uses RelHwPos_HwDeg_f32 | RTE 2 ms |
| AbsHwPos_Per2 | Call after 2ms periodic that outputs VDHwPos_HwDeg_f32 | RTE 2 ms |
| AbsHwPos_Per3 | None | RTE 4 ms |
| AbsHwPos_Per4 | None | RTE 10 ms |
| AbsHwPos_SCom_CustSetTrim | Common Manufacturing | On event |
| AbsHwPos_SCom_CustClrTrim | Common Manufacturing | On event |
| AbsHwPos_SCom_NxtSetTrim | Common Manufacturing | On event |
| AbsHwPos_SCom_NxtClearTrim | Common Manufacturing | On event |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| ABSHWPOS_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |
| ABSHWPOS_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| ABSHWPOS_START_SEC_VAR_CLEARED_16 |  |  |
| ABSHWPOS_START_SEC_VAR_CLEARED_32 |  |  |
| RTE_START_SEC_AP_ABSHWPOS_APPL_CODE |  |  |

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
| EOLVehCntrOffset |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1.0 | Initial version | 26-Nov-13 | KMC |
