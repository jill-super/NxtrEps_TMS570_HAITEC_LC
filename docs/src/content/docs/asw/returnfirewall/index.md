---
title: "Return Firewall Monitor (ReturnFirewall)"
description: "Return Firewall Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ReturnFirewall/src/Ap_ReturnFirewall.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ReturnFirewall_Per1`


**Notable header dependencies:** `Ap_ReturnFirewall_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_ReturnFirewall.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Return Firewall Module Design Document](documents/return-firewall-mdd) — converted from `ReturnFirewall/doc/Return_Firewall_MDD.docx`

## Repository location

All files live under `ReturnFirewall/` at the repository root.
