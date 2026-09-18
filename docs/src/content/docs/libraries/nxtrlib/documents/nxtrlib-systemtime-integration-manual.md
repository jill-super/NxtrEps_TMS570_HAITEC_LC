---
title: "NxtrLib Systemtime Integration Manual"
description: "Converted from NxtrLib_Systemtime Integration_Manual.docx"
---

> **Source document:** `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 22 paragraphs, 7 tables, 0 embedded figures).

**Author:** Jeremy Warmbier **Last saved by:** jzh87w **Revision:** 2

---

# Integration Manual – NxtrLib_SystemTime

# Dependencies

| Module | Required Feature |
| --- | --- |

# Configuration

## Build Time Config

| Constant | Notes | SWC |
| --- | --- | --- |

## Generator Config

### System

| Constant | Notes | SWC |
| --- | --- | --- |

# Integration

The following import steps must be completed:

- Place CBD project structure to appropriate integration folder

- Copy SystemTime_Cfg.h.tt into the Header folder and remove the .tt extension.

- Configure the constant D_TickRate_Cnt_u32 to the appropriate Os system tick time.

# Runnable Scheduling

This section specifies the required runnable scheduling.

| Runnable | Scheduling Requirements | Trigger |
| --- | --- | --- |

# Memory Mapping

## Mapping

| Constant | Notes |
| --- | --- |

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

| Feature | RAM | ROM |
| --- | --- | --- |
| Full driver |  |  |

Table 1: ARM Cortex R4 Memory Usage

# Revision Control Log

| Item # | Rev # | Change Description | Date | Author Initials |
| --- | --- | --- | --- | --- |
| 1 |  | Initial version | 26Jul13 | SAH |
