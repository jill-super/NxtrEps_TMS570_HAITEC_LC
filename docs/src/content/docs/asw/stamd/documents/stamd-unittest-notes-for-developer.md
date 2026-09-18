---
title: "StaMd UnitTest Notes For Developer"
description: "Converted from StaMd UnitTest Notes for Developer.docx"
---

> **Source document:** `StaMd/utp/StaMd UnitTest Notes for Developer.docx`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: Word document (`.docx`, 6 paragraphs, 0 tables, 0 embedded figures).

**Author:** Reddy, Niveditha **Last saved by:** Reddy, Niveditha **Revision:** 2

---

StaMd UnitTest Notes for Developer

(Note: Below is for short term plans. Long term plan is to make TEST_CFG folder more generic for projects)

To complete StaMd Unittest, StaMd files in GenData folder(Ap_StaMd_Cfg.c, Ap_StaMd_Proxy.c) should also be unit tested. These files are different across projects. Below steps should be followed to send files to ODC

- Place files from GenData (Ap_StaMd_Cfg.c, Ap_StaMd_Proxy.c)  in TEST_CFG folder of integration project .(For eg: BMW_UKL_MCV_EPS_TMS570\Tessy\Reports\StaMd).

- While submitting StaMd component to ODC for unittest, place TEST_CFG folder from step 1 in utp/contract folder of StaMd component(StaMd\utp\contract)

- And reports of StaMd component should be placed in integration project.(For eg: BMW_UKL_MCV_EPS_TMS570\Tessy\Reports\StaMd)
