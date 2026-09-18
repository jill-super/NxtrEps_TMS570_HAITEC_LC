---
title: "Fault Injection (FltInjection)"
description: "Fault Injection: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module manages the fault injection system.  It receives parameters through CANape-generated XCP signals (which write directly into memory), and creates a fault injection signal at a specified location based on these parameters.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `FltInjection/src/Ap_FltInjection.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `FltInjection_Per1`
- `FltInjection_SCom_FltInjection`


**Notable header dependencies:** `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_FltInjection.h`

## Documents

- [Fault Injection Module Design Document](documents/fault-injection-mdd) — converted from `FltInjection/doc/Fault_Injection_MDD.docx`

## Repository location

All files live under `FltInjection/` at the repository root.
