---
title: "Quality and safety"
description: "Static analysis, unit testing and functional-safety evidence."
---

<div class="origin-badges"><span class="origin-badge origin-custom">Custom — in-house</span></div>

## Static analysis (QAC / MISRA)

- The top-level [`QAC/`](../../integration/qac/) area holds the project-wide QAC configuration
  (`m2cm.p_c`, `m2cmAnalyser.p_a`, presets).
- Most components keep their own QAC results under `<Component>/doc/QAC_Results/` (`.err`/`.met` pairs)
  and QAC project files under `<Component>/tools/QAC/`.

## Documents

- [MISRA Compliance Guidelines](documents/misra-compliance-guidelines) — converted from `QAC/doc/MISRA Compliance Guidelines.docx`.

## Unit testing (Tessy)

Each component may ship a Tessy project under `<Component>/utp/` (test database `.pdbx`, contracts under
`utp/contract/`, reports under `utp/Tessy/report/`). The generated `index_*.pdf` reports are summarised on
the component pages: overall verdict (successful / failed / not executed) and coverage configuration
(statement, branch, decision, modified condition/decision and multiple-condition coverage where enabled).

## Functional safety

Supervision is layered: component-level firewall monitors, system-level temporal monitoring and shutdown
management, AUTOSAR Watchdog Manager supervision, and TMS570 hardware self-diagnostics. See
[System architecture](../architecture) for the safety concept and the individual component pages for details.
