## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

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
<td>Reference to the Appointment, Condition, Procedure, or ImmunizationRecommendation that is the reason for the appointment</td>
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