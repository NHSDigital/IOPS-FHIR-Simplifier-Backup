---
topic: Profile-PractitionerRole-55046
---
# StructureDefinition-UKCore-PractitionerRole

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCorePractitionerRole'
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
	name = 'UKCorePractitionerRole'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Patient's GP</b>- An example to illustrate the role of General Practitioner.
<br>
{{pagelink:Example-UKCore-PractitionerRole-GP}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core PractitionerRole profile:

- Query for a Practitioner role using the query parameter identifier `PractitionerRole.identifier` for a known SDS Role Id.
- Query for a Practitioner using query parameters such as specialty `PractitionerRole.specialty` for a known specialty.
- Exchange Practitioner role information within a FHIR document or message.

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
<td><code>PractitionerRole.active</code></td>
<td>Whether this practitioner role record is in active use</td>
</tr>
<tr>
<td><code>PractitionerRole.period</code></td>
<td>The period during which the practitioner is authorised to perform in these role(s)</td>
</tr>
<tr>
<td><code>PractitionerRole.practitioner</code></td>
<td>Practitioner that is able to provide the defined services for the organization</td>
</tr>
<tr>
<td><code>PractitionerRole.organization</code></td>
<td>Organization where the roles are available</td>
</tr>
<tr>
<td><code>PractitionerRole.specialty</code></td>
<td>Specific specialty of the practitioner</td>
</tr>
<tr>
<td><code>PractitionerRole.location</code></td>
<td>The location(s) at which this practitioner provides care</td>
</tr>
<tr>
<td><code>PractitionerRole.telecom</code></td>
<td>Contact details that are specific to the role/location/service</td>
</tr>
</table>

---