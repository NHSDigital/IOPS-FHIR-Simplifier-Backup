---
topic: Profile-Appointment
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment
usage: http://hl7.org/fhir/StructureDefinition/Appointment
issue: UKCore-Appointment
---

# StructureDefinition-UKCore-Appointment

<nocheck>
{{page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

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
</nocheck>


<div id="ProfileGuidance">

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Appointment profile:
- Query for appointment information for a given Patient
- Exchange appointment information within a FHIR document or message.

<hr class="thickline">

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
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
<td><code>Appointment.participant</code></td>
<td>List of participants involved in the appointment.</td>
</tr>
</table>
</div>

---

