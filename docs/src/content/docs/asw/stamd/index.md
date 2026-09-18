---
title: "States and Modes Manager (StaMd)"
description: "States and Modes Manager: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Note “#” denotes the application number. It can be any value =1 to n. Check project configuration files under UTP/Contract folder

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `StaMd/src/Ap_StaMd.c` | implementation |
| `StaMd/include/Ap_StaMd.h` | public interface |

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `BldTranVctr`
- `ReadTypeH`
- `WriteTypeH`
- `CheckWarmInitComplete`
- `StaMd_Init0`
- `StaMd_Init1`
- `StaMd_Per1`
- `StaMd_Trns1`
- `MilestoneRqst_WarmInitMilestoneComplete`
- `MilestoneRqst_WarmInitMilestoneNotComplete`
- `StaMd_SCom_EcuReset`
- `StaMd_SCom_FBLTransitionReq`
- `SystemStateCheck`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `Ap_StaMd_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Os.h`, `Rte_Ap_StaMd.h`, `Std_Types.h`

## Documents

- [StaMd Integration Manual](documents/stamd-integration-manual) — converted from `StaMd/doc/StaMd_Integration_Manual.docx`
- [StaMd UnitTest Notes For Developer](documents/stamd-unittest-notes-for-developer) — converted from `StaMd/utp/StaMd UnitTest Notes for Developer.docx`
- [States And Modes GeneratedConfiguration Module Design Document](documents/states-and-modes-generatedconfiguration-mdd) — converted from `StaMd/doc/States_And_Modes_GeneratedConfiguration_MDD.docx`
- [States And Modes Module Design Document](documents/states-and-modes-mdd) — converted from `StaMd/doc/States_And_Modes_MDD.docx`

## Repository location

All files live under `StaMd/` at the repository root.
