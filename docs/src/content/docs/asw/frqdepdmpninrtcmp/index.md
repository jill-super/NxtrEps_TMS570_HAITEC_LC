---
title: "Frequency-Dependent Damping and Inertia Compensation (FrqDepDmpnInrtCmp)"
description: "Frequency-Dependent Damping and Inertia Compensation: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This MDD describes the methods to provide compensation that is dependent on filter of motor velocity which will compensate for motor inertia at low frequencies and provide damping acting at higher frequencies.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `FrqDepDmpnInrtCmp/src/Ap_FrqDepDmpnInrtCmp.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `DriverVelCalc`
- `ADDCoefCalc`
- `FilterCoefCalc`
- `GenFddIcCmd`
- `DecelGain`
- `FrqDepDmpnInrtCmp_Init`
- `FrqDepDmpnInrtCmp_Per1`


**Notable header dependencies:** `Ap_FrqDepDmpnInrtCmp_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_FrqDepDmpnInrtCmp.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Frequency Dependant Damping And Inertia Compenstation Module Design Document](documents/frequency-dependant-damping-and-inertia-compenstation-mdd) — converted from `FrqDepDmpnInrtCmp/doc/Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD.docx`
- [Unit-Test Report ((skipped cases) without Power Steering)](documents/index-skipped-withoutps) — converted from `FrqDepDmpnInrtCmp/utp/Tessy/report/index_Skipped_WithOutPS.pdf`
- [Unit-Test Report (with Power Steering with Fault Injection)](documents/index-withps-fltinj) — converted from `FrqDepDmpnInrtCmp/utp/Tessy/report/index_WithPS_FLTINJ.pdf`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `FrqDepDmpnInrtCmp/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering with Fault Injection)](documents/index-withoutps-fltinj) — converted from `FrqDepDmpnInrtCmp/utp/Tessy/report/index_WithOutPS_FLTINJ.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `FrqDepDmpnInrtCmp/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `FrqDepDmpnInrtCmp/` at the repository root.
