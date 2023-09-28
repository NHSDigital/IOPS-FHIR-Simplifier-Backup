## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>MedicationRequest.identifier</code></td>
<td>Allow the resource to be referenced within/by other resources</td>
</tr>
<tr>
<td><code>MedicationRequest.status</code></td>
<td>A code specifying the current state of the order.</td>
</tr>
<tr>
<td><code>MedicationRequest.intent</code></td>
<td>Whether the request is a proposal, plan, or an original order.</td>
</tr>
<tr>
<td><code>MedicationRequest.category</code></td>
<td>Provides the business context for the relevant dispensing processes</td>
</tr>
<tr>
<td><code>MedicationRequest.medication[x]</code></td>
<td>Identifies the medication being requested.</td>
</tr>
<tr>
<td><code>MedicationRequest.subject</code></td>
<td>Who medication request is for</td>
</tr>
<tr>
<td><code>MedicationRequest.authoredOn</code></td>
<td>To timestamp the event</td>
</tr>
<tr>
<td><code>MedicationRequest.requester</code></td>
<td>Who is requesting the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction</code></td>
<td>Dosage instructions for the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.text</code></td>
<td>Free text dosage instructions.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.timing</code></td>
<td>When medication should be administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate</code></td>
<td>Dosage instructions for the medication</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate.dose[x]</code></td>
<td>Quantity of medication administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction.doseAndRate.rate[x]</code></td>
<td>Rate at which the medication is to be administered.</td>
</tr>
<tr>
<td><code>MedicationRequest.dosageInstruction</code></td>
<td>Dosage instructions for the medication.</td>
</tr>
<tr>
<td><code>MedicationRequest.dispenseRequest</code></td>
<td>Specific dispensing quantity instructions.</td>
</tr>
<tr>
<td><code>MedicationRequest.dispenseRequest.quantity</code></td>
<td>Amount of medication to supply per dispense.</td>
</tr>
<tr>
<td><code>MedicationRequest.substitution</code></td>
<td>Any restrictions on medication substitution.</td>
</tr>
</table>

---