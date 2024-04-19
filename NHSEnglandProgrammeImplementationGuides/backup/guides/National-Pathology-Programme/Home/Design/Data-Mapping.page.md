---
topic: DataMapping
---
## Data Mapping

### Overview
This page provides a set of high-level data mappings between the FHIR profiles that are referenced by this implementation guide and the [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) messaging specification. To aid traceability, the mappings are presented from two viewpoints: EDIFACT to FHIR and FHIR to EDIFACT.  

Whilst every effort has been made to ensure that the mappings are correct, they are not a normative part of the implementation guide. They are intended to provide additional guidance to suppliers who are familiar with the existing PMIP EDIFACT (NHS003) specification.

### EDIFACT to FHIR Mappings
The following diagram is based on the message structure/attribute cross-reference table that is included in Section 3 of ‘LSR_04_A_001.doc’, which forms part of the PMIP EDIFACT (NHS003) specification. The table has been updated to include the corresponding FHIR R4 element for each relevant EDIFACT attribute.

<table border=1 cellspacing=0 cellpadding=0 width=855 
 style='width:855pt;border-collapse:collapse;border:none'>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border:solid #dde1e4 1.0pt;
  border-bottom:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1073 colspan=12 valign=top style='width:804.55pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Information about the message:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; UNH</span></p>
  </td>
  <td width=52 valign=top style='width:39.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 colspan=2 valign=top style='width:14.6pt;border:none;padding:
  0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Message
  reference number</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Message
  type</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; BGM</span></p>
  </td>
  <td width=52 valign=top style='width:39.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 colspan=2 valign=top style='width:14.6pt;border:none;padding:
  0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Message
  name</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=52 valign=top style='width:39.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>A&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </span></p>
  </td>
  <td width=19 colspan=2 valign=top style='width:14.6pt;border:none;padding:
  0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Date/time
  of message generation</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1073 colspan=12 valign=top style='width:804.55pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Healthcare
  party (including Healthcare professional and Healthcare organisation) &nbsp; </span></b></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Laboratory
  service requester / Message recipient / Laboratory service provider:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG1</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>6</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S01</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; NAD</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Healthcare
  registration identification</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Name
  of healthcare organisation</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Person
  name details</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E084</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Practitioner.identifier</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E080</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Organization.name</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E092</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Practitioner.name</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; ADR</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; COM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Partner-agreed
  identification of healthcare party</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E083</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Practitioner.identifier</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SEQ</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; SPR</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Medical
  specialty of healthcare professional</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Position
  of healthcare professional</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E094</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-UKCore-PractitionerRole.specialty</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E095</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-UKCore-PractitionerRole.code</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1073 colspan=12 valign=top style='width:804.55pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Laboratory
  service report:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG2</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S02</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; GIS</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Service
  type of laboratory service report</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E183</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - N/A</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of laboratory service report by laboratory service provider</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E184</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-DiagnosticReport-Lab.identifier</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; STS</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Status
  of laboratory service</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E186</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-DiagnosticReport-Lab.status</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Issue
  date and time of laboratory service report</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E185</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-DiagnosticReport-Lab.issued</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p class=MsoToc1 style='margin-top:1.0pt;margin-right:0cm;margin-bottom:1.0pt;
  margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1040 colspan=11 valign=top style='width:780.15pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Laboratory
  service order:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG4</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S04</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FCA</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Payment
  category</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E160</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - N/A</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>2</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of laboratory service order by laboratory service requester</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of laboratory service order by laboratory service provider</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E152</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-ServiceRequest-Lab.identifier</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E153</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-ServiceRequest-Lab.identifier</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Issue
  date and time of laboratory service order</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E154</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-ServiceRequest-Lab.authoredOn</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p class=MsoToc1 style='margin-top:1.0pt;margin-right:0cm;margin-bottom:1.0pt;
  margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1040 colspan=11 valign=top style='width:780.15pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Subject
  of investigation:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG6</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S06</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of subject of investigation by laboratory service provider</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E294</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.identifier</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; ADR</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Unstructured
  address line</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Postal
  code</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E311</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.address</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E307</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.postalCode</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; COM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1008 colspan=10 valign=top style='width:755.8pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Patient:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG7</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S07</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; PNA</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Official
  patient identification</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Family
  name</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>First
  given name</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Middle
  name</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Title</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E202</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.identifier</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E313</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.name.family</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E314</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Patient.name.given</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E315</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.name.given</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E316</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.name.prefix</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>A</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Date
  and time of birth</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E218</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Patient.birthDate</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; PDI</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>A</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Patient
  administrative sex</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E217</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Patient.gender</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1008 colspan=10 valign=top style='width:755.8pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Clinical
  information:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG10</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S10</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; CIN</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Type
  of clinical observation</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E045</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-ServiceRequest-Lab.reasonCode</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>99</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Clinical
  observation description</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E046</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-ServiceRequest-Lab.reasonCode</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=975 colspan=9 valign=top style='width:731.5pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG14</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; CLI</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=943 colspan=8 valign=top style='width:707.25pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG15</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; IMD</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; DSG</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1008 colspan=10 valign=top style='width:755.8pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Specimen:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG16</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>99</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S16</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SEQ</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; SPC</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>2</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Pre-treatment
  description</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Type
  of sample</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E225</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Specimen.collection.fastingStatus[x]</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E264</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.type</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>*&nbsp;&nbsp; PRC</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>A</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>2</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of sample by laboratory service requester</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Identification
  of sample by laboratory service provider</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E262</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.identifier</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E263</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.accessionIdentifier</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>*&nbsp;&nbsp; QTY</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Numerical
  value of amount of collected sample</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Unit
  of amount of collected sample</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E055</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.collection.quantity.value</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E056</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.collection.quantity.unit</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>A</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>2</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Date
  and time of sample collection</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Date
  and time of receipt of collected sample</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E050</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.collection.collected[x]</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E061</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.receivedTime</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>9</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Laboratory
  service provider's comments to sample</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E271</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Specimen.note</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1008 colspan=10 valign=top style='width:755.8pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Laboratory
  investigation and result:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG18</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>99</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; GIS</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Service
  type of laboratory investigation result item</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E125</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - N/A</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; INV</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Measurable
  quantity attribute</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E108</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.code</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=72 colspan=3 valign=top style='width:53.95pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E108
  </span></b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>-
  UKCore-Observation-Group-Lab.code</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SEQ</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; RSL</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Numerical
  value of a measurement result</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Arithmetic
  comparator</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Unit
  of measurement result</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Deviating
  result indicator</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E129</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.valueQuantity</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E128</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.valueQuantity.comparator</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E130</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.valueQuantity.unit</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E137</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.interpretation</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; STS</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Status
  of laboratory investigation (result item)</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E139</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.status</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=72 colspan=3 valign=top style='width:53.95pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E139</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Group-Lab.status</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; DTM</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>99</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Text
  value of a laboratory investigation result item</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Comment
  to laboratory investigation result item</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Complex
  reference range information</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E136</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.valueString</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E141</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.note</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E141</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Group-Lab.note</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E330</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Observation-Lab.referenceRange.text</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=975 colspan=9 valign=top style='width:731.5pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG19</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; REL</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; RFF</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>N</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>0</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=975 colspan=9 valign=top style='width:731.5pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Reference
  limit:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; SG20</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>D</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>9</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; S20</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-top:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-top:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>+&nbsp;&nbsp; RND</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>R</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Numerical
  value of lower reference limit of quantity</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Numerical
  value of upper reference limit of quantity</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E144</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.referenceRange.low</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E145</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.referenceRange.high</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; FTX</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>O</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Reference
  population definition</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E148</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> - UKCore-Observation-Lab.referenceRange.type
  </span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=72 colspan=3 valign=top style='width:53.95pt;border:none;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>E148</span></b><span
  style='font-size:9.0pt;font-family:"Arial",sans-serif'> -
  UKCore-Observation-Lab.referenceRange.appliesTo</span></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border-top:none;border-left:solid #dde1e4 1.0pt;
  border-bottom:none;border-right:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=1073 colspan=12 valign=top style='width:804.55pt;border-top:solid #dde1e4 1.0pt;
  border-left:none;border-bottom:none;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:35.45pt'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Message
  trailer:</span></b></p>
  </td>
 </tr>
 <tr>
  <td width=33 valign=top style='width:24.4pt;border:solid #dde1e4 1.0pt;
  border-top:none;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=33 valign=top style='width:24.4pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.35pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.3pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=32 valign=top style='width:24.25pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></p>
  </td>
  <td width=60 valign=top style='width:44.9pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;&nbsp;&nbsp;&nbsp; UNT</span></p>
  </td>
  <td width=53 colspan=2 valign=top style='width:39.75pt;border:none;
  border-bottom:solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>M</span></p>
  </td>
  <td width=19 valign=top style='width:14.2pt;border:none;border-bottom:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>1</span></p>
  </td>
  <td width=406 valign=top style='width:304.75pt;border:none;border-bottom:
  solid #dde1e4 1.0pt;padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Message
  reference number</span></p>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:8.5pt'><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>Segment
  count</span></p>
  </td>
  <td width=340 valign=top style='width:9.0cm;border-top:none;border-left:none;
  border-bottom:solid #dde1e4 1.0pt;border-right:solid #dde1e4 1.0pt;
  padding:0cm 1.4pt 0cm 1.4pt'>
  <p style='margin-top:1.0pt;margin-right:0cm;margin-bottom:
  1.0pt;margin-left:0cm'><b><span style='font-size:9.0pt;font-family:"Arial",sans-serif'>&nbsp;</span></b></p>
  </td>
 </tr>
 <tr height=0>
  <td width=33 style='border:none'></td>
  <td width=33 style='border:none'></td>
  <td width=32 style='border:none'></td>
  <td width=32 style='border:none'></td>
  <td width=32 style='border:none'></td>
  <td width=32 style='border:none'></td>
  <td width=32 style='border:none'></td>
  <td width=60 style='border:none'></td>
  <td width=52 style='border:none'></td>
  <td width=1 style='border:none'></td>
  <td width=19 style='border:none'></td>
  <td width=406 style='border:none'></td>
  <td width=340 style='border:none'></td>
 </tr>
</table>

<br>

### FHIR to EDIFACT Mappings
The following tables provide a mapping between the data elements in each FHIR profile and the corresponding EDIFACT attributes.

The constraints that need to be applied to each FHIR resource using the relevant UK Core profiles are described in the individual profile pages (refer to the {{pagelink:FHIRAssetsR4Profiles}} section of this implementation guide). Only those FHIR data elements that are currently in scope (as defined in the Additional Guidance section of each profile page) are listed in the tables below.

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4DiagnosticReport}}</th>   
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E184</td>
            <td>identification of laboratory service report by laboratory service provider</td>
            <td>SG2.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E186</td>
            <td>status of laboratory service</td>
            <td>SG2.STS.C555.9011</td>
            <td>'STATUS EVENT' code is populated with a value of 'UN' (Unspecified). Refer to the definition of Segment Group 2 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>category.text</td>
            <td>E080</td>
            <td>name of healthcare organisation</td>
            <td>SG1.NAD.C080.3036(1-2)</td>
            <td>This mapping relates to the use of Segment Group 1 to carry the name of a pathology department (as text), indicated by a combination of 'PARTY QUALIFIER' = 'SLA' (Laboratory service provider) and 'SERVICE PROVIDER QUALIFIER' = 'DPT' (Department within an organisation). For example: <br><br><code>S01+01<br>NAD+SLA+++Medical Microbiology<br>SPR+DPT</code><br><br>Refer to LSR_04_A_001.doc for details.
</td>
        </tr>
        <tr>
            <td>code</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td>E185</td>
            <td>issue date and time of laboratory service report</td>
            <td>SG2.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>result</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>conclusion</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>conclusionCode</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ObservationTestGroup}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E139</td>
            <td>status of laboratory investigation (result item)</td>
            <td>SG18.STS.C555.9011</td>
            <td></td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.code</td>
            <td>E108</td>
            <td>measurable quantity attribute</td>
            <td>SG18.INV.C847.9931</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.system</td>
            <td>E108</td>
            <td>code list specifying the measurable quantity attribute</td>
            <td>SG18.INV.C847.1131</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.display</td>
            <td>E108</td>
            <td>textual representation of the code for measurable quantity attribute</td>
            <td>SG18.INV.C847.9930</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>note</td>
            <td>E141</td>
            <td>comment to laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is populated with a value of 'SPC' (Service provider's comment). Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>hasMember</td>
            <td></td>
            <td></td>
            <td></td>
            <td>The mechanism for supporting test groups, component tests within test groups and standalone tests in PMIP EDIFACT (NHS003) is described in the definition of Segment Group 18 in LSR_04_A_001.doc.</td>
        </tr>
   </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ObservationTestResult}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E139</td>
            <td>status of laboratory investigation (result item)</td>
            <td>SG18.STS.C555.9011</td>
            <td></td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.code</td>
            <td>E108</td>
            <td>measurable quantity attribute</td>
            <td>SG18.INV.C847.9931</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.system</td>
            <td>E108</td>
            <td>code list specifying the measurable quantity attribute</td>
            <td>SG18.INV.C847.1131</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.display</td>
            <td>E108</td>
            <td>textual representation of the code for measurable quantity attribute</td>
            <td>SG18.INV.C847.9930</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity</td>
            <td>E129</td>
            <td>numerical value of a measurement result</td>
            <td>SG18.RSL.C830(1).6314</td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity.comparator</td>
            <td>E128</td>
            <td>arithmetic comparator</td>
            <td>SG18.RSL.C830(1).6321</td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity.unit</td>
            <td>E130</td>
            <td>unit of measurement result</td>
            <td>SG18.RSL.C848.6410</td>
            <td></td>
        </tr>
        <tr>
            <td>valueString</td>
            <td>E136</td>
            <td>text value of a laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is populated with a value of 'RIT' (Text value of a result) for textual results. Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>dataAbsentReason</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td>E137</td>
            <td>deviating result indicator</td>
            <td>SG18.RSL.7857</td>
            <td>Partial mapping to 'RESULT NORMALCY INDICATOR, CODED' (also referred to as 'deviating result indicator'). Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>note</td>
            <td>E141</td>
            <td>comment to laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is populated with a value of 'SPC' (Service provider's comment). Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>bodySite</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>method</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.low</td>
            <td>E144</td>
            <td>numerical value of lower reference limit of quantity</td>
            <td>SG20.RND.6162</td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.high</td>
            <td>E145</td>
            <td>numerical value of upper reference limit of quantity</td>
            <td>SG20.RND.6152</td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.type<br>referenceRange.appliesTo</td>
            <td rowspan="2">E148</td>
            <td rowspan="2">reference population definition</td>
            <td rowspan="2">SG20.FTX.C108.4440(1-5)</td>
            <td rowspan="2">'TEXT SUBJECT QUALIFIER' is populated with a value of 'RPD' (Reference population definition). Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
        <tr>
            <td>referenceRange.text</td>
            <td>E330</td>
            <td>complex reference range information</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is populated with a value of 'CRR' (Complex reference range information). Refer to the definition of Segment Group 18 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>component</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Patient}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier.value</td>
            <td>E202</td>
            <td>official patient identification</td>
            <td>SG7.PNA.C206.7402</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier.value</td>
            <td>E294</td>
            <td>identification of subject of investigation by laboratory service provider</td>
            <td>SG6.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>name.family</td>
            <td>E313</td>
            <td>family name</td>
            <td>SG7.PNA.C816(1).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.given</td>
            <td>E314</td>
            <td>first given name</td>
            <td>SG7.PNA.C816(2).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.given</td>
            <td>E315</td>
            <td>middle name</td>
            <td>SG7.PNA.C816(3).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.prefix</td>
            <td>E316</td>
            <td>title</td>
            <td>SG7.PNA.C816(4).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>gender</td>
            <td>E217</td>
            <td>patient administrative sex</td>
            <td>SG7.PDI.3917</td>
            <td></td>
        </tr>
        <tr>
            <td>birthDate</td>
            <td>E218</td>
            <td>date and time of birth</td>
            <td>SG7.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>address.line<br>address.city</td>
            <td>E311</td>
            <td>unstructured address lines</td>
            <td>SG6.ADR.C090.3794(1-5)</td>
            <td></td>
        </tr>
        <tr>
            <td>address.postalCode</td>
            <td>E307</td>
            <td>postal code</td>
            <td>SG6.ADR.3251</td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Organization}} (performing)</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>active</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>name</td>
            <td>E080</td>
            <td>name of healthcare organisation</td>
            <td>SG1.NAD.C080.3036(1-2)</td>
            <td></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>address</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Practitioner}} (performer)</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E084</td>
            <td>healthcare registration identification</td>
            <td>SG1.NAD.C082.3039</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>E083</td>
            <td>partner-agreed identification of healthcare part</td>
            <td>SG1.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>name.family<br>name.given<br>name.prefix</td>
            <td>E092</td>
            <td>person name details</td>
            <td>SG1.NAD.C080.3036(1-2)</td>
            <td></td>
        </tr>  
        <tr>
            <td>telecom</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Practitioner}} (requester)</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E084</td>
            <td>healthcare registration identification</td>
            <td>SG1.NAD.C082.3039</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>E083</td>
            <td>partner-agreed identification of healthcare part</td>
            <td>SG1.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>name.family<br>name.given<br>name.prefix</td>
            <td>E092</td>
            <td>person name details</td>
            <td>SG1.NAD.C080.3036(1-2)</td>
            <td></td>
        </tr>  
        <tr>
            <td>telecom</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4PractitionerRole}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
           <tr>
            <td>active</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>period</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>practitioner</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>organization</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td>E095</td>
            <td>position of healthcare professional</td>
            <td>SG1.SPR.C846.3812</td>
            <td></td>
        </tr>
        <tr>
            <td>specialty</td>
            <td>E094</td>
            <td>medical specialty of healthcare professional</td>
            <td>SG1.SPR.C845.3811</td>
            <td></td>
        </tr>
        <tr>
            <td>location</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>        
    </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ServiceRequest}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E152</td>
            <td>identification of laboratory service order by laboratory service requester</td>
            <td>SG4.RFF.C506.1154</td>
            <td>'Reference qualifier' is populated with a value of 'ROI' (Order ID by service requester). Refer to the definition of Segment Group 4 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>E153</td>
            <td>identification of laboratory service order by laboratory service provider</td>
            <td>SG4.RFF.C506.1154</td>
            <td>'Reference qualifier' is populated with a value of 'SOI' (Order ID by service provider). Refer to the definition of Segment Group 4 in LSR_04_A_001.doc for details.</td>
        </tr>
        <tr>
            <td>requisition</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>intent</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>priority</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>authoredOn</td>
            <td>E154</td>
            <td>issue date and time of laboratory service order</td>
            <td>SG4.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>requester</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td rowspan="2">reasonCode</td>
            <td>E045</td>
            <td>type of clinical observation</td>
            <td>SG10.CIN.6810</td>
            <td></td>
        </tr>
        <tr>
            <td>E046</td>
            <td>clinical observation description</td>
            <td>SG10.FTX.C108.4440(1-5)</td>
            <td></td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>note</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Specimen}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E262</td>
            <td>identification of sample by laboratory service requester</td>
            <td>SG16.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>accessionIdentifier</td>
            <td>E263</td>
            <td>identification of sample by laboratory service provider</td>
            <td>SG16.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>type</td>
            <td>E264</td>
            <td>type of sample</td>
            <td>SG16.SPC.C832.7866</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>receivedTime</td>
            <td>E061</td>
            <td>date and time of receipt of collected sample</td>
            <td>SG16.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>request</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.collector</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.collected[x]</td>
            <td>E050</td>
            <td>date and time of sample collection</td>
            <td>SG16.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.quantity.value</td>
            <td>E055</td>
            <td>numerical value of amount of collected sample</td>
            <td>SG16.QTY.C186.6060</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.quantity.unit</td>
            <td>E056</td>
            <td>unit of amount of collected sample</td>
            <td>SG16.QTY.C848.6410</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.bodySite</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.fastingStatus[x]</td>
            <td>E225</td>
            <td>pre-treatment description</td>
            <td>SG16.SPC.C832.7867</td>
            <td></td>
        </tr>
        <tr>
            <td>condition</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>note</td>
            <td>E271</td>
            <td>laboratory service provider's comments to sample</td>
            <td>SG16.FTX.C108.4440(1-5)</td>
            <td></td>
        </tr>
    </tbody>
</table>