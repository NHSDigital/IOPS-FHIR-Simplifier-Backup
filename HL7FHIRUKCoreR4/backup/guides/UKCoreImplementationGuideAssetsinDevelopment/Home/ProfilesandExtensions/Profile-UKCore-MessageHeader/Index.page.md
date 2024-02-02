---
topic: Profile-MessageHeader
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader
usage: http://hl7.org/fhir/StructureDefinition/MessageHeader
issue: UKCore-MessageHeader
---
# StructureDefinition-UKCore-MessageHeader

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Discharge Summary</b> - An example to illustrate a message header for a discharge summary<br>
{{pagelink:Example-UKCore-MessageHeader-Discharge}}
</div>
</nocheck>

<div id="ProfileGuidance">

### Example Usage Scenarios

The following are feasible use cases for the UK Core OperationOutcome profile:

- Query for 
- Exchange of

<hr class="thickline">

## Profile Specific Implementation Guidance: ##


<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets" title="Minimum Viable Content list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>MessageHeader.event[x]</code></td>
<td>Code for the event this message represents or link to event definition</td>
</tr>
<tr>
<td><code>MessageHeader.destination</code></td>
<td>The destination application which the message is intended for.
</td>
</tr>
<tr>
<td><code>MessageHeader.sender</code></td>
<td>Real world sender of the message</td>
</tr>
<tr>
<td><code>MessageHeader.source</code></td>
<td>The source application from which this message originated.
</td>
</tr>
<tr>
<td><code>MessageHeader.focus</code></td>
<td>The actual content of the message</td>
</tr>
</table>
</div>

---
