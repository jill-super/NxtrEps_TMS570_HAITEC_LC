---
title: "CmMtrCurr Integration Manual"
description: "Converted from CmMtrCurr_Integration_Manual.docx"
---

> **Source document:** `CmMtrCurr/doc/CmMtrCurr_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 113 paragraphs, 11 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** Sengottaiyan, Selva **Revision:** 7

---

# Integration Manual –CmMtrCurr

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Functions to be provided to Integration Project

CurrDQPer1

# Configuration

## Build Time Config

| Modules | Notes |  |
| --- | --- | --- |
| None |  |  |

## Configuration Files to be provided by Integration Project

CmMtrCurr_Cfg.h ( Refer CmMtrCurr_Cfg_Template.h in tools folder)

(Data synchronization must be provided at the integration level between 2 ms periodic and Motor Control ISR Periodic’s)

Outputs from the CmMtrCurr (Motor Control ISR) periodic must be synchronized with  from

### Da Vinci Config Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| MTRCURRPHASEBC | PhaseB and Phase C used in Curr Measurement |  |
| MTRCURRPHASECB | PhaseC and Phase B used in Curr Measurement |  |
| MTRCURRPHASEAC | PhaseA and Phase C used in Curr Measurement |  |
| MTRCURRPHASECA | PhaseC and Phase A used in Curr Measurement |  |
| MTRCURRPHASEAB | PhaseA and Phase B used in Curr Measurement |  |
| MTRCURRPHASEBA | PhaseB and Phase A used in Curr Measurement |  |

Note: Only one of the configuration can be selected based on the requirements. Make sure order matches oreder in ADC  data read  ie MTRCURRPHASEBC -   “BC” represents current_1 is phase B and current_2 is phase C  .

### Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| none |  |  |

# Integration

## Required Global Data Inputs

For other inputs  Refer the template in tools folder of this component

## Required Global Output Inputs

For other inputs  Refer the template in tools folder of this component

## Specific Include Path present

Yes

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| CmMtrCurr_Init | None | RTE |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| CmMtrCurr_Per2 | None | RTE(2MilliS) |
| CmMtrCurr_Per1 | None | RTE(100 MilliS) |
| CurrDQPer1 | After  processing | ISR MicroS) |

**.**

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| CMMTRCURR_START_SEC_VAR_CLEARED_16 |  |  |
| CMMTRCURR_START_SEC_VAR_CLEARED_8 |  |  |
| CMMTRCURR_START_SEC_VAR_CLEARED_BOOLEAN |  |  |
| CMMTRCURR_START_SEC_VAR_CLEARED_32 |  |  |
| SA_CMMTRCURR_CODE |  |  |
| RTE_START_SEC_SA_CMMTRCURR_APPL_CODE |  |  |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |

Table 1: ARM Cortex R4 Memory Usage

## RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

## Non RTE NvM Blocks

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
| 1 | Initial version | 7-Sep- 13 | nzt9hv |
| 2 |  |  |  |
