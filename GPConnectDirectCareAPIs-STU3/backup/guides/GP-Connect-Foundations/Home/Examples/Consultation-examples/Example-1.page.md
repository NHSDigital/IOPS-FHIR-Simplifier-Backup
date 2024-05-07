## {{page-title}}

### Request

Example of a call to return the following items from a patient's structured record:

- Consultations

#### Request payload

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

### Response

#### Response payload

The response payload is available as a `JSON` file by clicking on the link below. The consultation is in line with the diagram on the consultation guidance page {{pagelink:Home/Design/Consultations-guidance}}.

[Consultation response - Example 1](https://simplifier.net/gpconnect2/consultations_response1/$download?format=json)