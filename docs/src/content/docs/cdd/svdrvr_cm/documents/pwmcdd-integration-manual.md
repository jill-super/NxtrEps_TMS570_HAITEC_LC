---
title: "PWMCdd Integration Manual"
description: "Converted from PWMCdd_Integration_Manual.docx"
---

> **Source document:** `SVDrvr_CM/doc/PWMCdd_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 92 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Kaur, Lovepreet **Revision:** 27

---

# Integration Manual – PWMCdd

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| CDD_Data | Global variables for DC Phs Comp (for using in Nhet/) |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

CDDPorts_ClearPhsReasSum(uint16 DataAccessBfr_Cnt_T_u16)

CDD_ApplyPWMMtrElecMechPol(sint8 MtrElecMechPol_Cnt_s8)

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

<Configuration file that will generated from this components that will require Da Vinci Config generation or manual generation. Describe each parameter >

### Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| None |  |  |

### DaVinci Interrupt Configuration Changes

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| None |  |  |  |

### Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| d_PwmFreq_Hz_Cnt_u16            <br />d_PWMFreqDither_Hz_u16 |  |  |

# Integration

## Required Global Data Inputs

The following global symbols must be defined in CDD_Data.c and .h (populated by PwmCdd):

- uint16: CDD_DCPhsComp_Cnt_G_u16[3]

- uint16: CDD_PWMPeriod_Cnt_G_u16

**NHET/****EPWM**  version corresponding PWMCdd component spilt and using global variables CDD_DCPhsComp_Cnt_G_u16 and CDD_PWMPeriod_Cnt_G_u16  should be used.

- CDD_Read_PhaseAdvanceFinal_Rev_u0p16

- CDD_Read_CorrectedMtrPos_Rev_u0p16

- CDD_Read_CommOffset_Cnt_u16

## Required Global Data Outputs

- CDD_Write_DCPhsBComp_Cnt_u16p0

- CDD_Write_DCPhsCComp_Cnt_u16p0

## Specific Include Path present

Yes - The “include” directory of this SWC needs to be included in the integration project include search path.

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Scheduling Requirements | Trigger | Trigger |
| --- | --- | --- | --- | --- |
| PwmCdd_Init | PwmCdd_Init | Place in EcuStartup.  Execute along with NHET initialization. | Place in EcuStartup.  Execute along with NHET initialization. | ISR |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| PwmCdd_Per1 | Must be placed in the motor control ISR, before Nhet (or whichever function populates the global variables used byNhet). | Cyclic (ISR) * |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| PWMCDD_START_SEC_VAR_CLEARED_16 | Variable Definitions |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |

Table 1: ARM Cortex R4 Memory Usage

## Non  RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

None

## Optimization Settings

None

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 14-Feb-13 | Selva |
| 2 | Added cal k_PWMBaseFrequency_Hz to replace constant d_PWMFreqBase_Hz_u16. | 21-Jan-14 | LK |
