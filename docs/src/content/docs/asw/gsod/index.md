---
title: "Global Shutdown Manager (Gsod)"
description: "Global Shutdown Manager: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Key system inputs including handwheel torque, motor position, motor and handwheel velocity are widely distributed and used by command path and other safety critical system functions.  The safety strategy for these “global” input signals is a dual channel diverse calculation with cross check to detect a systematic design fault that would propagate to the receiving functions.  However, since the dual channel diversity does not continue along the command path out to the motor command output, this strategy cannot fully cover  a potential systematic overwrite of the global signals after the cross c

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Gsod/src/Ap_Gsod.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Gsod_Per1`


**Notable header dependencies:** `Ap_Gsod_Cfg.h`, `MemMap.h`, `Os.h`, `Rte_Ap_Gsod.h`

## Documents

- [Gsod Module Design Document](documents/gsod-mdd) — converted from `Gsod/doc/Gsod_MDD.docx`

## Repository location

All files live under `Gsod/` at the repository root.
