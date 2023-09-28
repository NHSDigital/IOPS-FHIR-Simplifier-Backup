## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Encounter.identifier</code></td>
<td>Identifier(s) by which this encounter is known.</td>
</tr>
<tr>
<td><code>Encounter.class</code></td>
<td>Concepts representing classification of patient encounter such as ambulatory (outpatient), inpatient, emergency, home health or others due to local variations.</td>
</tr>
<tr>
<td><code>Encounter.subject</code></td>
<td>The patient or group present at the encounter.</td>
</tr>
<tr>
<td><code>Encounter.participant</code></td>
<td>The list of people responsible for providing the service.</td>
</tr>
<tr>
<td><code>Encounter.participant.individual</code></td>
<td>Persons involved in the encounter other than the patient.</td>
</tr>
<tr>
<td><code>Encounter.reasonCode</code></td>
<td>Reason the encounter takes place, expressed as a code. For admissions, this can be used for a coded admission diagnosis.</td>
</tr>
<tr>
<td><code>Encounter.reasonReference</code></td>
<td>Reason the encounter takes place, expressed as a reference to a Condition, Procedure, Observation, or ImmunizationRecommendation.</td>
</tr>
</table>

---