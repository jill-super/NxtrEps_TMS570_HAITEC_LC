---
title: "Motor Control (Current Mode) (MtrCtrl_CM)"
description: "Motor Control (Current Mode): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This Module generates the current command and the voltage reference for the current control.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `MtrCtrl_CM/src/Ap_CurrCmd.c` | implementation |
| `MtrCtrl_CM/src/Ap_CurrParamComp.c` | implementation |
| `MtrCtrl_CM/src/Ap_PICurrCntrl.c` | implementation |
| `MtrCtrl_CM/src/Ap_PeakCurrEst.c` | implementation |
| `MtrCtrl_CM/src/Ap_QuadDet.c` | implementation |
| `MtrCtrl_CM/src/Ap_TrqCanc.c` | implementation |
| `MtrCtrl_CM/src/Ap_TrqCmdScl.c` | implementation |
| `MtrCtrl_CM/include/Ap_MtrCtrl.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ParabolicInterpolation`
- `CalculateIq`
- `CalculateImVSIdq`
- `CurrtoVoltTest`
- `CalcTorque`
- `LocateTrqExtremes`
- `LocateMinimumIm`
- `CurrCmd_Init`
- `CurrCmd_Per1`
- `CurrParamComp_Init`
- `CurrParamComp_Per1`
- `CurrParamComp_Per2`
- `SCom_EOLNomMtrParam_Get`
- `SCom_EOLNomMtrParam_Set`
- `PICurrCntrl_Per2`
- `PICurrCntrl_Per1`
- `PeakCurrEst_Per1`
- `PeakCurrEst_Per2`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `Ap_CurrCmd_Cfg.h`, `Ap_CurrParamComp_Cfg.h`, `Ap_MtrCtrl.h`, `Ap_PICurrCntrl_Cfg.h`, `Ap_PeakCurrEst_Cfg.h`, `Ap_QuadDet_Cfg.h`, `Ap_TrqCanc_Cfg.h`, `Ap_TrqCmdScl_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `Interpolation.h`, `MemMap.h`, `MtrCtrl_Cfg.h`, `Rte_Ap_CurrCmd.h`, `Rte_Ap_CurrParamComp.h`, `Rte_Ap_PICurrCntrl.h`

## Documents

- [CurrCmd Module Design Document](documents/currcmd-mdd) — converted from `MtrCtrl_CM/doc/CurrCmd_MDD.doc`
- [CurrParamComp Module Design Document](documents/currparamcomp-mdd) — converted from `MtrCtrl_CM/doc/CurrParamComp_MDD.docx`
- [MtrCntrl Integration Manual](documents/mtrcntrl-integration-manual) — converted from `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx`
- [PICurrentContrl](documents/picurrentcontrl) — converted from `MtrCtrl_CM/doc/PICurrentContrl.doc`
- [PeakCurrEst Module Design Document](documents/peakcurrest-mdd) — converted from `MtrCtrl_CM/doc/PeakCurrEst_MDD.docx`
- [Quadrant Detection Module Design Document](documents/quadrant-detection-mdd) — converted from `MtrCtrl_CM/doc/Quadrant_Detection_MDD.docx`
- [TorqueCmdScaling Module Design Document](documents/torquecmdscaling-mdd) — converted from `MtrCtrl_CM/doc/TorqueCmdScaling_MDD.doc`
- [TrqCanc Module Design Document](documents/trqcanc-mdd) — converted from `MtrCtrl_CM/doc/TrqCanc_MDD.docx`

## Repository location

All files live under `MtrCtrl_CM/` at the repository root.
