## Minimum Viable Content

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>OperationOutcome.issue</code></td>
<td>A single issue associated with the action</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.severity</code></td>
<td>Indicates how relevant the issue is to the overall success of the action. This is labelled as "Is Modifier" because applications should not confuse hints and warnings with errors.</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.code</code></td>
<td>Error or warning code</td>
</tr>
<tr>
<td><code>OperationOutcome.issue.expression</code></td>
<td>FHIRPath of element(s) related to issue</td>
</tr>
</table>

---