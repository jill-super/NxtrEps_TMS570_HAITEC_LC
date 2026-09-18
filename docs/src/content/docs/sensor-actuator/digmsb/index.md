---
title: "Digital Motor Sensor Bridge (DigMSB)"
description: "Digital Motor Sensor Bridge: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The data synchronsiation  between Motor Control ISR and 2 ms Task will be provided at the integration level. But the synchronization between 2 and 100ms is provided by the Module level variable by disabling and enabling interrupts.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `DigMSB/src/Sa_DigMSB.c` | implementation |
| `DigMSB/include/Sa_DigMSB.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `MtrPosProcessing`
- `ErrorRegisterProcessing`
- `RevCntrProcessing`
- `DigMSB_Init`
- `DigMSB_Per2`
- `DigMSB_Per3`
- `DigMSB_Per1`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `CalConstants.h`, `DigMSB_Cfg.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_DigMSB.h`, `Sa_DigMSB.h`, `Sa_DigMSB_Cfg.h`, `SystemTime.h`, `fixmath.h`

## Documents

- [DigMSB Integration Manual](documents/digmsb-integration-manual) — converted from `DigMSB/doc/DigMSB_Integration_Manual.docx`
- [DigtalMSB Module Design Document](documents/digtalmsb-mdd) — converted from `DigMSB/doc/DigtalMSB_MDD.docx`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `DigMSB/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `DigMSB/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `DigMSB/` at the repository root.
