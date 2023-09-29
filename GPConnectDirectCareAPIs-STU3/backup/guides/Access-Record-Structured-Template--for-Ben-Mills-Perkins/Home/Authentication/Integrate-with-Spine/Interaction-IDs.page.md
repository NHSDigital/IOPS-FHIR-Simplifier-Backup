## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: A list of GP Connect API interaction IDs
</div>


## GP Connect Interaction ID naming policy

All new interaction IDs follow the following format:

- ```urn:nhs:names:services:[programme]:[capability]:[standard]:[mechanism]:[operation]:[subject]```

Many of the existing interaction IDs follow the older format, which omits the [capability] delimeter:

- ```urn:nhs:names:services:[programme]:[standard]:[mechanism]:[operation]:[subject]```

Where the fields above are defined as:

- Programme = `gpconnect`
- Capability = [ `structured`, `documents` ]
- Standard = `fhir`
- Mechanism = [ `rest`, `operation` ]
	- `rest` for RESTful API interactions
	- `operation` for custom Operation API interactions
- Operation
	- RESTful style = [ `create`, `read`, `update`, `delete`, `search` ] + any more specific actions (for example, `cancel`)
	- Extended operation = [ `gpc.getcarerecord`, `gpc.registerpatient` ]
- Subject = [ `resourceType`, `operationName` ]
	- Resource Type is the name of a FHIR resource, such as `Patient`, `Appointment`, `Organization`
	- Operation Name is the name of a extended operation, such as `gpc.getcarerecord`

## List of Interaction IDs

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
TO DO - Links need to be updated below
</div>

### Foundations interactions

| Operation                 | Interaction ID            |
|---------------------------|---------------------------|
| [Read metadata](foundations_use_case_get_the_fhir_capability_statement.html) | `urn:nhs:names:services:gpconnect:fhir:rest:read:metadata-1` |
| [Read patient](foundations_use_case_read_a_patient.html) | `urn:nhs:names:services:gpconnect:fhir:rest:read:patient-1` |
| [Patient search](foundations_use_case_find_a_patient.html) | `urn:nhs:names:services:gpconnect:fhir:rest:search:patient-1` |
| [Read practitioner](foundations_use_case_read_a_practitioner.html) | `urn:nhs:names:services:gpconnect:fhir:rest:read:practitioner-1` |
| [Practitioner search](foundations_use_case_find_a_practitioner.html) | `urn:nhs:names:services:gpconnect:fhir:rest:search:practitioner-1` |
| [Read organisation](foundations_use_case_read_an_organisation.html) | `urn:nhs:names:services:gpconnect:fhir:rest:read:organization-1` |
| [Organisation search](foundations_use_case_find_an_organisation.html) | `urn:nhs:names:services:gpconnect:fhir:rest:search:organization-1` |
| [Read location](foundations_use_case_read_a_location.html) | `urn:nhs:names:services:gpconnect:fhir:rest:read:location-1` |
| [Register patient](foundations_use_case_register_a_patient.html)          | `urn:nhs:names:services:gpconnect:fhir:operation:gpc.registerpatient-1` |


---

### Access Record Structured interactions

| Operation                 | Interaction ID            |
|---------------------------|---------------------------|
| [Get Structured Record](accessrecord_structured_development_retrieve_patient_record.html) | `urn:nhs:names:services:gpconnect:fhir:operation:gpc.getstructuredrecord-1` |
| [Read metadata (Access Record Structured)](accessrecord_structured_get_the_fhir_capability_statement.html) | `urn:nhs:names:services:gpconnect:structured:fhir:rest:read:metadata-1` |

---

### Access Document interactions

| Operation                 | InteractionID             |
|---------------------------|---------------------------|
| [Read metadata (Access Document)](access_documents_use_case_get_the_fhir_capability_statement.html) | `urn:nhs:names:services:gpconnect:documents:fhir:rest:read:metadata-1` |
| [Patient search (Access Document)](access_documents_use_case_find_a_patient.html) | `urn:nhs:names:services:gpconnect:documents:fhir:rest:search:patient-1` |
| [Search for documents](access_documents_development_search_patient_documents.html) | `urn:nhs:names:services:gpconnect:documents:fhir:rest:search:documentreference-1` |
| [Retrieve document](access_documents_development_retrieve_patient_documents.html)   | `urn:nhs:names:services:gpconnect:documents:fhir:rest:read:binary-1` |

---

</br>