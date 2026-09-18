---
title: "BatteryVoltage Integration Manual"
description: "Converted from BatteryVoltage_Integration_Manual.docx"
---

> **Source document:** `BatteryVoltage/doc/BatteryVoltage_Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 83 paragraphs, 12 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** wz7x3j **Revision:** 2

---

# Integration Manual – Battery Voltage

Table of Contents

# Dependencies

## SWCs

| Module | Required Feature |
| --- | --- |
| ADC | D_ADC1CURRENTMODE_ULS_LGC configuration constant |
| Basic System Services | EnableOvervoltThreshInterrupt()* |

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

* Note: EnableOvervoltThreshInterrupt() must be called from ECUStartup.c as soon as possible, but AFTER Adc_Init(), so as to allow configuration of the ADC registers (and subsequently magnitude threshold).

## Global Functions(Non RTE) to be provided to Integration Project

- ISR(Isr_OvervoltThresh)

- Since the ISR that contains the overvoltage threshold diagnostic is enabled in ECUStartup.c, the NTC could be set before the RTE starts. In this case the non-Rte “report NTC staus” API should be used. Also, the application that contains the Battery Voltage ISR and NTC is configured at the integration level.  A component specific API,  BATTERYVOLTAGE_REPORTERRORSTATUS, is used in the ISR source code and a header file, Template_BatteryVoltage_Cfg.h, needs to be configured to link the BATTERYVOLTAGE_REPORTERRORSTATUS() to the appropriate NxtrDiagMgr**???**_ReportNTCStatus() function. Remove the “Template_” from the file name and replace the ??? in the API with the appropriate application and place the file in the Header folder of the integration project.

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
| Isr_OvervoltThresh | 31 | None | Category 2 IRQ |

### Manual Configuration Changes

| Constant | Notes | SWC |
| --- | --- | --- |
| BATTERYVOLTAGE_REPORTERRORSTATUS |  |  |

# Integration

## Required Global Data Inputs

None

## Required Global Data Outputs

None

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Init | Scheduling Requirements | Trigger |
| --- | --- | --- |
| BatteryVoltage_Init1 | None | RTE (Warm init) |

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |
| BatteryVoltage_Per1 | None | RTE (2ms) |
| BatteryVoltage_Per2 | None | RTE (4ms) |

# Memory Mapping

## Mapping

| Memory Section | Contents | Notes |
| --- | --- | --- |
| BATTERYVOLTAGE_START_SEC_VAR_CLEARED_32 | float32 | None |
| BATTERYVOLTAGE_START_SEC_VAR_CLEARED_16 | uint16 | None |
| BATTERYVOLTAGE_START_SEC_VAR_CLEARED_BOOLEAN | boolean | None |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| <Memmap usuage info> |  |  |

Table 1: ARM Cortex R4 Memory Usage

## Non  RTE NvM Blocks

| Block Name |
| --- |
| None |

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

| Block Name |
| --- |
| OvervoltageData (6 bytes) |

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

None

## Optimization Settings

None

# Revision Control Log

| Rev # | Change Description | Date | Author |
| --- | --- | --- | --- |
| 1 | Initial version | 16-Apr-13 | Jared |
| 2 | Added Overvoltage Threshold ISR, some cleanup, updated template | 3-Jan-14 | Jared |
| 3 | Added BATTERYVOLTAGE_REPORTERRORSTATUS and new template header file. | 8-Jan-14 | BDO |
