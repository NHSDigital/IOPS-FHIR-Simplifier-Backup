## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>DiagnosticReport.status</code></td>
<td>The status of the diagnostic report.
</td>
</tr>
<tr>
<td><code>DiagnosticReport.category</code></td>
<td>A code that classifies the clinical discipline, department or diagnostic service that created the report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.code</code></td>
<td>A code or name that describes this diagnostic report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.subject</code></td>
<td>The subject of the report - usually, but not always, the patient</td>
</tr>
<tr>
<td><code>DiagnosticReport.encounter</code></td>
<td>Health care event when test ordered.</td>
</tr>
<tr>
<td><code>DiagnosticReport.effective[x]</code></td>
<td>Clinically relevant time/time-period for report.</td>
</tr>
<tr>
<td><code>DiagnosticReport.result</code></td>
<td>Observations that are part of this diagnostic report.</td>
</tr>
</table>

---