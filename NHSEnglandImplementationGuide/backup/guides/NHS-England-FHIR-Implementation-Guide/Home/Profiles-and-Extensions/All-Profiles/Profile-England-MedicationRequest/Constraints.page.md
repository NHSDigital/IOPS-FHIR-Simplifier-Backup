## Constraints (differential)

More information about the constraints on the <code>England-MedicationRequest</code> profile can be found below.

<table class="assets">
<tr>
<th width="15%">Key</th>
<th width="10%">Severity</th>
<th width="30%">Expression</th>
<th width="45%">Human Description</th>
</tr>
<tr>
<td>nhse-mer-001</td>
<td>error</td>
<td>(medicationReference.exists() and medicationCodeableConcept.exists().not()) or (medicationReference.exists().not() and medicationCodeableConcept.exists())</td>
<td>medication[x] - Only one of medicationReference or medicationCodeableConcept should be provided</td>
</tr>
<tr>
<td>nhse-mer-002</td>
<td>error</td>
<td>extension('https://fhir.nhs.uk/StructureDefinition/Extension-England-DMResponsiblePractitioner').exists().not() or (extension('https://fhir.nhs.uk/StructureDefinition/Extension-England-DMResponsiblePractitioner').value.reference.exists() or extension('https://fhir.nhs.uk/StructureDefinition/Extension-England-DMResponsiblePractitioner').value.system.exists())</td>
<td>Extension(responsiblePractitioner) - An identifier or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-mer-003</td>
<td>warning</td>
<td>(courseOfTherapyType.coding.code != 'continuous-repeat-dispensing') or ((courseOfTherapyType.coding.code = 'continuous-repeat-dispensing') and ((intent ='original-order') or (intent ='reflex-order')))</td>
<td>For continuous-repeat-dispensing intent must be reflex-order or original-order</td>
</tr>
<tr>
<td>nhse-mer-004</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code != 'continuous') or ((courseOfTherapyType.coding.code = 'continuous') and ((intent ='original-order') or (intent ='instance-order')))</td>
<td>For continuous intent must be instance-order or original-order</td>
</tr>
<tr>
<td>nhse-mer-005</td>
<td>warning</td>
<td>(courseOfTherapyType.coding.code.startsWith('acute')) or  (courseOfTherapyType.coding.code.startsWith('continuous') and dispenseRequest.exists() and dispenseRequest.numberOfRepeatsAllowed.exists())</td>
<td>dispenseRequest.numberOfRepeatsAllowed should be populated for continuous and continuous-repeat-dispensing MedicationRequests.</td>
</tr>
<tr>
<td>nhse-mer-006</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code = 'acute') or (courseOfTherapyType.coding.code = 'continuous') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent !='reflex-order') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent ='reflex-order' and dispenseRequest.exists() and basedOn.exists())</td>
<td>For continuous-repeat-dispensing (intent=reflex-order) basedOn must be populated</td>
</tr>
<tr>
<td>nhse-mer-007</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code = 'acute') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent !='reflex-order') or ((courseOfTherapyType.coding.code = 'continuous' or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent ='reflex-order')) and (dispenseRequest.numberOfRepeatsAllowed.exists().not() or (dispenseRequest.numberOfRepeatsAllowed.exists() and dispenseRequest.numberOfRepeatsAllowed = 0)))</td>
<td>For continuous-repeat-dispensing (intent=reflex-order) or continous orders, numberOfRepeatsAllowed must be empty or equal to 0</td>
</tr><tr>
<td>nhse-mer-008</td>
<td>warning</td>
<td>(courseOfTherapyType.coding.code = 'acute') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing') or (courseOfTherapyType.coding.code = 'continuous' and dispenseRequest.exists() and basedOn.exists())</td>
<td>For continuous issues basedOn should be populated</td>
</tr>
<tr>
<td>nhse-mer-009</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code != 'continuous-repeat-dispensing') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent='reflex-order') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent!='reflex-order' and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').exists().not()) or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent!='reflex-order' and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').exists() and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').extension('numberOfPrescriptionsIssued').exists().not())</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should not be present for continuous-repeat-dispensing that are not intent=reflex-order"</td>
</tr>
<tr>
<td>nhse-mer-010</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code != 'continuous-repeat-dispensing') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent != 'reflex-order') or (courseOfTherapyType.coding.code = 'continuous-repeat-dispensing' and intent='reflex-order' and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').exists() and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').extension('numberOfPrescriptionsIssued').exists())</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should be present for continuous-repeat-dispensing that have intent=reflex-order</td>
</tr>
<tr>
<td>nhse-mer-011</td>
<td>warning</td>
<td>(courseOfTherapyType.coding.code != 'continuous') or (courseOfTherapyType.coding.code = 'continuous' and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').exists() and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').extension('numberOfPrescriptionsIssued').exists())</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued is recommend to be present for continuous issues</td>
</tr>
<tr>
<td>nhse-mer-012</td>
<td>error</td>
<td>(courseOfTherapyType.coding.code != 'acute') or (courseOfTherapyType.coding.code = 'acute' and extension('https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation').exists().not())</td>
<td>Extension repeatInformation.numberOfPrescriptionsIssued should not be present for acute issues</td>
</tr>
<tr>
<td>nhse-mer-013</td>
<td>error</td>
<td>identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists().not() or (identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').exists()  and identifier.where(system='https://fhir.nhs.uk/Id/nhs-number').value.matches('^([0-9]{10})$'))</td>
<td>Length of the supplied NHS Number is wrong.</td>
</tr>
<tr>
<td>nhse-mer-014</td>
<td>error</td>
<td>(reference.exists() or (identifier.exists()))</td>
<td>requester - An identifier reference or resource reference must be provided</td>
</tr>
<tr>
<td>nhse-mer-015</td>
<td>error</td>
<td>(reference.exists() or (identifier.exists()))</td>
<td>recorder - An identifier reference or resource reference must be provided</td>
</tr>
</table>

---