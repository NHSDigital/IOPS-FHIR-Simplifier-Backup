## {{page-title}}

### Purpose
To know who to contact with questions or clinical results and how they should be contacted.

### Notes
Mapped to the requestor of the ServiceRequest. Usage of HealthcareService and Location resources still to be determined.

It is expected that practitioner and organization details will be referenced from PractitionerRole resources (e.g. using ODS/SDS identifiers) rather than be included as FHIR resources within Test Request payloads, though the full FHIR mapping has been provided below for completeness.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Requestor - Full name|ServiceRequest.requester( PractitionerRole.practitioner( Practitioner.name ) )|ORC-12|Requestor's full name.|
|Requestor - Job Title|ServiceRequest.requester( PractitionerRole.code )|STF-18|Requestor's job title.|
|Requestor - Current Specialty|ServiceRequest.requester( PractitionerRole.specialty )|PRA-5|Requestor's current specialty.|
|Requestor - Phone|ServiceRequest.requester( PractitionerRole.telecom:system=phone )|ORC-14|Requestor's phone number.|
|Requestor - Email address|ServiceRequest.requester( PractitionerRole.telecom:system=email )|STF-15|Requestor's email address.|
|Requestor - Organization name.|ServiceRequest.requester( PractitionerRole.organization( Organization.name ) )|ORC-21|Requestor's organization name.|
|Requestor - Organization address.|ServiceRequest.requester( PractitionerRole.organization( Organization.address ) )|ORC-22|Requestor's organization address.|
|Requestor - Organization ODS code.|ServiceRequest.requester( PractitionerRole.organization( Organization.identifier ) )|ORC-21.10|Requestor's organization ODS code.|
|Requestor - Department name|ServiceRequest.requester( PractitionerRole.healthcareService( HealthcareService.name ) ), could alternatively use PractitionerRole.healthcareService.display to reduce resources in message or PractitionerRole.specialty if mapped to clinical specialty **TBC**|STF-8|Requestor's department name.|
|Requestor - Professional registration number|ServiceRequest.requester( PractitionerRole.practitioner( Practitioner.identifier ) )|ORC-12.1|Requestor's professional registration number such as their GMC number.|
|Requestor - Professional registration number type|ServiceRequest.requester( PractitionerRole.practitioner( Practitioner.identifier.system ) )|ORC-12.9|Requestor's professional registration number type such GMC.|
|Requestor - Genomic report delivery method|ServiceRequest.requester( PractitionerRole.telecom.rank=1 )|STF-16|Requestors report preferred delivery method.|
|Requestor - Central email for address and reporting (many)|Additional ServiceRequest.requester( PractitionerRole.telecom:system=email ) optionally marked with extension:contactpoint-comment indicating reporting, may need to be additionally indicated in NEMS subscription **TBC**|STF-15|Central email address provided by the requestor.|

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
