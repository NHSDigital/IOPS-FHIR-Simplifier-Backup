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
      "name": "includeConsultations",
      "part": [
        {
          "name": "includeNumberOfMostRecent",
          "valuePositiveInt": 3
        }
      ]
    }
  ]
}
```