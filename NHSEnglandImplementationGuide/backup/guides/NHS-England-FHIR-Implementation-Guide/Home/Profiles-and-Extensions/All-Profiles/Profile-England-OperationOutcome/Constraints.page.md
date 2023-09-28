## Constraints (differential)

More information about the constraints on the <code>England-OperationOutcome</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width10">Severity</th>
<th class="width30">Expression</th>
<th class="width45">Human Description</th>
</tr>
<tr>
<td>nhse-opo-001</td>
<td>error</td>
<td>(severity = 'information') or ((severity != 'information') and details.empty().not())</td>
<td>An NHS England error or warning code is required</td>
</tr>
</table>

---