---
topic: Profile-Organization
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization
---
# StructureDefinition-UKCore-Organization

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreOrganization'
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
	name = 'UKCoreOrganization'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks" onclick="openTab(event, 'Usage')">Usage</button>
</div>

<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree, buttons}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>{{pagelink:Example-UKCore-Organization-WhiteRoseMedicalCentre}}   <br><br>

<b>Hospital</b> - Example to illustrate a Hospital organisation.
</br>{{pagelink:Example-UKCore-Organization-LeedsTeachingHospital}}   <br><br>

<b>Main Location</b> - Example to illustrate the mainLocation extension.
</br>{{pagelink:Example-UKCore-Extension-MainLocation}}   <br><br>

<b>Organization Period</b> - Example to illustrate the core-defined organization-period extension.
</br>{{pagelink:Example-UKCore-Extension-OrganizationPeriod}}
</div>
</nocheck>

### Example Usage Scenarios ###

- Query for organisation information using the query parameter identifier `Organization.identifier` for a known ODS code.
- Exchange organisation information within a FHIR document or message.

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
<td><code>Organization.identifier</code></td>
<td>Identifies this organization across multiple systems</td>
</tr>
<tr>
<td><code>Organization.identifier.system</code></td>
<td>a URL that describes a set values that are unique.</td>
</tr>
<tr>
<td><code>Organization.identifier.value</code></td>
<td>The value that is unique</td>
</tr>
<tr>
<td><code>Organization.active</code></td>
<td>Whether the organization's record is still in active use</td>
</tr>
<tr>
<td><code>Organization.name</code></td>
<td>A name associated with the organization.</td>
</tr>
<tr>
<td><code>Organization.telecom</code></td>
<td>A contact detail for the organization.</td>
</tr>
<tr>
<td><code>Organization.address</code></td>
<td>An address for the organization.</td>
</tr>
</table>

---