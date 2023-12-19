## {{page-title}}

### Purpose
To know who additionally should be contacted with questions or clinical results and how they should be contacted.

### Notes
Mapped to an extension on the ServiceRequest, in review.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Additional contact - Full name|ServiceRequest.extension:additionalContact( PractitionerRole.practitioner( Practitioner.name ) )|Additional STF segment (STF-3), possibly referenced from the STF segment for the requester via STF-14|Additional contact's full name.|
|Additional contact - Job Title|ServiceRequest.extension:additionalContact( PractitionerRole.code )|STF-18|Additional contact's job title.|
|Additional contact - Current Specialty|ServiceRequest.extension:additionalContact( PractitionerRole.specialty )|PRA-5|Additional contact's current specialty.|
|Additional contact - Phone|ServiceRequest.extension:additionalContact( PractitionerRole.telecom:system=phone )|STF-10|Additional contact's phone number.|
|Additional contact - Email address|ServiceRequest.extension:additionalContact( PractitionerRole.telecom:system=email )|STF-15|Additional contact's email address.|
|Additional contact - Organization name, address and ODS code.|ServiceRequest.extension:additionalContact( PractitionerRole.organization( Organization.name ) )|STF-9.2|Additional contact's organization name.|
|Additional contact - Organization address.|ServiceRequest.extension:additionalContact( PractitionerRole.organization( Organization.address ) )|STF-11|Additional contact's organization address.|
|Additional contact - Organization ODS code.|ServiceRequest.extension:additionalContact(PractitionerRole.organization( Organization.identifier ) )|STF-9.1|Additional contact's organization ODS code.|
|Additional contact - Department name|ServiceRequest.extension:additionalContact(PractitionerRole.healthcareService( HealthcareService.name ) ), could alternatively use PractitionerRole.healthcareService.display to reduce resources in message|STF-8|Additional contact's department name.|
|Additional contact - Professional registration number|ServiceRequest.extension:additionalContact(PractitionerRole.practitioner( Practitioner.identifier ) )|STF-2.1|Additional contact's professional registration number such as their GMC number.|
|Additional contact - Professional registration number type|ServiceRequest.extension:additionalContact(PractitionerRole.practitioner( Practitioner.identifier.system ) )|STF-2.3|Additional contact's professional registration number type such GMC.|
|Additional contact - Genomic report delivery method|ServiceRequest.requester( PractitionerRole.telecom.rank=1 )|STF-16|Additional contact's report preferred delivery method.|
|Additional contact - Central email for address and reporting (many)|Additional ServiceRequest.extension:additionalContact( PractitionerRole.telecom:system=email ), may need to be additionally indicated in NEMS subscription|STF-15|Central email address provided by the additional contact.|

<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Additional contact - Full name|Optional|Optional|Optional|Optional|ServiceRequest.extension:additionalContact(PractitionerRole.practitioner(Practitioner.name))|Additional STF segment (STF-3), possibly referenced from the STF segment for the requester via STF-14|Additional contact's full name.|
|Additional contact - Phone |Optional|Optional|Optional|Optional|ServiceRequest.extension:additionalContact(PractitionerRole.telecom:system=phone)|STF-10|Additional contact's phone number.|
|Additional contact - Email address |Optional|Optional|Optional|Optional|ServiceRequest.extension:additionalContact(PractitionerRole.telecom:system=email)|STF-15|Additional contact's email address.|
|Additional contact - Hospital name, address and ODS code.|Optional|Optional|Optional|Optional|ServiceRequest.extension:additionalContact(PractitionerRole.organization(Organization.name)), ServiceRequest.extension:additionalContact(PractitionerRole.organization(Organization.address)), ServiceRequest.extension:additionalContact(PractitionerRole.organization(Organization.identifier))|STF-9.2, STF-11, STF-9.1|Additional contact's hospital name, address and ODS code.|
-->