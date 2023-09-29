## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This section should, in time, be superseded by the <a href="https://build.fhir.org/ig/HL7-UK/UK-Core-Access/index.html">UK Core Access API</a>.
</div>

An objective for publishing this implementation guidance is to establish a search interaction standard that can be adopted across all systems aligned to the FHIR UK Core standard.

When searching a clinical system, ICS or shared records system, the adoption of a common `GET` API syntax for search operations would allow the same software to access FHIR resources from any compliant system, by using a different base URL.

### GET by 'identifier', such as NHS Number

To query a FHIR server for a specific resources for a given patient;

```
GET [base]/{resource}?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|{NHS_Number}
```

Or if querying an NHS Scotland implemenmtation;

```
GET [base]/{resource}?patient:identifier=https://fhir.nhs.uk/Id/chi-number|{CHI_Number}
```

For example;

```
GET https://myfhirserver.net/MedicationRequest?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|123543254
```

See additional guidance for a [query for current medication](https://simplifier.net/guide/ukcoreimplementationguideformedicines/MedicationsDataUseCases#QueryforCurrentMedication).

---