---
title: "Assist Firewall Monitor (AssistFirewall)"
description: "Assist Firewall Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module limits the output from the Assist module according to safety requirements.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `AssistFirewall/src/Ap_AssistFirewall.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `AssistFirewall_Init1`
- `AssistFirewall_Per1`


**Notable header dependencies:** `Ap_AssistFirewall_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_AssistFirewall.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Assist Firewall Module Design Document](documents/assist-firewall-mdd) — converted from `AssistFirewall/doc/Assist_Firewall_MDD.docx`

## Repository location

All files live under `AssistFirewall/` at the repository root.
