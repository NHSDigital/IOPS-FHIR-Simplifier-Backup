### MedicationRequest.courseOfTherapyType

This element was introduced in HL7 FHIR R4 and in the NHS Digital Medicines this replaces the following extensions:

| FHIR Version | Extension |
|--
| CareConnect (GP Connect) STU3 |`https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1` |
| CareConnect STU3 | `https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-PrescriptionType-1` |
| UKCore R4 | `https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PrescriptionType` |

These extensions use CodeSystems

- `https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1`
- `https://fhir.hl7.org.uk/CodeSystem/UKCore-PrescriptionType`

These are not supported in NHS Digital Medicines and the codes must be mapped to codes from 
- `http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy` 
- `https://fhir.nhs.uk/CodeSystem/medicationrequest-course-of-therapy`

The mapping is described in a FHIR ConceptMap {{pagelink: MedicationRequest-course-therapy-type-map.md}}, which is summarised below:

| Source Code | Source CodeSystem | Destination Code | Destination CodeSystem ||
|--
| **acute** (Acute)	| `https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1`<br><br> `https://fhir.hl7.org.uk/CodeSystem/UKCore-PrescriptionType` |	**acute** (Short course (acute) therapy) | `http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy`  |
| **repeat** (Repeat)	| `https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1`<br><br> `https://fhir.hl7.org.uk/CodeSystem/UKCore-PrescriptionType` |	**continuous** (Continuous long term therapy) | `http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy`  | 
| **repeat-dispensing** (Repeat Dispensing) | `https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1`<br><br> `https://fhir.hl7.org.uk/CodeSystem/UKCore-PrescriptionType`	|	**continuous-repeat-dispensing** (Continuous long term (repeat dispensing)) | `https://fhir.nhs.uk/CodeSystem/medicationrequest-course-of-therapy` |







