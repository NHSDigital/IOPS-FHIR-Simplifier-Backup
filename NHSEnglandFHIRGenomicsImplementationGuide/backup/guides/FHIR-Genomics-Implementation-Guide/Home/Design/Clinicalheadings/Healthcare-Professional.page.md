## {{page-title}}

### Purpose
To record details regarding a HCP that is associated with a test order. 
To know who to contact with questions or clinical results and how they should be contacted.

### Notes
Mapped to PractitionerRole. The requestor is mapped to ServiceRequest.requestor. Usage of HealthcareService and Location resources still to be determined.

It is expected that practitioner and organization details will be referenced from PractitionerRole resources (e.g. using ODS/SDS identifiers) rather than be included as FHIR resources within Test Request payloads, though the full FHIR mapping has been provided below for completeness.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|HCP - Genomic test order role|Determined through where the PractitionerRole is referenced from e.g. for the requester: ServiceRequest.requestor, Additional contact: ServiceRequest.extension:additionalContact, Sample collection: Specimen.collection.collector etc.|multiple possible segments e.g. ORC-12 for requester|HCP's function within the genomic test ordering process.|
|HCP - Full name|PractitionerRole.practitioner.display (full delimited name can be retrieved via identifier e.g. from SDS)|ORC-12|HCP's full name.|
|HCP - Job Title|PractitionerRole.code (display can be used to capture human readable job role code)|STF-18|HCP's job title.|
|HCP - Current Specialty|PractitionerRole.specialty|PRA-5|HCP's current specialty.|
|HCP - Phone|PractitionerRole.telecom:system=phone|ORC-14|HCP's phone number.|
|HCP - Email address|PractitionerRole.telecom:system=email|STF-15|HCP's email address.|
|HCP - Organization name.|PractitionerRole.organization.display (full delimited name can be retrieved via identifier e.g. from ODS)|ORC-21|HCP's organization name.|
|HCP - Organization address.|PractitionerRole.organization (retrieved via ODS)|ORC-22|HCP's organization address.|
|HCP - Organization ODS code.|PractitionerRole.organization.identifier|ORC-21.10|HCP's organization ODS code.|
|HCP - Department name|PractitionerRole.healthcareService.identifier, could alternatively use PractitionerRole.healthcareService.display to record human readable version or PractitionerRole.specialty if mapped to clinical specialty **TBC**|STF-8|HCP's department name.|
|HCP - Professional registration number|PractitionerRole.practitioner.identifier|ORC-12.1|HCP's professional registration number such as their GMC number.|
|HCP - Professional registration number type|PractitionerRole.practitioner.identifier.system|ORC-12.9|HCP's professional registration number type such GMC.|
|HCP - Genomic report delivery method|PractitionerRole.telecom.rank=1|STF-16|HCP report preferred delivery method.|
|HCP - Central email for address and reporting (many)|Additional  PractitionerRole.telecom:system=email marked with extension:contactpoint-comment indicating reporting, may need to be additionally indicated in NEMS subscription depending on notification method used **TBC**|STF-15|Central email address provided by the HCP.|

<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Requestor - Full name|Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.practitioner(Practitioner.name))|ORC-12|Requestor's full name.|
|Requestor - Job Title|N/A|N/A|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.code)|ORC-12.1|Requestor's GMC number.|
|Requestor - Professional registration number|N/A|N/A|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.practitioner(Practitioner.identifier))|ORC-12.1|Requestor's GMC number.|
|Requestor - Phone |Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.telecom:system=phone)|ORC-14|Requestor's phone number.|
|Requestor - Email address |Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.telecom:system=email)|STF-15|Requestor's email address.|
|Requestor - Hospital name, address and ODS code.|Mandatory|Mandatory|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.organization(Organization.name)), ServiceRequest.requester(PractitionerRole.organization(Organization.address)), ServiceRequest.requester(PractitionerRole.organization(Organization.identifier))|ORC-21,ORC-22,ORC-21.10|Requestor's hospital name, address and ODS code.|
|Requestor - Department name|N/A|N/A|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.healthcareService(HealthcareService.name))|STF-8|Requestor's department name.|
|Requestor - Department address|N/A|N/A|Mandatory|Mandatory|ServiceRequest.requester(PractitionerRole.healthcareService(HealthcareService.location(Location.address)))|ORC-24|Requestor's department address.|
-->
