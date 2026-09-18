---
title: "Standard Type Definitions (StdDef)"
description: "Standard Type Definitions: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-vector">Vector-provided (MICROSAR)</span>
</div>
## Purpose

The Standard Type Definitions software component (StdDef) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Vector-provided (MICROSAR)]
Vector Informatik copyright. 
:::

## Key files

| File | Role |
| --- | --- |
| `StdDef/include/Compiler.h` | public interface |
| `StdDef/include/Platform_Types.h` | public interface |
| `StdDef/include/Std_Types.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/_fmt_specifier.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/_isfuncdcl.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/_isfuncdef.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/_lock.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/access.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/assert.h` | public interface |
| `StdDef/include/TMS570_4_9_1/include/cpy_tbl.h` | public interface |

_Showing a selection; the area contains 0 source files and 120 headers in total._

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies


**Public interface declarations** (from headers):

- `void`
- `copy_in`
- `longjmp`
- `remove`
- `rename`
- `tmpfile`
- `tmpnam`
- `fclose`
- `fopen`
- `freopen`
- `setbuf`
- `setvbuf`
- `fflush`
- `fprintf`
- `fscanf`
- `printf`
- `scanf`
- `sprintf`

## Documents

_No converted design documents are attached to this page. Original Word, PDF or text documents (if any) remain in the repository._

## Repository location

All files live under `StdDef/` at the repository root.
