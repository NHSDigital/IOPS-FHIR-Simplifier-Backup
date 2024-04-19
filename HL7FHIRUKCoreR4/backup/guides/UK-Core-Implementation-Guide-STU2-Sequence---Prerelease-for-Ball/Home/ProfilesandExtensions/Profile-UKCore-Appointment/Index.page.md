---
topic: Profile-Appointment-87479
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Orthopaedic Surgery</b> - An example to illustrate an Orthopaedic Surgery appointment.<br/>
{{pagelink:Example-UKCore-Appointment-OrthopaedicSurgery}}
<br/><br/>
<b>Booking Organization</b> - An example to illustrate the booking organization extension associated with an appointment.<br/>
{{pagelink:Example-UKCore-Appointment-Extension-BookingOrganization}}
<br/><br/>
<b>Delivery Channel</b> - An example to illustrate the delivery channel associated with an appointment.<br/>
{{pagelink:Example-UKCore-Appointment-Extension-DeliveryChannel}}

</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Appointment profile:
- Query for appointment information for a given Patient
- Exchange appointment information within a FHIR document or message.

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
<td><code>Appointment.basedOn</code></td>
<td>The service request this appointment is allocated to assess</td>
</tr>
<tr>
<td><code>Appointment.participant</code></td>
<td>List of participants involved in the appointment.</td>
</tr>
</table>

---

