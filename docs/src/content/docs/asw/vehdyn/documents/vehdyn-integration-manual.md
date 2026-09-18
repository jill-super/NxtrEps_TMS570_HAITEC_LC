---
title: "VehDyn Integration Manual"
description: "Converted from VehDyn_Integration_Manual.docx"
---

> **Source document:** `VehDyn/doc/VehDyn_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 97 paragraphs, 13 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Balani, Spandana **Revision:** 24

---

# Integration Manual -- VehDyn

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| None |  |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

< Global function (except the ones that are defined in RTE modules) that is defined in this component but used by other function>

None

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

Ap_VehDyn_Cfg.h   (generated using Ap_VehDyn_Cfg.h.tt)

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| VehDynGeneral/VehDynCPEnable | Enable checkpoints if needed | VehDyn |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| None |  |  |  |

### Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |

# Integration

## Required Global Data Inputs

VehicleSpeed_Kph_f32

HwTorque_HwNm_f32

TorqueCmdCRF_MtrNm_f32

VehicleSpeedValid_Cnt_lgc

MotorVelCRF_MtrRadpS_f32

RelHwPos_HwDeg_f32

CcwEOT_HwDeg_f32

CwEOT_HwDeg_f32

HwAuth_Uls_f32

HandwheelPosition_HwDeg_f32

## Required Global Data Outputs

SensorlessHwAuth_Uls_f32

SensorlessHwPos_HwDeg_f32

## Specific Include Path present

< No >

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| VehDyn_Init1 | Called from RTE before first call of periodic function | RTE at init |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| VehDyn_Per1 | Should be called after the 2ms periodic that outputs RelHwPos and before the 2ms periodic that uses VDHwPos and VDAuthority | RTE 2 ms |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| VehDyn_Trns1 | triggered on entering of Mode <OFF> of ModeDeclarationGroupPrototype <Mode> of PortPrototype <SystemState> | RTE at shutdown |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| VEHDYN_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |
| VEHDYN_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| RTE_START_SEC_AP_VEHDYN_APPL_CODE |  |  |
| VEHDYN_START_SEC_VAR_CLEARED_32 |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usage info> |  |  |

Table 1: ARM Cortex R4 Memory Usage

## Non  RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

| Block Name |
| --- |
| VehDynReset |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 19-Aug-13 | KMC |
| 2 | Updated per SF42 - VCDMotPos rev 002 | 21-Aug-14 | SB |
