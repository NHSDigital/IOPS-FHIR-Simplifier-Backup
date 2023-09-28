## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Patient.identifier</code></td>
<td>An identifier for this patient.</td>
</tr>
<tr>
<td><code>Patient.identifier.system</code></td>
<td>The namespace for the identifier value.</td>
</tr>
<tr>
<td><code>Patient.identifier.value</code></td>
<td>The portion of the identifier typically relevant to the user and which is unique within the context of the system.</td>
</tr>
<tr>
<td><code>Patient.active</code></td>
<td>Whether this patient's record is in active use.</td>
</tr>
<tr>
<td><code>Patient.name</code></td>
<td>A name associated with the patient.</td>
</tr>
<tr>
<td><code>Patient.name.family</code></td>
<td>Family name (often called 'Surname').</td>
</tr>
<tr>
<td><code>Patient.name.given</code></td>
<td>Given names (not always 'first'). Includes middle names.</td>
</tr>
<tr>
<td><code>Patient.telecom</code></td>
<td>A contact detail for the individual</td>
</tr>
<tr>
<td><code>Patient.telecom.system</code></td>
<td>Telecommunications form for contact point</td>
</tr>
<tr>
<td><code>Patient.telecom.value</code></td>
<td>The actual contact point details</td>
</tr>
<tr>
<td><code>Patient.gender</code></td>
<td> the gender that the patient is considered to have for administration and record keeping purposes.</td>
</tr>
<tr>
<td><code>Patient.birthDate</code></td>
<td>The date of birth for the individual.</td>
</tr>
<tr>
<td><code>Patient.address</code></td>
<td>An address for the individual
</td>
</tr>
<tr>
<td><code>Patient.address.line</code></td>
<td>Street name, number, direction & P.O. Box etc.</td>
</tr>
<tr>
<td><code>Patient.address.city</code></td>
<td>Name of city, town etc.</td>
</tr>
<tr>
<td><code>Patient.address.postalCode</code></td>
<td>Postal code for area</td>
</tr>
</table>

---