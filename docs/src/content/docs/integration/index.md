---
title: "Integration Project"
description: "ECU integration project: configuration, generated artifacts, build, and quality gates."
---

Everything that turns the components into a flashable Electronic Control Unit image: the DaVinci/GENy configuration project, generated sources, linker script, post-build steps, host-side tooling and the static-analysis setup.

## Modules in this layer (1)

| Component | Directory | Origin |
| --- | --- | --- |
| [Static Analysis Configuration (QAC)](./qac/) | `QAC` | Custom (in-house) |

## Integration areas

- [Integration project](./project/) — the `Haitec_LC_EPS_TMS570` Electronic Control Unit project.
- [Static analysis configuration](./qac/) — the `QAC` setup.
