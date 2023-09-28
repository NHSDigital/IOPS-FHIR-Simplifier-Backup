---
topic: Profile-Appointment
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment
---

# StructureDefinition-UKCore-Appointment

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreAppointment'
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
	name = 'UKCoreAppointment'
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
  <b>Orthopaedic Surgery</b> - An example to illustrate an Orthopaedic Surgery appointment.<br/>
{{pagelink:Example-UKCore-Appointment-OrthopaedicSurgery}}
<br/><br/>
<b>Booking Organization</b> - An example to illustrate the booking organization extension associated with an appointment.<br/>
{{pagelink:Example-UKCore-Extension-BookingOrganization}}
<br/><br/>
<b>Delivery Channel</b> - An example to illustrate the delivery channel associated with an appointment.<br/>
{{pagelink:Example-UKCore-Extension-DeliveryChannel}}

</div>

<div id="Usage" class="tabcontent">
  <h3>Usage</h3>
  This Profile has the following derived profiles:<br>
<span id="usage">
@```
  from
	StructureDefinition
select id,baseDefinition,status
  where baseDefinition = 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment'
  and status = 'active'
```
</span>
<br><br>
  This Profile is referenced in the following Extensions: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment'
```
</span>
<br><br>
  This Profile is referenced in the following Profiles: <br>
<span id="usage">
@```
from
	StructureDefinition
  where type !='Extension' and status = 'active'
 select id,
	for differential.element
	select
	join type {targetProfile}
	where targetProfile contains 'https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment'
```
</span>
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Appointment profile:
- Query for appointment information for a given Patient
- Exchange appointment information within a FHIR document or message.

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
<td><code>Appointment.status</code></td>
<td>The overall status of the appointment.</td>
</tr>
<tr>
<td><code>Appointment.specialty</code></td>
<td>The specialty of a practitioner that would be required to perform the service requested in this appointment</td>
</tr>
<tr>
<td><code>Appointment.appointmentType</code></td>
<td>The type of appointment or patient that has been booked in the slot</td>
</tr>
<tr>
<td><code>Appointment.reasonCode</code></td>
<td>Reason for the appointment</td>
</tr>
<tr>
<td><code>Appointment.reasonReference</code></td>
<td>Reference to the Observation, Condition, Procedure, or ImmunizationRecommendation that is the reason for the appointment</td>
</tr>
<tr>
<td><code>Appointment.start</code></td>
<td>Start time of the appointment </td>
</tr>
<tr>
<td><code>Appointment.end</code></td>
<td>End time of the appointment </td>
</tr>
<tr>
<td><code>Appointment.basedOn</code></td>
<td>The service request this appointment is allocated to assess</td>
</tr>
<tr>
<td><code>Appointment.basedOn.identifier</code></td>
<td>Logical reference, when literal reference is not known</td>
</tr>
<tr>
<td><code>Appointment.participant</code></td>
<td>List of participants involved in the appointment.</td>
</tr>
<tr>
<td><code>Appointment.participant.actor</code></td>
<td>A Person, Location, HealthcareService, or Device that is participating in the appointment.</td>
</tr>
</table>

---

