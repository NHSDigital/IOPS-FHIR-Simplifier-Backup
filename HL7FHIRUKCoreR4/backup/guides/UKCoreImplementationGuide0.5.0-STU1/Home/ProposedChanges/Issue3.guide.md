## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>
The current binding for the Appointment.appointmentType element is to the FHIR standard v2.0276 (Appointment Reason Codes) ValueSet. The CodeSystem in this ValueSet seems to mix a number of axes of concept (e.g. kind of consultation, urgency of appointment etc), yet only single instance of the Appointment.appointmentType element is allowed.

Given the restriction to just a single instance of this data, one additional concept that may have a use in the UK is "urgent follow-up".
</td>
<td>
Create a UKCore-AppointmentReasonCode Code System consisting of a single "Urgent follow-up" concept.

Create a UKCore-AppointmentReasonCode ValueSet consisting of the entirety of the standard v2.0276 and UKCore-AppointmentReasonCode CodeSystems.

Change the binding of Appointment.appointmentType to the new UKCore-AppointmentReasonCode ValueSet with an "extensible" binding strength.
</td>
</tr>

</table>