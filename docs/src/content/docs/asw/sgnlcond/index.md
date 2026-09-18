---
title: "Signal Conditioning (SgnlCond)"
description: "Signal Conditioning: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This function conditions a signal received from SER prior to its distribution to other functions. Typical conditioning methods may include filters, slew rates, gain values or limits.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `SgnlCond/src/Ap_SignlCondn.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `SignlCondn_Per1`


**Notable header dependencies:** `Ap_SignlCondn_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_SignlCondn.h`

## Documents

- [SignalConditioning Module Design Document](documents/signalconditioning-mdd) — converted from `SgnlCond/doc/SignalConditioning_MDD.docx`
- [SignlCondn Integration Manual](documents/signlcondn-integration-manual) — converted from `SgnlCond/doc/SignlCondn_Integration_Manual.docx`

## Repository location

All files live under `SgnlCond/` at the repository root.
