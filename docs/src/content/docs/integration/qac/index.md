---
title: "Static Analysis Configuration (QAC)"
description: "Project-wide QAC static-analysis setup for MISRA compliance."
---

<div class="origin-badges"><span class="origin-badge origin-custom">Custom — in-house</span></div>

## Purpose

The `QAC/` folder at the repository root holds the project-wide QAC (static analysis) configuration used to
check MISRA compliance of the C code: compiler personalities (`m2cm.p_c`), analyser settings
(`m2cmAnalyser.p_a`), message configuration (`m2cmMessage.p_s`) and presets (`preset_4.p_d`).

Component-level results live next to the code (`<Component>/doc/QAC_Results/`, `<Component>/tools/QAC/`);
the process view is described under [Quality and safety](../../general/quality/).

## Repository location

All files live under `QAC/` at the repository root.
