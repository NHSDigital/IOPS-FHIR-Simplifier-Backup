## `identifier`

The `Practitioner.identifier` can be populated using the examples given below.

<table class="assets">
<tr>
<th width="20%">Role</th>
<th width="30%">Identifier</th>
<th width="20%">Format</th>
<th width="30%">System</th>
</tr>
<tr>
<td>Doctors</td>
<td>General Medical Council Information (GMC) registration number</td>
<td>7 digits OR L + 6 digits. </br>L prefix is for limited registrations.</td>
<td>https://fhir.hl7.org.uk/Id/gmc-number</td>
</tr>
<td>Pharmacist</td>
<td>General Pharmaceutical Council (GPhC) registration number</td>
<td>7 digit number starting with the number 2.</td>
<td>https://fhir.hl7.org.uk/Id/gphc-number</td>
</tr>
<td>Nurses, Midwives, Health Visitors</td>
<td>Nursing and Midwifery Council (NMC) registration number</td>
<td>8 character alphanumeric pin.</td>
<td>https://fhir.hl7.org.uk/Id/nmc-number</td>
</tr>
<td>Other Health Care Professions (HCPs)</td>
<td>Health and Care Professions Council (HCPC) registration number</td>
<td>Up to 6 numbers, and starts with 2 letters. </br>For example **PH123456** </td>
<td>https://fhir.hl7.org.uk/Id/hcpc-number</td>
</tr>

<td>Other (England)</td>
<td>Spine Directory Service (SDS) User ID</td>
<td>Refer to Spine Directory Service - FHIR API</td>
<td> NA</td>
</tr>
<td>Other</td>
<td>Other identifier e.g. local ID</td>
<td>Implementation specific</td>
<td>NA</td>
</tr>
</table>
<br>
More information about the GMC, GPhC, and NMC registration numbers can be found within the Glossary, under NHS Data Model and Dictionary.
<br>
More information about SDS can be found within the Glossary, under Spine Directory Service.
<br>
<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Breaking Change</h4>
The minimum cardinality of <code>Practitioner.identifier.system</code> and <code>Practitioner.identifier.value</code>reset from 1 in UK Core STU1 Sequence, to 0 in this release, as a result of the UK Core STU2 Sequence ballot reconciliation actions.
</div> 

---