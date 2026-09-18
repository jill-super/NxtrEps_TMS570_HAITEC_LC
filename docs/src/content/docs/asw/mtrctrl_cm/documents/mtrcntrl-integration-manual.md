---
title: "MtrCntrl Integration Manual"
description: "Converted from MtrCntrl_Integration_Manual.docx"
---

> **Source document:** `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 70 paragraphs, 9 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Sengottaiyan, Selva **Revision:** 32

---

# Integration Manual -- MtrCntrl

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |

## Configuration Files to be provided by Integration Project

MtrCtrl_Cfg.h

## Functions to be provided to Integration Project

PICurrCntrl_Per1()

TrqCogCancRefPer1()

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| PICurrentCntrl<br />TrqCanc | Optimization level greater than 3 |  |

## Generator Config

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |

# Integration

## Global Data

The global symbols mapping done in MtrCtrl_Cfg.h.

## Component Conflicts

None

## Include Path

The “include” directory of this SWC needs to be included in the integration project include search path.

.

## Configurator Changes

None

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| TrqCogCancRefPer1() | Must be placed in the motor control ISR, after MtrPos | Cyclic (ISR) |
| PICurrCntrl_Per1() | Must be placed in the motor control ISR after TrqCogCancRefPer1() | Cyclic (ISR) |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| QuadDet_Per1 | Must run after TrqReasonable Diagnostics | RTE (2ms) |
| CurrCmd_Per1 | Must run after  QuadDet | RTE (2ms) |
| TrqCanc_Per1 | Must run after CurrCmd_Per1 | RTE (2ms) |
| PICurrCntrl_Per2() | Must be placed after TrqCanc_Per1 | RTE (2ms) |
| CurrParamComp_Per1() | Must be placed after PICurrCntrl_Per2 | RTE (2ms) |
| PeakCurrEst_Per1() | Must be placed after PICurrCntrl_Per2 | RTE (2ms) |

*Note: In motor control ISR include Ap_MtrCtrl.h instead of CDD_Func.h

Proper Initialization of input signals should occur before running each function for the first time.  **(****CurrParamComp_Init****)****.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| RTE Memory mapping |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |

## Table 1: ARM Cortex R4 Memory Usage

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 25-Mar-13 | Selva |
