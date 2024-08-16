## {{page-title}}
  
The API endpoints for the Genomic Medicine Service have been defined in {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}}, but these are largely dependent on Architecture Decisions following First of Type/alpha development. This page will be updated once the API design has been has been finalised to describe how the API should be used.

This page will also link out to the OpenAPI specification once this is available.

## Validation
The test order service will validate the resources created on the service against the base FHIR resource profiles, no business or genomic profile validation will be implemented. Business and code validation will be included in the national portal and validation is expected in the connecting systems which will be creating data on the service.

Business logic validation and validation of codes such as  SNOMED and test codes could be added to the validation within the test order service if data quality is a concern.

## Duplicate Resources
In a [FHIR transaction interaction](https://hl7.org/fhir/R4B/http.html#transaction) there is a “Bundle.entry.request” condition which can be added, such as “ifNoneExist” or “ifNoneMatch”, that allow the requester to specify some parameters as to how to perform the operation, but from a service perspective, in order to minimise storage volume and cost, the service will attempt to de-duplicate resources based on key identifiers, such as NHS Number for patients and ODS code for organisations. A simple check of length can be performed to validate if there is less information in the latest resource compared to the one stored.

Each resource could be checked for a set of fields which would act as a unique key, in order to reduce the chance of duplicates. The same fields could be used to decide if the new version of a resource should replace or be used to enrich the stored data, but this strategy carries risk that similar resources might be overwritten or ignored if the key fields are the same but additional fields are included with pertinent information, therefore the validation will be simplified to reduce duplication but at the same time reduce risk of missing important information. Reducing the validation will also improve performance compared to complex and extensive duplicate checking of each resource.

The following resources will be unique for each service request as they link to the service request, therefore when created they will always be stored without duplicate checks being performed:
- Condition
- Consent
- DiagnosticReport
- FamilyMemberHistory
- Observation
- Procedure
- Provenance
- QuestionnaireResponse
- ResearchSubject
- ServiceRequest
- Specimen
- Subscription
- Task

The following resources are likely to be shared across different service requests so should be validated to minimise duplication. The suppliers are expected to use consistent identifiers for this data which is not unique to the service request but will be representing consistent data across multiple service requests:
- Patient (compared though Identifier e.g. NHS Number/ Hospital ID)
- PractitionerRole (compared through SDS user ID and ODS code Identifiers)
- RelatedPerson (compared though links to patient resources and identifiers)

As these resources will be referenced from other resources, there is a risk that they might become orphaned if the referencing resource is updated to no longer reference the resource. The number of expected orphaned resources should be low as all of these resources will be used across multiple
test requests.

## API Versioning
The current specification aligns to the UK Core FHIR R4 standard, but in future uplifted versions or new standards may be introduced.

### Minor Changes
For minor updates to the UK Core FHIR R4 standard the changes should be non-breaking and the service and existing APIs will be updated to include the changes. As the changes are non breaking there should be no effect on the service or integration with existing suppliers.

### Major Changes
For more significant changes such as a standard or a new major version of the FHIR specification which contains breaking changes, each resource will be assessed to determine the significance of the change and plan accordingly.

The service will most likely need to support both the existing version and new version with a migration plan and a plan to deprecate the old API version.

Some internal transformation between versions may be possible and desirable, as long as transformation introduces no additional clinical risk. Transformation is desirable when there are significant benefits from decoupling supplier migration, with the aim of preventing loss of access to old or new data during the migration process and to reduce complexity and cost on the supplier development side, which filters back to the purchasing NHS services and commissioners.

## API Performance

Details regarding API performance, e.g. maximum transactions per second or storage scalability are defined within an external Non-Functional Requirements document so will not be repeated within this IG.

## Data Retention Policy

Retention of transactional data will follow government guidance regarding data retention of sensitive information. Long-term storage of patient Genomic information is expected to be covered within the Unified Genomic Record.