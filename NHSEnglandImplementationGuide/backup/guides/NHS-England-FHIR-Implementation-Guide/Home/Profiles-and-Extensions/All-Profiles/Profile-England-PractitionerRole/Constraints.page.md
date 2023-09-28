## Constraints (differential)

More information about the constraints on the <code>England-PractitionerRole</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width10">Severity</th>
<th class="width30">Expression</th>
<th class="width45">Human Description</th>
</tr>
<tr>
<td>nhse-pro-001</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/sds-role-profile-id').value.matches('^[0-9]{12}$'))
</td>
<td>SDS Role Profile Id must be 12 digits</td>
</tr>
<tr>
<td>nhse-pro-002</td>
<td>warning</td>
<td>(reference.exists() or identifier.exists())
</td>
<td>An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-pro-003</td>
<td>warning</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/nmc-number').value.matches('^[0-9]{2}[A-Z]{1}[0-9]{4}[A-Z]{1}$'))
</td>
<td>NMC must be of the format NNANNNNA</td>
</tr>
<tr>
<td>nhse-pro-004</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmp-number').value.matches('^[G]{1}[01234589]{1}[0-9]{6}$'))
</td>
<td>GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)</td>
</tr>
<tr>
<td>nhse-pro-005</td>
<td>error</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-number').value.matches('^[C]{1}[0-9]{7}$'))
</td>
<td>GMC must be of the format CNNNNNNN</td>
</tr>
<tr>
<td>nhse-pro-006</td>
<td>warning</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').value.matches('^[0-9]{7}$'))
</td>
<td>GPHC must be of the format NNNNNNN</td>
</tr>
<tr>
<td>nhse-pro-007</td>
<td>warning</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/hcpc-number').value.matches('^[A-Z]{2}[0-9]{6}$'))
</td>
<td>HCPC must be of the format AANNNNNN</td>
</tr>
<tr>
<td>nhse-pro-008</td>
<td>warning</td>
<td>identifier.exists().not() or identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/din-number').value.matches('^[0-9]{6}$'))
</td>
<td>DIN format must be NNNNNN</td>
</tr>
<tr>
<td>nhse-pro-009</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/sds-user-id').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/sds-user-id').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/sds-user-id').value.matches('^[0-9]+$'))
</td>
<td>sds-user-id must be numeric</td>
</tr>
<tr>
<td>nhse-pro-010</td>
<td>error</td>
<td>identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-reference-number').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/gphc-number').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/gmc-reference-number').value.matches('^[0-9]{7}$'))
</td>
<td>GMC Reference Number must be of the format NNNNNNN</td>
</tr>
<tr>
<td>nhse-pro-011</td>
<td>warning</td>
<td>identifier.where(system='https://fhir.hl7.org.uk/Id/professional-code').exists().not()
</td>
<td>NACS (/ODS) Practitioner Identifier is retired in NHS FHIR and should not be used. Please use the actual naming system instead (e,g, https://fhir.hl7.org.uk/Id/gmc-number, https://fhir.hl7.org.uk/Id/gmp-number, etc).</td>
</tr>
<tr>
<td>nhse-pro-012</td>
<td>warning</td>
<td>(reference.exists() or identifier.exists())
</td>
<td>PractitionerRole.organization - An identifier reference or resource reference should be provided</td>
</tr>
<tr>
<td>nhse-pro-013</td>
<td>error</td>
<td>(reference.exists() or identifier.exists())
</td>
<td>PractitionerRole.location - An identifier or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-pro-014</td>
<td>error</td>
<td>(reference.exists() or (identifier.exists()))
</td>
<td>PractitionerRole.healthcareService - An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-pro-015</td>
<td>warning</td>
<td>identifier.where(system='https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code').exists().not() or (identifier.where(system='https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code').exists()  and identifier.where(system='https://fhir.hl7.org.uk/Id/nhsbsa-spurious-code').value.matches('^[G]{1}[67]{1}[0-9]{6}$'))
</td>
<td>Spurious Code format must be G6NNNNNN or G7NNNNNN</td>
</tr>
</table>

---

