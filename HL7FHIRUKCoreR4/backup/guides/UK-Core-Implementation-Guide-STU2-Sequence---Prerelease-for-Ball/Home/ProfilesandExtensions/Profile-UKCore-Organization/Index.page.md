---
topic: Profile-Organization-94604
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Hospital</b> - Example to illustrate a Hospital organisation.
</br>{{pagelink:Example-UKCore-Organization-LeedsTeachingHospital}}   <br><br>

<b>General Practice</b> - Example to illustrate a General Practice organisation.
</br>{{pagelink:Example-UKCore-Organization-WhiteRoseMedicalCentre}}   <br><br>

<b>Extension - mainLocation</b> - Example to illustrate the mainLocation extension.
</br>{{pagelink:Example-UKCore-Organization-Extension-MainLocation}}   <br><br>

<b>Extension - organizationPeriod</b> - Example to illustrate the core-defined organization-period extension.
</br>{{pagelink:Example-UKCore-Organization-Extension-OrganizationPeriod}}
</div>
</nocheck>

### Example Usage Scenarios ###

- Query for organisation information using the query parameter identifier `Organization.identifier` for a known ODS code.
- Exchange organisation information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##


### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Organization.identifier</code></td>
<td>Identifies this organisation across multiple systems</td>
</tr>
<tr>
<td><code>Organization.active</code></td>
<td>Whether the organisation's record is still in active use</td>
</tr>
<tr>
<td><code>Organization.name</code></td>
<td>A name associated with the organisation.</td>
</tr>
<tr>
<td><code>Organization.telecom</code></td>
<td>A contact detail for the organisation.</td>
</tr>
<tr>
<td><code>Organization.address</code></td>
<td>An address for the organisation.</td>
</tr>
</table>

---