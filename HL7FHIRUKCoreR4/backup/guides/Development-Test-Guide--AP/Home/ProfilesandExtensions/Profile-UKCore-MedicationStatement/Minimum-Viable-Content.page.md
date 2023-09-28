## Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>MedicationStatement.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources.</td>
</tr>
<tr>
<td><code>MedicationStatement.basedOn</code></td>
<td>To reference to a <code>MedicationRequest</code> resource, where applicable.</td>
</tr>
<tr>
<td><code>MedicationStatement.status</code></td>
<td>A code representing the patient or other source's judgement about the state of the medication used that this statement is about.</td>
</tr>
<tr>
<td><code>MedicationStatement.category</code></td>
<td>Indicates where the medication is expected to be consumed or administered.
</td>
</tr>
<tr>
<td><code>MedicationStatement.medication[x]</code></td>
<td>Identifies the medication being administered. </td>
</tr>
<tr>
<td><code>MedicationStatement.subject</code></td>
<td>Who is/was taking the medication.</td>
</tr>
<tr>
<td><code>MedicationStatement.effective[x]</code></td>
<td>To timestamp the statement</td>
</tr>
<tr>
<td><code>MedicationStatement.dateAsserted</code></td>
<td>To timestamp the statement assertion</td>
</tr>
<tr>
<td><code>MedicationStatement.informationSource</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.derivedFrom</code></td>
<td>To reference other resources, where applicable</td>
</tr>
<tr>
<td><code>MedicationStatement.dosage</code></td>
<td>For the dosage for the statement</td>
</tr>
</table>

---