---
title: "HaitecTrqCmd Integration Manual"
description: "Converted from HaitecTrqCmd_Integration Manual.doc"
---

> **Source document:** `HaitecTrqCmd/doc/HaitecTrqCmd_Integration Manual.doc`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: legacy Word document (`.doc`).

> **Note:** the original file is a legacy binary Word document (`.doc`) which cannot be converted with full fidelity in this environment. The text below was recovered automatically and may be out of order in places; tables and figures are not preserved. See the original file for the authoritative content.

bjbj$

## Integration Manual

## Haitec Torque Command

VERSION: 1.0

DATE: 08-SEP-2015

Prepared By:

## Software Group,

## Nexteer Automotive,

## Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

## Revision History

Sl. No.

## Description

## Author

## Version

## Approved By

## Initial version

## Jayakrishnan T

08-SEP-2015

## Table of Contents

## Abbrevations And Acronyms

## References

## Dependencies

## Global Functions(Non RTE) to be provided to Integration Project

## Configuration REQUIREMeNTS

## Build Time Config

## Configuration Files to be provided by Integration Project

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

## Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

## Required Global Data Outputs

## Specific Include Path present

## Runnable Scheduling

## Memory Map REQUIREMENTS

## Mapping

## Usage

## NvM Blocks

## Compiler Settings

## Preprocessor MACRO

## Optimization Settings

## Appendix

## Abbrevations And Acronyms

## Abbreviation

## Description

## Design functional diagram

## Module design Document

## Functional Design Document

## References

This section lists the title & version of all the documents that are referred for development of this document

Sr. No.

## Title

## Version

CF015A_HaitecTrqCmd

V.001

## Dependencies

## Module

## Required Feature

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

## Configuration REQUIREMeNTS

## Build Time Config

## Modules

## Notes

## Configuration Files to be provided by Integration Project

## Da Vinci Parameter Configuration Changes

## Parameter

## Notes

## DaVinci Interrupt Configuration Changes

## ISR Name

VIM #

## Priority Dependency

## Notes

## Manual Configuration Changes

## Constant

## Notes

## Integration DATAFLOW REQUIREMENTS

## Required Global Data Inputs

MtrVelCRF_MtrRadpS_f32

HwTrq_HwNm_f32

AssitMechTempEst_DegC_f32

VehSpd_Kph_f32

## Required Global Data Outputs

## Specific Include Path present

## Runnable Scheduling

This section specifies the required runnable scheduling.

## Scheduling Requirements

## Trigger

HaitecTrqCmd_Init1

## RTE(Init)

## Runnable

## Scheduling Requirements

## Trigger

HaitecTrqCmd_Per1

RTE(2ms)

## Memory Map REQUIREMENTS

## Mapping

## Memory Section

## Contents

## Notes

HAITECTRQCMD_START_SEC_VAR_CLEARED_UNSPECIFIED

HAITECTRQCMD_START_SEC_VAR_CLEARED_32

HAITECTRQCMD_START_SEC_VAR_CLEARED_BOOLEAN

* Each

START_SEC

constant is terminated by a

STOP_SEC

constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

## Feature

## Table

SEQ Table \* ARABIC

: ARM Cortex R4 Memory Usage

## NvM Blocks

## Compiler Settings

## Preprocessor MACRO

## Optimization Settings

## Appendix

## Nexteer Automotive Confidential Proprietary Information

## Do Not Copy/Distribute Without Prior Permission

## Integration Manual Template

Version: 2.0 Date: 08-Sep-2015

## Nexteer Automotive

}w}qf]Q

}ofoP}

f]Y]If>

\SOS?\

o`oN`o`

tkgkWtL>L

]TPT@]

jaXOB5

pepYQpQ

}pg[SOSO

gd_@'

gd*9Z

zrgXgXKXg

phfff

gdd<O

_Toc429483080

_Toc429483081

_Toc429483082

_Toc429483083

_Toc429483084

_Toc429483085

_Toc429483086

_Toc429483087

_Toc429483088

_Toc429483089

_Toc429483090

_Toc429483091

_Toc429483092

_Toc429483093

_Toc429483094

_Toc429483095

_Toc429483096

_Toc429483097

_Toc429483098

_Toc429483099

_Toc429483100

_Toc429483101

_Toc429483102

_Toc429483103

## LOGO

Picture 5

## LOGO

tEXtSoftware

## Adobe ImageReadyq

## IDATx

*`mPO

#3Bh8JN

$h1S%

)IUF\

?\z6{

k6Wzj

igZ>E

7m]l\,@

e ,F]\R

$Ib-'

S;DrY

JD+Sw

0cq*x

`TUp#j

dcQ9Y]Tr^

l.[v`!

zd}Qi

t1C*jUV

Y=J&)

meJJq

(rJMt

-_2d_

GK8dD

h$c%9O

L'~^i;

Y=TfU

## LO)O/

ljp^8!MG

<GE]8!M

20"p"

iFAQ7h

DH3_<g

ipnr/

x;eMm

1r/<6

/{npr

cNQ!T

!H5yn

P@o3"

_:90CCa

&nf1\

23)}S;

b<(<,

irP@J

## BNkIr

!U56&m:

pm St$

)~W120B

Uz@8!

.x/Lv

3vji|

3JdfO

8_W 0

?1172

eCP=E

~.GfB

g~xi&%Ikl

'f2/r

F-e!M)

fMB0}

bRRZZ

4[uJl'

~---%5U

,|rVK

i5y$n

K%8[/

(KbF"

L4h)rD

p)DNM

|]?OIRL

*/H!'

N]=qn

H)f$y

N<?:g

iXXLp9

P9m V;

lzo)<

J2>Uc

fF8fM,

q>^XP

+`-QO5

>}>Xk

2>o"/I

^iUzW

dv^3$

UqK)[

{OGC$

{?[`X

`e[Ui

<^rEq

{_NJW

pAe]g%

{?UWm(*

D9pb;6\

Hh4A@I

## LgZBC

#V~vB

0;W:#

}X?*r

xOzqD

49mvT

Y6l6*

SavLO=

]J"yg

/*;@y?

rkj9\

/W6?,

CT.Ak

Px/$w

pp"%<

7E|`Z

Nfn%A7J

\1"r~

).*vtC

## USRvE

q[1Z:n

gzXav>

Wy#\Y

wu_M}

~+54|

y_et6)

/9ci}R

L-y|cQ

>#]/U

## Normal

Heading 1

Heading 2

Heading 3

Heading 4

Heading 5

Heading 6

Heading 7

Heading 8

Heading 9

## Default Paragraph Font

## Table Normal

## No List

TOC 1

TOC 2

Index 1

Index 2

Index 3

Index 4

Index 5

Index 6

Index 7

Index 8

Index 9

TOC 3

TOC 4

TOC 5

TOC 6

TOC 7

TOC 8

TOC 9

## Hyperlink

## Header

## Footer

## FollowedHyperlink

## List Bullet

List Bullet 2

List Bullet 3

List Bullet 4

List Bullet 5

## List Number

List Number 2

List Number 3

List Number 4

List Number 5

## Caption

## Balloon Text

## Document Map

## Strong

## Table Grid

## TOC Heading

Table Grid 3

## Body Text

## Body Text Char

## Comment Reference

## Comment Text

## Comment Text Char

## Comment Subject

## Comment Subject Char

Light List - Accent 11

Light List - Accent 12

[Content_Types].xml

_rels/.rels

theme/theme/themeManager.xml

theme/theme/theme1.xml

w toc'v

3Vq%'#q

:\TZaG

Qg20pp

\}DU4

,)''K

O@%\w

0X4D)

theme/theme/_rels/themeManager.xml.rels

K(M&$R(.1

[Content_Types].xmlPK

_rels/.relsPK

theme/theme/themeManager.xmlPK

theme/theme/theme1.xmlPK

theme/theme/_rels/themeManager.xml.relsPK

<?xml version="1.0" encoding="UTF-8" standalone="yes"?>

<a:clrMap xmlns:a="http://schemas.openxmlformats.org/drawingml/2006/main" bg1="lt1" tx1="dk1" bg2="lt2" tx2="dk2" accent1="accent1" accent2="accent2" accent3="accent3" accent4="accent4" accent5="accent5" accent6="accent6" hlink="hlink" folHlink="folHlink"/>

_Toc348792978

_Toc348793074

_Toc348793965

_Toc349459173

_Toc349621609

_Toc378476016

_Toc367436496

_Toc429483080

_Toc429483081

_Hlt172996899

_Toc357692818

_Toc429483082

_Toc357692819

_Toc429483083

_Toc357692820

_Toc429483084

_Toc357692821

_Toc429483085

_Toc357692822

_Toc429483086

_Toc357692823

OLE_LINK10

OLE_LINK11

_Toc429483087

_Toc357692824

OLE_LINK12

OLE_LINK13

_Toc357692825

_Toc429483088

_Toc429483089

_Toc429483090

OLE_LINK22

OLE_LINK23

OLE_LINK24

_Toc357692826

_Toc429483091

_Toc357692827

OLE_LINK83

OLE_LINK84

_Toc429483092

_Toc429483093

_Toc357692829

_Toc429483094

_Toc357692830

_Toc429483095

_Toc357692831

OLE_LINK16

OLE_LINK17

_Toc429483096

_Toc357692832

_Toc429483097

_Toc357692833

_Toc429483098

OLE_LINK20

OLE_LINK81

OLE_LINK82

_Toc357692834

_Toc429483099

_Toc357692835

OLE_LINK18

OLE_LINK19

_Toc429483100

_Toc357692836

_Toc429483101

OLE_LINK21

_Toc357692837

_Toc429483102

_Toc382295838

_Toc382297291

_Toc383611455

_Toc383698777

_Toc382295839

_Toc382297292

_Toc383611456

_Toc383698778

_Toc382295842

_Toc382297295

_Toc383611459

_Toc383698781

_Toc382295843

_Toc382297296

_Toc383611460

_Toc383698782

_Toc382295850

_Toc382297303

_Toc383611467

_Toc383698789

_Toc382295853

_Toc382297306

_Toc383611470

_Toc383698792

_Toc382295856

_Toc382297309

_Toc383611473

_Toc383698795

_Toc382295858

_Toc382297311

_Toc383611475

_Toc383698797

_Toc382295859

_Toc382297312

_Toc383611476

_Toc383698798

_Toc382295876

_Toc382297329

_Toc383611493

_Toc383698815

_Toc382297340

_Toc383611504

_Toc383698826

_Toc382297341

_Toc383611505

_Toc383698827

_Toc382297346

_Toc383611510

_Toc383698832

_Toc382297348

_Toc383611512

_Toc383698834

_Hlt375931258

_Toc382297371

_Toc383611535

_Toc383698857

_Toc382297372

_Toc383611536

_Toc383698858

_Toc382297373

_Toc383611537

_Toc383698859

_Toc382297374

_Toc383611538

_Toc383698860

_Toc382297375

_Toc383611539

_Toc383698861

_Toc382297376

_Toc383611540

_Toc383698862

_Toc382297377

_Toc383611541

_Toc383698863

_Toc382297378

_Toc383611542

_Toc383698864

_Toc382297379

_Toc383611543

_Toc383698865

_Toc382297380

_Toc383611544

_Toc383698866

_Toc382297381

_Toc383611545

_Toc383698867

_Toc382297382

_Toc383611546

_Toc383698868

_Toc382297383

_Toc383611547

_Toc383698869

_Toc382295908

_Toc382297384

_Toc383611548

_Toc383698870

_Toc382295909

_Toc382297385

_Toc383611549

_Toc383698871

_Toc382295910

_Toc382297386

_Toc383611550

_Toc383698872

_Toc382295911

_Toc382297387

_Toc383611551

_Toc383698873

_Toc382295912

_Toc382297388

_Toc383611552

_Toc383698874

_Toc382295913

_Toc382297389

_Toc383611553

_Toc383698875

_Toc382295914

_Toc382297390

_Toc383611554

_Toc383698876

_Toc382295915

_Toc382297391

_Toc383611555

_Toc383698877

_Toc382297405

_Toc383611575

_Toc383698897

_Toc382295931

_Toc382297409

_Toc383611582

_Toc383698904

_Toc382295932

_Toc382297410

_Toc383611583

_Toc383698905

_Toc382295935

_Toc382297413

_Toc383611586

_Toc383698908

_Toc382295937

_Toc382297415

_Toc383611588

_Toc383698910

_Toc382295942

_Toc382297420

_Toc383611593

_Toc383698915

_Toc382295950

_Toc382297428

_Toc383611601

_Toc383698923

_Toc382295955

_Toc382297433

_Toc383611606

_Toc383698928

_Toc382295959

_Toc382297437

_Toc383611610
