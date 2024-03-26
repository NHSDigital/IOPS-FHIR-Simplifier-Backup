## {{page-title}}

```json
{
  "resourceType": "Parameters",
  "parameter": [
    {
      "name": "patientNHSNumber",
      "valueIdentifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    },
    {
      "name": "includeAllergies",
      "part": [
        {
          "name": "includeResolvedAllergies",
          "valueBoolean": true
        }
      ]
    },
    {
      "name": "includeMedication",
      "part": [
        {
          "name": "medicationSearchFromDate",
          "valueDate": "2019-02-21"
        }
      ]
    }
  ]
}
```