## Constraints (differential)

More information about the constraints on the <code>England-Immunization</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-imm-001</td>
<td>warning</td>
<td>(reference.exists() or (identifier.exists()))</td>
<td> subject - An identifier reference or resource reference must be provided.</td>
</tr>
<tr>
<td>nhse-imm-002</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').value.matches('^([0-9]{10})$'))"</td>
<td>Length of the supplied NHS Number is wrong.</td>
</tr>
<tr>
<td>nhse-imm-003</td>
<td>error</td>
<td>(reference.exists() or identifier.exists())</td>
<td>An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-imm-004</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').value.matches('^[0-9]{2}[A-Z]{1}[0-9]{4}[A-Z]{1}$'))</td>
<td>NMC must be of the format NNANNNNA</td>
</tr>
<tr>
<td>nhse-imm-005</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').value.matches('^[G]{1}[01234589]{1}[0-9]{6}$'))</td>
<td>GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)</td>
</tr>
<tr>
<td>nhse-imm-006</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').value.matches('^[C]{1}[0-9]{7}$'))</td>
<td>GMC must be of the format CNNNNNNN</td>
</tr>
<tr>
<td>nhse-imm-007</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').value.matches('^[0-9]{7}$'))</td>
<td>GPHC must be of the format NNNNNNN</td>
</tr>
<tr>
<td>nhse-imm-008</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').value.matches('^[A-Z]{2}[0-9]{6}$'))</td>
<td>HCPC must be of the format AANNNNNN</td>
</tr>
<tr>
<td>nhse-imm-009</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').value.matches('^[0-9]{6}$'))</td>
<td>DIN format must be NNNNNN</td>
</tr>
<tr>
<td>nhse-imm-010</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').value.matches('^[0-9]{12}$'))</td>
<td>SDS Role Profile Id must be 12 digits</td>
</tr>
</table>

---