---
title: "ReleaseNotes Artt Generator"
description: "Converted from ReleaseNotes_Artt_Generator.pdf"
---

> **Source document:** `Haitec_LC_EPS_TMS570/Tools/AsrProject/Generators/Artt/artt/ReleaseNotes_Artt_Generator.pdf`
>
> This page was converted automatically from the original document so it can be browsed online. Original format: PDF document (14 pages).

**Pages:** 14

---

Page 1 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
BMW Package Release Notes
Artt_Generator-2.0.2
Package Status:
Released
Author:
BMW Group
Version:
2.0.2
Release Date:
23-Nov-2011

Page 2 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
1 Revision History
 1.0.1
 03-Oct-2008
Initial revision. CR70051, CR70068.
 1.0.2
 29-Jun-2009
Support of more BAC2.1 templates. CR70168, 
CR70166, CR70167, CR70195, CR70237, 
CR70267.
 1.0.3
 27-Oct-2009
Performance optimization CR70341.
 1.1.0
 11-Nov-2009
User friendliness and portability CR70397, 
CR70343.
 1.1.1
 27-May-2010
CR70519.
 1.2.0
 30-Jun-2010
New validation feature CR70359, CR .
 1.3.0
 11-Oct-2010
AUTOSAR 4.0 schema CR .
 2.0.0
 15-Mar-2011
Behaviour of ValueOf() changed CR71004, 
CR71005.
 2.0.1
 14-Apr-2011
Method ModuleConfAtDefRefTo() added CR71008.
 2.0.2
 23-Nov-2011
CR71146, CR71147.
 Revision
 Date
 Remarks

Page 3 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
2 Package Enumeration Scheme
3 Package Description
artt is a command line application allowing to generate text files, including source code, from 
AUTOSAR descriptions. As input data artt uses a template file describing static content and 
structure of the desired output and one or more AUTOSAR descriptions, which are serving as 
provider for dynamic content. Since AUTOSAR descriptions are XML files, templates for artt 
typically use XPATH expressions referring to certain elements in the input file.
This package is maintained by BMW AUTOSAR Core Support, via Request Tracker (https://sc-
support.bader-muenchen.de/rt3/) or telephone hotline (+49-89-382-32233).
Every package carries a 3-digit version number. The following table explains how compatibility 
between versions can be determined from the version number:
 Minor Version
 ĺ
A new feature was added. New version is 
backwards compatible to old version.
 Major Version
 ĺ
API of package changed. Versions are not 
compatible. If the new package is used, other 
packages must be changed as well.
 Patch Version
 ĺ
A defect has been fixed. Versions are fully 
compatible.
 Changed Version
 Example
 Compatibility

Page 4 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
4 Revisions and Modifications
Revision 2.0.2 [Released]
Changed Files:
Compatibility:
Description of Changes:
Item
Description
CR ID:
CR Headline:
Description of Issues:
Changed Files:
Helper.tt
Compatibility:
Fully compatible
Description of Changes:
Changed the implementation to use the correct artt internal 
implicit bool operator to map a ValueNode to a bool.
Marked the helper function BoolValueOf and its wrapper Enabled
() as being obsolete since these helpers can simply be substuitted 
with core artt functions.
Item
Description
CR ID:
71147
CR Headline:
Wrong implementation of BoolValueOf
Description of Issues:
The included template utility file Helper.tt contained a helper 
function BoolValueOf. This implementation was wrong since it did 
not respect the various representations of bool-values allowed by 
the autosar schema.
Changed Files:
artt.chm
Compatibility:
Fully compatible
Item
Description
Description of Changes:
Extended the documentation of ChangeContext method in 
ArGtcBase to reflect that a call to ChangeContext(null) will 
successfully reset the context to the root context AND return false. 
(although one could expect that it returns true because the context 
change was successfull.
CR ID:
71146
CR Headline:
ARTT ChangeContext returns false when called with null as 
parameter.
Description of Issues:
Misleading documentation

Page 5 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 2.0.1 [Stable]
artt.chm
Changed Files:
artt.exe
Compatibility:
no restrictions to older AUTOSAR versions
Item
Description
Description of Changes:
Creates XPATH to the <c>MODULE-CONFIGURATION</c> node 
(for AUTOSAR versions before 4.0) 
or the <c>ECUC-MODULE-CONFIGURATION-VALUES</c> 
node (starting with AUTOSAR version 4.0) of the module 
configuration that is based on the module definition with the given 
shortname.
CR ID:
71008
CR Headline:
new method ModuleConfAtDefRefTo()
Description of Issues:
New method ModuleConfAtDefRefTo() added.

Page 6 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 2.0.0 [Stable]
Changed Files:
artt.exe
Compatibility:
Instead of writing:
boolean blub = <#= ValueOf(<xpath to BOOLEAN-VALUE>) #>
now it has to be written:
boolean blub = <#= (ValueOf(<xpath to BOOLEAN-VALUE>) == 
true ? “TRUE” : “FALSE”) #>
Item
Description
Description of Changes:
The method ValueOf() now always returns just the string found in 
the template file without an interpretation of it.
CR ID:
71005
CR Headline:
ValueOf-Method shall not try to interprete ECUC-BOOLEAN-
VALUE
Description of Issues:
In versions less the 2 the ValueOf() method returned the string 
found in the tt-file if it was not a boolean value. In case of a 
boolean value, it retruned "TRUE" or "FALSE".
Changed Files:
artt.exe
Compatibility:
no restrictions to older AUTOSAR versions
Item
Description
Description of Changes:
Also in case of a thrown exception in template file an output file is 
generated.
CR ID:
71004
CR Headline:
artt generator shall write output file even in case of error
Description of Issues:
Also for Environment.Exit in template file an outputfile is 
generated.

Page 7 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 1.3.0 [Released]
artt.chm
Changed Files:
artt.exe
Compatibility:
no restrictions to older AUTOSAR versions
Item
Description
Description of Changes:
Changed tags of AUTOSAR V4.0 are supported now. Depending 
on the URL given in the template or via the commandline, the tag 
name of AUTOSAR 2.x, 3.x or 4.x is used.
CR ID:
CR Headline:
Handling of the changed tags in AUTOSAR 4.0 schema.
Description of Issues:
- ECUC-MODULE-CONFIGURATION-VALUES instead of 
MODULE-CONFIGURATION (in AR < V3.x)
- ECUC- PARAM-CONF-CONTAINER-DEF instead of PARAM-
CONF-CONTAINER-DEF (in AR < V3.x)

Page 8 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 1.2.0 [Stable]
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
New set of functions added to manipulate the context using a 
stack: PushContext(), PopContext(), ClearContextStack().
See user guide for more information.
CR ID:
CR Headline:
Push- / PopContext functionality
Description of Issues:
Functionality was needed for Validation of AUTOSAR 
descriptions.
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
Implemented validation of AUTOSAR description (EPC) against 
AUTOSAR definition (BMD). Validation can be triggered by 
specifiying the AUTOSAR definition file on the command line. See 
user guide for more information.
CR ID:
70359
CR Headline:
Validation of AUTOSAR descriptions
Description of Issues:
The ARTT generator has no ability to validate the given EPC file 
against the BMD. This has the following disadvantages:
- Existence of nodes can not be ensured
- MIN/MAX/RANGE tags can not be evaluated
- Type checks of variables can not be done
- Uniqueness of container entries can not be verified

Page 9 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 1.1.1 [Released]
Changed Files:
logger.tt
Compatibility:
Description of Changes:
Artt-Generator does not return value if successfull generated.<> 0.
Item
Description
CR ID:
70519
CR Headline:
Artt-Generator continous generating even if verify failed
Description of Issues:
Artt-Generator returns success of generation.
Revision 1.1.0 [Stable]
Changed Files:
artt.exe
Compatibility:
Description of Changes:
It is now possible to declare an search path for the includes given 
in an template via command line parameter -i.
Item
Description
CR ID:
70343
CR Headline:
Include search path
Description of Issues:
The usage of the templates with includes in build systems with 
different folder structures was not possilbe.
artt.exe
Changed Files:
artt.chm
Compatibility:
Item
Description
Description of Changes:
Help file extened with the information, that a not existing output 
folder is created.
In case of a wrong command line parameter, the program returns 
an errorlevel <> 0.
CR ID:
70397
CR Headline:
Improve user friendliness
Description of Issues:
In some cases of wrong command line parameters the return 
value was an errorlevel of 0.

Page 10 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 1.0.2 [Stable]
Changed Files:
artt.exe
artt.chm
SswcT4EngineHost.dll
Compatibility:
Item
Description
CR Headline:
ARTT: Missing Include Directives.
CR ID:
70168
Description of Changes:
Added support for T4 <#@include #> directive.
Description of Issues:
Although ARTT documentation references MS T4 documentation 
(which ARTT is based on), ARTT currently does not support 
Template Include directives.
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
Fixed issue with expressions other than non-verbatim string 
literals being used in LOOP macros. Now all expressions are 
possible.
CR ID:
70166
CR Headline:
ARTT: String variables as XPATH-Expression in LOOP.
Description of Issues:
Currently only String Literals in the form "xxx" are accepted as a X
-PATH expression in a LOOP-statement.
Revision 1.0.3 [Stable]
Changed Files:
artt.exe
Compatibility:
Description of Changes:
Performance optimizations done with different means.
- Caches for Autosar shortnames to xpaths.
- Working with compiled xpaths.
Item
Description
CR ID:
70341
CR Headline:
ARTT Performance Issue
Description of Issues:
For large .epc files the template generation takes a long time 
because of the xpath search.

Page 11 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
Warnings no longer result in a generation error, i.e. the calling 
code will no longer abort the build in case of template warnings.
CR ID:
70167
CR Headline:
ARTT: Warnings shall not abort the generation process.
Description of Issues:
The ARTT generator aborts the generation process if warnings 
(like "unused variables") are encountered.
artt.chm
artt.exe
*.dll removed
artt.exe
artt.config (removed)
Changed Files:
AutosarDirectiveProcessor.dll
artt.chm
SswcT4EngineHost.dll
artt.exe
artt.exe
artt.chm
Compatibility:
An old artt.config will not be used and therefore has no influence 
on the application.
CR ID:
Item
Description
CR Headline:
Number of processed AUTOSAR files no longer limited.
Description of Changes:
The number of AUTOSAR description files is no longer limited. As 
consequence the configuration file artt.config, which specified the 
used upper limit is no longer required.
Description of Issues:
Number of AUTOSAR descriptions was limited.

Page 12 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
New XPathFactory.ContainerAtDefRefTo(): Creates XPath for a 
certain container node.
Change function XPathFactory.ModuleConf(): Return absolute 
XPath instead of relative.
New function FormatBin(): format integer to binary format with 
variable length.
new commandlineswitches for overwrite the name of the 
generated file and the namespace URI in the template
CR ID:
70237
CR Headline:
Extension of XPathFactory functionality
Description of Issues:
Better usablility.
Changed Files:
artt.exe
AutosarDirectiveProcessor.dll
artt.chm
Compatibility:
Item
Description
CR Headline:
ARTT-Generator: New convenience functions for template 
creation.
CR ID:
70195
Description of Changes:
A number of new functions have been added. In order to fit 
existing architecture, original function names were used as 
suggestion and were adapted as specified below.

The following utility functions have been added to artt: BitTest(), 
Xp.DefRefTo(), Xp.ValueAtDefRefTo(), Xp.ValueRefAtDefRefTo(), 
LastValueSegmentOf(), ModuleConf(), Xp.ShortNamePath(), 
Assert(), FormatHex(), AsBool(), RefExists().

See user guide for detailed information about the functionality of 
new and existing methods.
Description of Issues:
The functions of interest are:
- RefValueExists() (a combination of the existing functions Exists() 
and RefValueOf())
- AppendTrailingSpaces()
- LastStringAfterSlash(string xpath)
- bool BitTest(int val, bitNo)
- xpath creators (ShortName(), DefRef(), ...)
- ToHex(...)
- BoolFromString()

Page 13 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Revision 1.0.1 [Stable]
AutosarDirectiveProcessor.dll
artt.chm
SswcT4EngineHost.dll
Changed Files:
artt.exe
Microsoft.VisualStudio.TextTemplating.dll
Compatibility:
CR ID:
70051
Item
Description
CR Headline:
Artt-Generator: Failure when called from network drive.
Description of Changes:
artt executable and all required libraries were signed with a BMW 
signature. The signature can be imported on Windows machines 
that need to call artt from a network path.
Description of Issues:
When called from a network drive, artt cannot be executed due to 
a .NET runtime exception.
Changed Files:
artt.exe
artt.chm
AutosarDirectiveProcessor.dll
Compatibility:
Item
Description
CR Headline:
Support of relative XPATH references.
CR ID:
Description of Changes:
A new feature supporting relative XPATH references has been 
added through the ChangeContext() command.
Description of Issues:
artt.chm
Changed Files:
artt.exe
Compatibility:
Item
Description
Description of Changes:
Function to validate the .epc files against a via commandline 
given .xsd schema.
CR ID:
70267
CR Headline:
Validation of the given XML against a schema
Description of Issues:

Page 14 of 14
Copyright (c) 2010 by BMW Group. All rights reserved.
Changed Files:
artt.exe
artt.chm
AutosarDirectiveProcessor.dll
Compatibility:
Item
Description
CR Headline:
LOOP processing of XML nodes.
CR ID:
70068
Description of Changes:
A new feature was added to support looping over a set of 
referenced XML nodes through the LOOP command.
Description of Issues:
