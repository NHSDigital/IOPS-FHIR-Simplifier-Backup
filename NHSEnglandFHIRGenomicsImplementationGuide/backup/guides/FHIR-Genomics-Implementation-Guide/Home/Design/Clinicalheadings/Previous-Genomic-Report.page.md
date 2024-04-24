## {{page-title}}

### Purpose
To locate previous genomic test reports linked to this service request.

### Notes
Mapped to DiagnosticReport.
It is expected previous genomic reports will be attached as PDF documents or references to their location will be provided within the genomic test order. Structured genomic reports will be investigated in future stages of the Genomic Medicine Service. 
Metadata regarding patient/performer details are expected to match previous mappings for these headings above.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Previous genomic report - Report referral summary|DiagnosticReport.conclusion|OBX-5|Referring clinician's summary of the previous genomic report to support test request.|
|Previous genomic report - Report file/link|DiagnosticReport.presentedForm|OBX-5 where OBX-2=ED or RP|A copy of/or link to the previous genomic report.|
|Previous genomic report - Test performed date|DiagnosticReport.effectiveDateTime|OBX-19|The date a previous genomic test was performed.|
|Previous genomic report - Report identifier|DiagnosticReport.identifier|OBX-3|The identifier for the previous genomic report.|
|Previous genomic report - Patient's first name|DiagnosticReport.subject( Patient.name.given )|PID-5.2 attached to OBR|The first name of the patient on the previous genomic report.|
|Previous genomic report - Patient's surname|DiagnosticReport.subject( Patient.name.family )|PID-5.1 attached to OBR|The surname of the patient on the previous genomic report.|
|Previous genomic report - Patient's address|DiagnosticReport.subject( Patient.address )|PID-11 attached to OBR|The address of the patient on the previous genomic report.|
|Previous genomic report - Patient's post code|DiagnosticReport.subject( Patient.address.postalCode )|PID-11.5 attached to OBR|The postcode of the patient on the previous genomic report.|
|Previous genomic report - Patient's country|DiagnosticReport.subject( Patient.address.country )|PID-11.6 attached to OBR|The country of the patient on the previous genomic report.|
|Previous genomic report - Patient's date of birth|DiagnosticReport.subject( Patient.birthDate )|PID-7 attached to OBR|The date of birth of the patient on the previous genomic report.|
|Previous genomic report - Patient's NHS number|DiagnosticReport.subject( Patient.identifier:system = https://fhir.nhs.uk/Id/nhs-number )|PID-3 where PID-3.5=2.16.840.1.113883.2.1.3.2.4.18.23|The NHS number of the patient on the previous genomic report.|
|Previous genomic report - Patient's alternative identifier|DiagnosticReport.subject( Patient.identifier:system != https://fhir.nhs.uk/Id/nhs-number )|PID-3 where PID-3.5 != 2.16.840.1.113883.2.1.3.2.4.18.23|The alternative identifier of the patient on the previous genomic report.|
|Previous genomic report - Patient's relationship to requesting patient|DiagnosticReport.subject( Patient.link( RelatedPerson.relationship ) )|NK1-3|The relationship of the patient on the previous genomic report to the requesting patient.|
|Previous genomic report - Patient's clinical genetics number|DiagnosticReport.subject( Patient.identifier:system = **TBC** )|PID-3|The individual clinical genetic number of the patient on the previous genomic report.|
|Previous genomic report - Patient's pedigree number|DiagnosticReport.subject( Patient.identifier:system = https://fhir.nhs.uk/Id/genomics-pedigree-number )|PID-3, system **TBC**|The pedigree number of the patient on the previous genomic report which links their family.|
|Previous genomic report - Report lab test number|DiagnosticReport.basedOn( ServiceRequest.identifier )|ORC-2|The lab test number from the previous genomic report.|
|Previous genomic report - Report of genetic analysis|DiagnosticReport.conclusionCode|OBR-5|The clinical outcomes from the previous genomic report.|
|Previous genomic report - Report performer full name|DiagnosticReport.performer( PractitionerRole.practitioner.display )|OBX-16|The full name of the individual that authored the previous genomic test report.|
|Previous genomic report - Report performer organisation ODS code|DiagnosticReport.performer( PractitionerRole.organization.identifier )|OBX-23.10|The organisation ODS code of the individual that authored the previous genomic test report.|
|Previous genomic report - Original requester full name|DiagnosticReport.basedOn( ServiceRequest.requester( PractitionerRole.practitioner.display ) )|ORC-12|The full name of the individual that requested the previous genomic test report.|
|Previous genomic report - Original requester organisation ODS code|DiagnosticReport.basedOn( ServiceRequest.requester( PractitionerRole.organization.identifier ) )|ORC-21.10|The organisation ODS code of the individual that requested the previous genomic test report.|
|Previous genomic report - Original requester reason for request|DiagnosticReport.basedOn( ServiceRequest.reasonCode )|ORC-16|The reason for requesting the previous genomic test report.|

