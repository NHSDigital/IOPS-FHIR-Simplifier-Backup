## {{page-title}}

a) If done in one query then all medications would be returned, no date filter could be applied:

```json
{
  "resourceType":"Parameters",
  "parameter":[
    {
      "name":"patientNHSNumber",
      "valueIdentifier":{
        "system":"https://fhir.nhs.uk/Id/nhs-number",
        "value":"9999999999"
      }
    },
    {
      "name":"includeConsultations",
      "part":[
        {
          "name":"includeNumberOfMostRecent",
          "valuePositiveInt":3
        }
      ]
    },
    {
      "name":"includeProblems"
    },
    {
      "name":"includeAllergies",
      "part":[
        {
          "name":"includeResolvedAllergies",
          "valueBoolean":true
        }
      ]
    },
    {
      "name":"includeMedication"
    }
  ]
}
```

b) If done in two separate queries, the first would retrieve the last three consultations and problems and the second would retrieve allergies and medications for the last year:

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
    },
    {
      "name": "includeProblems"
    }
  ]
}
```

AND

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
          "valueDate": "2019-12-21"
        }
      ]
    }
  ]
}
```