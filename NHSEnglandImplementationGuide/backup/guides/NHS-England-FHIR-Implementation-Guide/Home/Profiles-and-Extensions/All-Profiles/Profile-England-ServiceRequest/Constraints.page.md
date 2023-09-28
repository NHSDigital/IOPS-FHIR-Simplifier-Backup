## Constraints (differential)

More information about the constraints on the <code>England-ServiceRequest</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width10">Severity</th>
<th class="width30">Expression</th>
<th class="width45">Human Description</th>
</tr>
<tr>
<td>nhse-prr-001</td>
<td>error</td>
<td>(reference.exists() or identifier.exists())</td>
<td>An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-prr-002</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').value.matches('^([0-9]{10})$'))</td>
<td>Length of the supplied NHS Number is wrong.</td>
</tr>
</table>

---