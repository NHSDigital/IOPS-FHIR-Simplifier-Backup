## `subject`

A reference to the patient.

Within a FHIR Messaging or FHIR Document implementation, include a **UKCore-Patient** resource within the Bundle with at least the minimum dataset populated as defined within the UK Core standard. The `reference` points to the resource in the Bundle.

JSON
``` json
// within the MedicationStatement resource...

  "subject": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith"
  }

// elsewhere in the Bundle...

  {
    "fullUrl": "urn:patient-011223344",
    "resource": {
      "resourceType": "Patient",
      "id": "urn:patient-011223344",
      "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9912003888"
      },
      "name": {
        "use": "official",
        "text": "Mr Richard Smith",
        "family": "Smith",
        "given": "Richard",
        "prefix": "Mr"
      },
      "gender": "male",
      "birthDate": "1956-02-04"
    }
  }
```

Within a RESTful implemementation a `reference` and/or `identifier` **MUST** be provided that allows the consumer system to query another API if they need to access the complete **UKCore-Patient** resource. The `reference` points to the resource in the Bundle.

For implementations within England and Wales, the `identifier` could be the patient's **NHS Number**, allowing consumer system to use the [NHS Digital Personal Demographics Service FHIR API](https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir) return a Patient resource.

JSON
``` json
{
  "subject": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith",
    "identifier": {
      "system": "https://fhir.nhs.uk/Id/nhs-number",
      "value": "9912003888"
    }
  }
}
```

For implementations within Scotland, the `identifier` could be the patient's **CHI Number**.

JSON
``` json
{
  "subject": {
    "reference": "urn:patient-011223344",
    "display": "Richard Smith",
    "identifier": {
      "system": "https://fhir.nhs.uk/Id/nhs-number",
      "value": "9912003888"
    }
  }
}
```

---