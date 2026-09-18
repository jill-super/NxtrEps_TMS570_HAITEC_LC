---
title: "Common Motor Current Measurement (CmMtrCurr)"
description: "Common Motor Current Measurement: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Current Measurement function is responsible for measuring the motor phase currents used as feedback by the Motor Control FDD. Two motor phase currents are measured using a shunt resistor and a differential amplifier circuitry, and along with the motor position are transformed into direct (D) and quadrature (Q) axes currents using the combined Clarke/Park transform

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `CmMtrCurr/src/Sa_CmMtrCurr.c` | implementation |
| `CmMtrCurr/include/Sa_CmMtrCurr.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `CmMtrCurrTempOffset_Scom_Get`
- `CmMtrCurrTempOffset_Scom_Set`
- `CmMtrCurr_Init`
- `CmMtrCurr_Per1`
- `CmMtrCurr_Per2`
- `CmMtrCurr_Per3`
- `CmMtrCurr_SCom_CalGain`
- `CmMtrCurr_SCom_CalOffset`
- `CmMtrCurr_SCom_MtrCurrOffReadStatus`
- `CmMtrCurr_SCom_ReadMtrCurrCals`
- `CmMtrCurr_SCom_SetMtrCurrCals`
- `CurrDQPer1`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `CalConstants.h`, `CmMtrCurr_Cfg.h`, `GlobalMacro.h`, `Interpolation.h`, `MemMap.h`, `Rte_Sa_CmMtrCurr.h`, `Sa_CmMtrCurr.h`, `Sa_CmMtrCurr_Cfg.h`, `filters.h`, `fixmath.h`

## Documents

- [CmMtrCurr Integration Manual](documents/cmmtrcurr-integration-manual) — converted from `CmMtrCurr/doc/CmMtrCurr_Integration_Manual.docx`
- [CmMtrCurr Module Design Document](documents/cmmtrcurr-mdd) — converted from `CmMtrCurr/doc/CmMtrCurr_MDD.docx`

## Repository location

All files live under `CmMtrCurr/` at the repository root.
