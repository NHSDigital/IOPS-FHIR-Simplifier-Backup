---
topic: Profile-Slot-83549
---
# StructureDefinition-UKCore-Slot

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreSlot'
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
	name = 'UKCoreSlot'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Available Walk In Visit</b> - An example to illustrate a slot regarding a walk in visit.
  <br>
  {{pagelink:Example-UKCore-Slot-AvailableWalkInVisit}}
  <br><br>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Slot profile:
- Query for slot information from a given schedule
- Exchange slot information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Slot.specialty</code></td>
<td>The specialty of a practitioner that would be required to perform the service requested in this appointment.</td>
</tr>
<tr>
<td><code>Slot.appointmentType</code></td>
<td>The style of appointment or patient that may be booked in the slot.</td>
</tr>
<tr>
<td><code>Slot.schedule</code></td>
<td>A reference to a Schedule resource.</td>
</tr>
<tr>
<td><code>Slot.status</code></td>
<td>The status of the slot, e.g free, busy, etc.</td>
</tr>
<tr>
<td><code>Slot.start</code></td>
<td>Date/Time that the slot is to begin.</td>
</tr>
<tr>
<td><code>Slot.end</code></td>
<td>Date/Time that the slot is to conclude.</td>
</tr>
</table>
</div>

---