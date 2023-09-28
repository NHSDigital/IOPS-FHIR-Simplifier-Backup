## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

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
<td>The period during which the practitioner is authorized to perform in these role(s)</td>
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
<tr>
<td><code>PractitionerRole.telecom.system</code></td>
<td>Telecommunications form for contact point</td>
</tr>
<tr>
<td><code>PractitionerRole.telecom.value</code></td>
<td>The actual contact point details</td>
</tr>
</table>

---