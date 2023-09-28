## Constraints (differential)

More information about the constraints on the <code>England-Patient</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-pat-001</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').value.matches('^([0-9]{10})$'))</td>
<td>Length of the supplied NHS Number is wrong.</td>
</tr>
</table>

---