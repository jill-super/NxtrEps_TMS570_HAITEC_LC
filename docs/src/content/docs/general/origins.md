---
title: "Vector vs. in-house code"
description: "Which parts are Vector-provided, generated, TI-provided or custom, and how to tell."
---

## Summary

| Origin | What it covers | Where it lives |
| --- | --- | --- |
| Custom — in-house | All application components (`Ap_*`, `Sa_*`), complex drivers (`Cd_*`, peripheral drivers), libraries, startup code | Top-level component folders (`Assist/`, `Adc/`, `DiagMgr/`, `NxtrLib/`, …) |
| Vector-provided (MICROSAR) | Communication, diagnostics, memory, mode-management and OS modules | `Haitec_LC_EPS_TMS570/SwProject/Source/BSW/` |
| Vector-generated | Runtime Environment, OS objects, module configurations | `…/Source/GenData`, `…/Source/GenDataRte`, `…/Source/GenDataOS` |
| Texas Instruments-provided | Flash EEPROM Emulation driver, F021 Flash API | `Fee/`, `Fls/` |
| Third-party | Timing-measurement library | `GliwaT1/` |

Every component page in this site carries one of these origin badges at the top.

## How to recognise each kind

- **In-house files** carry a `Copyright … Nexteer Automotive` header. Application sources additionally contain a
  `Generator: MICROSAR RTE Generator` banner — that banner only marks the file as an RTE component template;
  the control code itself is in-house.
- **Vector files** carry a `Copyright … Vector Informatik GmbH` block stating that rights remain with Vector,
  and generator banners naming `GENy`, `DaVinci` or `MICROSAR RTE Generator` with a Vector serial number.
- **Vector SIP adaptation:** `CMS_Common/src/EPS_DiagSrvcs_XCP.Vector.c` is in-house code that adapts the common
  manufacturing services to the Vector Software Integration Package (SIP); it must be kept in sync with the
  Vector XCP profiling functions.
- **Texas Instruments files** carry a `TEXAS INSTRUMENTS INCORPORATED PROPRIETARY INFORMATION` header
  (`Fee/`, `Fls/` including the prebuilt `F021_API_CortexR4_BE_V3D16.lib` library).
- **Gliwa T1** ships as a prebuilt static library (`libt1base.a`, …) with headers and its own integration manual.

## Licensing consequence

The in-house documentation and description pages are published under the repository MIT licence
(see the `LICENSE` file at the repository root). The Vector, Texas Instruments and Gliwa deliverables remain
subject to their own proprietary licences and are integrated — not re-licensed — here.
