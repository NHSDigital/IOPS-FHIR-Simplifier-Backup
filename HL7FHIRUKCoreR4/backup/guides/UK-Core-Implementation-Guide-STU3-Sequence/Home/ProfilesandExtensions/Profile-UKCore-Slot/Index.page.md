---
topic: Profile-Slot
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Slot
usage: http://hl7.org/fhir/StructureDefinition/Slot
issue: UKCore-Slot
---
# StructureDefinition-UKCore-Slot

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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
<td><code>Slot.specialty</code></td>
<td>The specialty of a practitioner that would be required to perform the service requested in this appointment.</td>
</tr>
<td><code>Slot.appointmentType</code></td>
<td>The style of appointment or patient that may be booked in the slot.</td>
</tr>
<td><code>Slot.status</code></td>
<td>The status of the slot, e.g free, busy, etc.</td>
</tr>
<td><code>Slot.start</code></td>
<td>Date/Time that the slot is to begin.</td>
</tr>
<td><code>Slot.end</code></td>
<td>Date/Time that the slot is to conclude.</td>
</tr>
</table>

---