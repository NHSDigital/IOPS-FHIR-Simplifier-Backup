# Introduction

The UK Core Hazard Log is a mechanism for recording and communicating the on-going identification and mitigation of hazards associated with HL7 FHIR® UK Core R4. It is organised so that it enables a systematic approach to the management of hazards and supports the effective collation of safety case evidence. Such on-going revisions will:
- incorporate new hazards, when identified
- record the mitigation of defined hazards through the implementation of clinical risk control mechanisms
- reference supporting evidence
- record the status of actions.

The Hazard Log is a living document and continues to be updated during the lifecycle of the UK Core.

Each version of the Hazard Log has to be reviewed and approved by the Clinical Safety Officer to signify that the clinical safety information recorded is accurate and appropriate.

To make software clinically safe, clinical risk management standards must be met which have been established in law through the Health and Social Care Act 2012.

There are two clinical risk management standards:
- DCB0129 is for organisations building software
- DCB0160 is for care organisations that are deploying and using software

The standards ensure potential clinical hazards are identified and suitable mitigations are put in place to minimise associated clinical risks.

<br><br>

This UK Core hazard log records generic hazards separated into:
- {{pagelink:UK-Core-Development-e149f5a3-e1bf-4800-9c33-713a44ef4a3e}} for NHS England 
- {{pagelink:UK-Core-Implementation-641b7675-9a2d-4a54-aba8-b3917c0b2abb}} for vendors.

A nominated Clinical Safety Officer (CSO) is responsible for making sure that these clinical risk management requirements are effectively met.

---

## Risk Matrix
<style>

.column {
  float: left;
  width: 50%;
  padding: 5px;
}

/* Clearfix (clear floats) */
.row::after {
  content: "";
  clear: both;
  display: table;
}

td { 
    padding: 10px;
}
th { 
    padding: 10px;
}
.matrixTable {
  border-collapse: collapse;
  width: 100%;
}
.centerTd {
  text-align: center; 
}
.bigCell{
  border:1px solid black; height: 34px
}
</style>

<table class="matrixTable";>
<tr>
  <td ROWSPAN=5 bgcolor='#c5e0b3' class="bigCell centerTd" width="10%">
  <SPAN STYLE="writing-mode: vertical-lr;
        font-weight:bold;
        -ms-writing-mode: tb-rl;
        transform: rotate(180deg);" >Likelihood</SPAN></TD>
  <td width="12%"; bgcolor='#c5e0b3'; class="bigCell centerTd">Very High</th>
  <td width="15%"; class="bigCell centerTd risk3">3</th>
  <td width="15%"; class="bigCell centerTd risk4">4</th>
  <td width="15%"; class="bigCell centerTd risk4">4</th>
  <td width="15%"; class="bigCell centerTd risk5">5</th>
  <td width="15%"; class="bigCell centerTd risk5">5</th>
</tr>
<tr>
  <td bgcolor='#c5e0b3'; class="bigCell centerTd">High</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell centerTd risk4">4</td>
  <td class="bigCell centerTd risk5">5</td>
</tr>
<tr>
  <td bgcolor='#c5e0b3'; class="bigCell centerTd">Medium</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell centerTd risk4">4</td>
</tr>
<tr>
  <td bgcolor='#c5e0b3'; class="bigCell centerTd">Low</td>
  <td class="bigCell centerTd risk1">1</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell centerTd risk4">4</td>
<tr>
  <td bgcolor='#c5e0b3'; class="bigCell centerTd">Very Low</td>
  <td class="bigCell centerTd risk1">1</td>
  <td class="bigCell centerTd risk1">1</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell centerTd risk3">3</td>
</tr>
<tr>
  <td></td>
  <td></td>
  <td bgcolor='#b4c6e7'; class="bigCell centerTd">Minor</td>
  <td bgcolor='#b4c6e7'; class="bigCell centerTd">Significant</td>
  <td bgcolor='#b4c6e7'; class="bigCell centerTd">Considerable</td>
  <td bgcolor='#b4c6e7'; class="bigCell centerTd">Major</td>
  <td bgcolor='#b4c6e7'; class="bigCell centerTd">Catastrophic</td>
<tr>
  <td></td>
  <td></td>
  <td colspan=5; bgcolor='#b4c6e7'; class="bigCell centerTd">
  <SPAN STYLE= font-weight:bold; >Consequence</SPAN>
  </td>
</tr>
</table>
<br><br>

## Risk Rating

<table id="assets" width=100%>
<tr>
  <th class="bigCell centerTd">Risk Rating </th>
  <th class="bigCell centerTd">Definition</th>
</tr>
<tr>
  <td class="bigCell centerTd risk5">5</td>
  <td class="bigCell";>Unacceptable level of risk.</td>
</tr>
<tr>
  <td class="bigCell centerTd risk4">4</td>
  <td class="bigCell";>Mandatory elimination or control to reduce risk to an acceptable level.</td>
</tr>
<tr>
  <td class="bigCell centerTd risk3">3</td>
  <td class="bigCell"; > Undesirable level of risk.<br>
Attempts should be made to eliminate or control to reduce risk to an acceptable level.  Shall only be acceptable when further risk reduction is impractical.
  </td>
</tr>
<tr>
  <td class="bigCell centerTd risk2">2</td>
  <td class="bigCell">Acceptable where cost of further reduction outweighs benefits gained.</td>
</tr>
<tr>
  <td class="bigCell centerTd risk1">1</td>
  <td class="bigCell">Acceptable, no further action required.</td>
</tr>
</table>

<br><br>

---

## Interpretations

### Likelihood Interpretation


<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
 
</style>

<table id="assets">
<tr>
  <th class="bigCell centerTd">Likelihood Category </th>
  <th class="bigCell centerTd">Interpretation</th>
</tr>
<tr>
  <td class="bigCell centerTd"; >Very High</td>
  <td class="bigCell centerTd";>Certain or almost certain; highly likely to occur</td>
</tr>
<tr>
  <td class="bigCell centerTd"; >High</td>
  <td class="bigCell centerTd";>Not certain but very possible; reasonably expected to occur in the majority of cases</td>
</tr>
<tr>
  <td class="bigCell centerTd";>Medium</td>
  <td class="bigCell centerTd"; >Possible</td>
</tr>
<tr>
  <td class="bigCell centerTd">Low</td>
  <td class="bigCell centerTd">Could occur but in the great majority of occasions will not</td>
</tr>
<tr>
  <td class="bigCell centerTd">Very Low</td>
  <td class="bigCell centerTd">Negligible or nearly negligible possibility of occurring</td>
</tr>
</table>

<br><br>

### Consequence Interpretation

<table id="valuesetlist">
<tr>
  <th class="bigCell centerTd">Consequence Category</th>
  <th class="bigCell centerTd">Consequence</th>
  <th class="bigCell centerTd">Patients Affected</th>
</tr>
<tr>
  <td rowspan=2; class="bigCell centerTd">Catastrophic</td>
  <td class="bigCell centerTd">Death</td>
  <td class="bigCell centerTd">Multiple</td>
</tr>
<tr>
  <td class="bigCell centerTd">Permanent life-changing incapacity and any condition for which the prognosis is death or permanent life-changing incapacity; severe injury or severe incapacity from which recovery is not expected in the short term</td>
  <td class="bigCell centerTd">Multiple</td>
</tr>

<tr>
<td colspan="3"  class="override"></td>
</tr>

<tr>
  <td  rowspan=4; class="bigCell centerTd">Major</td>
  <td class="bigCell centerTd">Death</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
  <td class="bigCell centerTd">Permanent life-changing incapacity and any condition for which the prognosis is death or permanent life-changing incapacity; severe injury or severe incapacity from which recovery is not expected in the short term</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
<td class="bigCell centerTd">Severe injury or severe incapacity from which recovery is expected in the short term
</td>
<td class="bigCell centerTd">Multiple</td>
</tr>
<tr>
<td class="bigCell centerTd">Severe psychological trauma
</td>
<td class="bigCell centerTd">Multiple</td>
</tr>

<tr>
<td colspan="3"  class="override"></td>
</tr>

<tr>
  <td  rowspan=4; class="bigCell centerTd">Considerable</td>
  <td class="bigCell centerTd">Severe injury or severe incapacity from which recovery is expected in the short term</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
  <td class="bigCell centerTd">Severe psychological trauma</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
<td class="bigCell centerTd">Minor injury or injuries from which recovery is not expected in the short term.</td>
<td class="bigCell centerTd">Multiple</td>
</tr>
<tr>
<td class="bigCell centerTd">Significant psychological trauma</td>
<td class="bigCell centerTd">Multiple</td>
</tr>

<tr>
<td colspan="3"  class="override"></td>
</tr>

<tr>
  <td  rowspan=4; class="bigCell centerTd">Significant</td>
  <td class="bigCell centerTd">Minor injury or injuries from which recovery is not expected in the short term</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
  <td class="bigCell centerTd">Significant psychological trauma</td>
  <td class="bigCell centerTd">Single</td>
</tr>
<tr>
<td class="bigCell centerTd">Minor injury from which recovery is expected in the short term</td>
<td class="bigCell centerTd">Multiple</td>
</tr>
<tr>
<td class="bigCell centerTd">Minor psychological upset; inconvenience</td>
<td class="bigCell centerTd">Multiple</td>
</tr>

<tr>
<td colspan="3"  class="override"></td>
</tr>

<tr>
<td class="bigCell centerTd">Minor</td>
  <td class="bigCell centerTd">Minor injury from which recovery is expected in the short term; minor psychological upset; inconvenience; any negligible consequence</td>
  <td class="bigCell centerTd">Single</td>
</tr>
</table>
