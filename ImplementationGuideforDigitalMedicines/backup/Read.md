## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This section should, in time, be superseded by the <a href="https://build.fhir.org/ig/HL7-UK/UK-Core-Access/index.html">UK Core Access API</a>.
</div>

The adoption of a common `GET` API syntax to read a specific resource from a FHIR server would allow the same software to, for example, read a FHIR resource from a GP system or read a FHIR resource from shared records service. The query syntax can be the same, using a different base URL technical end-point.

### GET by 'id'

To query a FHIR server for a specific resources where the `id` is a nationally understood unique identifier;

```
GET [base]/{resource}/{id}
```

Examples;

Where X26 is the ODS code as per the [NHS Digital FHIR ODS API](https://digital.nhs.uk/developer/api-catalogue/organisation-data-service-fhir).

```
GET https://myfhirserver.net/Organization/X26
```

Where 9000000009 is a valid NHS Number as per the [NHS Digital FHIR PDS API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir#api-Default-getPatient).

```
GET https://myfhirserver.net/Patient/9000000009
```

### GET by 'identifier'

To query a FHIR server for a specific resource by `identifier`;

```
GET [base]/{resource}?identifier={value}
```

For example;

```
GET https://myfhirserver.net/MedicationRequest?identifier=a54219b8-f741-4c47-b662-e4f8dfa49ab6
```

---
