## Constraints (differential)

More information about the constraints on the <code>England-OperationOutcome</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-opo-001</td>
<td>error</td>
<td>(severity = 'information') or ((severity != 'information') and details.empty().not())</td>
<td>An NHS England error or warning code is required</td>
</tr>
</table>

---