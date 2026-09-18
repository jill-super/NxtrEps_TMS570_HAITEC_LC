---
title: "Analog-to-Digital Converter Driver (Adc)"
description: "Analog-to-Digital Converter Driver: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Adc Common module provides “stateless” application context independent functions which provide functionality required by both the Adc and Adc2 modules.  In order to operate in any given application, the function design must not write to any fixed static variable location, unless it is in Globally shared memory.  All static variable writes outside of Globally shared memory must be performed via pointer access where the caller provides the pointer reference to allowed writable memory in the application context from with the caller is executing.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Adc/src/Adc.c` | implementation |
| `Adc/src/Adc2.c` | implementation |
| `Adc/src/Adc_Common.c` | implementation |
| `Adc/include/Adc.h` | public interface |
| `Adc/include/Adc2.h` | public interface |
| `Adc/include/Adc_Common.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Adc_Init_FixedCfg`
- `Adc_StartGroupConversion`
- `Adc_GetGroupStatus`
- `Adc_ReadGroup`
- `Adc2_Init1`
- `Adc2_StartGroupConversion`
- `Adc2_EnableGroupNotification`
- `ADCOffsetCalibration`


**Public interface declarations** (from headers):

- `Adc_Init_FixedCfg`
- `Adc_StartGroupConversion`
- `Adc_ReadGroup`
- `Adc_GetGroupStatus`
- `Adc2_ReadConversion`
- `Adc2_Init1`
- `Adc2_StartGroupConversion`
- `Adc2_EnableGroupNotification`
- `ADCOffsetCalibration`


**Notable header dependencies:** `Adc.h`, `Adc2.h`, `Adc_Common.h`, `Ap_DiagMgr.h`, `CDD_Data.h`, `CalConstants.h`, `Calconstants.h`, `GlobalMacro.h`, `MemMap.h`, `Std_Types.h`, `SystemTime.h`, `adc_regs.h`

## Documents

- [Adc Common Module Design Document](documents/adc-common-mdd) — converted from `Adc/doc/Adc_Common_MDD.docx`
- [Adc Module Design Document](documents/adc-mdd) — converted from `Adc/doc/Adc_MDD.docx`
- [Adc2 Module Design Document](documents/adc2-mdd) — converted from `Adc/doc/Adc2_MDD.docx`
- [Integration Manual ADC](documents/integration-manual-adc) — converted from `Adc/doc/Integration_Manual_ADC.docx`

## Repository location

All files live under `Adc/` at the repository root.
