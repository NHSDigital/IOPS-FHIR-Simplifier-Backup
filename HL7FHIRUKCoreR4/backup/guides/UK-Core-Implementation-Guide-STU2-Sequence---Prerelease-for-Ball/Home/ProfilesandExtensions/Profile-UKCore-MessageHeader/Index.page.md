---
topic: Profile-MessageHeader-48618
---
# StructureDefinition-UKCore-MessageHeader

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreMessageHeader'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'UKCoreMessageHeader'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Discharge Summary</b> - An example to illustrate a message header for a discharge summary<br>
{{pagelink:Example-UKCore-MessageHeader-Discharge}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
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
<table>

---
