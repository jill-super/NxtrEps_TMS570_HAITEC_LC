---
title: "SVDiag Integration Manual"
description: "Converted from SVDiag_Integration_Manual.docx"
---

> **Source document:** `SVDiag/doc/SVDiag_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 152 paragraphs, 14 tables, 0 embedded figures).

**Author:** Nexteer **Last saved by:** Ahmed, Rijvi **Revision:** 8

---

**Integration Manual**

**For**

**Sine Voltage Generation Diagnostics (ES-49)**

**VERSION: ****2**

**DATE: ****0****2****-12-2014**

**Prepared By: **

**Rijvi Ahmed****,**

**Nexteer Automotive,**

** Saginaw,**** ****MI****, ****USA**

**Location:** The official version of this document is stored in the Nexteer Configuration Management System.

**Revision History**

| Sl. No. | Description | Author | Version | Date |
| --- | --- | --- | --- | --- |
| 1 | Initial version | VT | 1 | 03-Oct-2013 |
| 2 | Updated for FDD rev.008 and updated the template. | Rijvi | 2 | 01-Dec-2014 |

**Table of Contents**

# Abbrevations And Acronyms

| Abbreviation | Description |
| --- | --- |
| DFD | Design functional diagram |
| MDD | Module design Document |

# References

This section lists the title & version of all the documents that are referred for development of this document

| Sr. No. | Title | Version |
| --- | --- | --- |

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| None | None |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

Global function (except the ones that are defined in RTE modules) that is defined in this component but used by other function

# Configuration REQUIREMeNTS

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

None

## Da Vinci Parameter Configuration Changes

| Parameter | Notes | SWC |
| --- | --- | --- |
| None |  |  |

## DaVinci Interrupt Configuration Changes

| ISR Name | VIM # | Priority Dependency | Notes |
| --- | --- | --- | --- |
| None |  |  |  |

## Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| None |  |  |

# Integration  DATAFLOW REQUIREMENTS

## Required Global Data Inputs

ExpectedOnTimeA_Cnt_u32

ExpectedOnTimeB_Cnt_u32

ExpectedOnTimeC_Cnt_u32

LRPRCorrectedMtrPosCaptured_Rev_f32

LRPRModulationIndexCaptured_Uls_f32

LRPRPhaseadvanceCaptured_Cnt_s16

MeasuredOnTimeA_Cnt_u32

MeasuredOnTimeB_Cnt_u32

MeasuredOnTimeC_Cnt_u32

MotorVelMRFUnfiltered_MtrRadpS_f32

MtrElecMechPolarity_Cnt_s08

PDActivateTest_Cnt_lgc

MtrDrvrInitStart_Cnt_lgc

*

## Required Global Data Outputs

SVDiag_LowPhReasErrorAcc_Cnt_u16

SVDiag_HighResPhsReasDisable_u8

SVDiag_LowResPhsReasDisable_u8

SVDiag_MtrDrvInitComp_Cnt_lgc

SVDiag_GateDriveFltAcc_Cnt_u16

SVDiag_GenGateDriveFltAcc_Cnt_u16

SVDiag_OnStateFltAcc_Cnt_u16

*

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigPhsReasDiag_Init | Executed once after the RTE is started before first call of MtrDrvDiag_Per1 | RTE (at Startup) |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| DigPhsReasDiag_Per1 | Not in OFF, DISABLE, or WARMINIT modes | Rte 2ms task |
| DigPhsReasDiag_Trans1 | In OPERATE mode | On entering mode |
| MtrDrvDiag_Per1 | Not in DISABLE or OFF modes | Rte 2ms task |
| MtrDrvDiag_Per2 | Not in OPERATE or WARMINIT modes | Rte 2ms task |
| MtrDrvDiag_Trns1 | In WARMINIT mode | On entering mode |

**.**

# Memory Map REQUIREMENTS

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| < Memory mapping Info>* |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_32 |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_16 |  |  |
| DIGPHSREASDIAG_START_SEC_VAR_CLEARED_8 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_32 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| MTRDRVDIAG_START_SEC_VAR_CLEARED_UNSPECIFIED |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| Full |  |  |

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

# Appendix

*None*
