---
title: "Non-Volatile Memory Proxy (NvMProxy)"
description: "Non-Volatile Memory Proxy: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This diagram depicts the physical memory allocation for the various parts of the NvM Proxy system. 3 application RAM areas are shown for illustrative purposes, however, this module can handle any number of application RAM areas.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `NvMProxy/src/Cd_NvMProxy.c` | implementation |
| `NvMProxy/include/Cd_NvMProxy.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `NvMProxy_Init`
- `NvMProxy_MainFunction`
- `NvMProxy_WriteBlock`
- `NvMProxy_WriteAll`
- `NvMProxy_GetErrorStatus`
- `NvMProxy_SetRamBlockStatus`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `Cd_NvMProxy.h`, `Crc.h`, `MemMap.h`, `NvM.h`, `SchM_NvMProxy.h`, `Std_Types.h`

## Documents

- [NvMProxy Integration Manual](documents/nvmproxy-integration-manual) — converted from `NvMProxy/doc/NvMProxy_Integration_Manual.docx`
- [NvMProxy Module Design Document](documents/nvmproxy-mdd) — converted from `NvMProxy/doc/NvMProxy_MDD.docx`

## Repository location

All files live under `NvMProxy/` at the repository root.
