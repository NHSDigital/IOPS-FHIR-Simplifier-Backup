---
topic: Profile-RequestGroup
---
# StructureDefinition-UKCore-RequestGroup

<div  id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 5. This is a new Profile added to UK Core and undergoing review under Ballot 2.
</div>

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreRequestGroup'
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
	name = 'UKCoreRequestGroup'
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
{{tree:http://hl7.org/fhir/StructureDefinition/RequestGroup, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:http://hl7.org/fhir/StructureDefinition/RequestGroup, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:http://hl7.org/fhir/StructureDefinition/RequestGroup, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/StructureDefinition/RequestGroup, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/StructureDefinition/RequestGroup, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/StructureDefinition/RequestGroup, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Paracetamol</b> - An example to illustrate a Requesting Paracetamol 500mg either oral or via IV using RequestGroup.
  <br>
  {{pagelink:Example-UKCore-RequestGroup-Paracetamol}}
  <br><br>
</div>
<nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core RequestGroup profile:

<br><br>
#### An example of the same drug, different route

This example shows how a request for the same drug through two different routes can be strucured, with the decision to the more appropriate route being taken before a dispense is made.

{{render:RequestGroup-Paracetamol}}

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
<td><code></code></td>
<td></td>
</tr>
</table>

---
