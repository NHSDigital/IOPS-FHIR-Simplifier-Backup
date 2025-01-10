## {{page-title}}

The way the API is designed to conform with FHIR standards means the prescription reissue request and the prescription itself are two separate objects. The prescription reissue request is referenced using a FHIR R4 `Task` Resource and the prescription itself is a FHIR R4 MedicationRequest.

The two are linked using the `focus` element on the `Task` resource where it references a specific `MedicationRequest` that has `intent` set to `plan`, i.e. this request (Task) is for a new issue of this prescription (MedicationRequest).

The first and most reliable option is to resolve this reference from the `MedicationRequest` endpoint itself to get more information. 

In order to reduce API calls and ease integration with the API the consumer has two options.

The simplest option is to utilise the display text under the reference to obtain a short summary about the MedicationRequest.

###### Example:
```json
        "focus": {
          "reference": "MedicationRequest/a0531933-0673-45d4-bcb9-80acfd8a9fc7",
          "display": "Repeat prescription for Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
        }
```

Should the consumer require further information, i.e. dosage information or expiration date and doesn't wish to use multiple API calls, there is a further option to utilise the [`_include`](https://www.hl7.org/fhir/search.html#_include) parameter.

The `_include` parameter can be used to follow links to referenced resources, in this use case, it will be used to retrieve the referenced `MedicationRequest`s. 

This means in the response searchset bundle it will also include the referenced `MedicationRequest`s. The supplier can then use the extra detail in the `MedicationRequest`s to display to the user. 

###### Example
```json
{
  "resourceType": "Bundle",
  "id": "a96bb563-c86b-4021-903e-5917b927c386",
  "identifier": {
    "system": "https://tools.ietf.org/html/rfc4122",
    "value": "a3294018-6c63-4556-8797-f782d1c95480"
  },
  "type": "searchset",
  "entry": [
    {
      "fullUrl": "20885a31-acf0-42d5-bd5b-85c23f7a32fd",
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "06c7d0e2-1022-4e47-ac55-f6463d701a4f",
        "meta": {
          "profile": [
            "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation",
            "extension": [
              {
                "url": "numberOfPrescriptionsIssued",
                "valueUnsignedInt": 1
              },
              {
                "url": "authorisationExpiryDate",
                "valueDateTime": "2023-09-10T19:00:00.000Z"
              }
            ]
          }
        ],
        "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
            "value": "4857b9d3-b714-44b9-9e67-3df67275b785"
          }
        ],
        "status": "active",
        "intent": "plan",
        "category": [
          {
            "coding": [
              {
                "system": "http://terminology.hl7.or/CodeSystem/medicationrequest-category",
                "code": "community",
                "display": "Community"
              }
            ]
          }
        ],
        "medicationCodeableConcept": {
          "coding": [
            {
              "system": "https://dmd.nhs.uk",
              "code": "3113111000001106",
              "display": "Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
            }
          ]
        },
        "subject": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        },
        "requester": {
          "reference": "PractitionerRole/ed313d93-f470-420f-ae4e-2b7eb91d3f45",
          "display": "Dr Jane Smith"
        },
        "groupIdentifier": {
          "system": "https://fhir.nhs.uk/Id/prescription-order-number",
          "value": "PDI12E-Y765908-4FF3LQ"
        },
        "courseOfTherapyType": {
          "coding": [
            {
              "system": "http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy",
              "code": "continuous",
              "display": "Continuous long term therapy"
            }
          ]
        },
        "authoredOn": "2022-10-13T16:20:27+07:00",
        "substitution": {
          "allowedBoolean": false
        },
        "dosageInstruction": [
          {
            "text": "One to two puffs to be inhaled as needed",
            "method": {
              "coding": [
                {
                  "system": "http://snomed.info/sct",
                  "code": "420652005",
                  "display": "Until gone"
                }
              ]
            }
          }
        ]
      }
    },
    {
      "fullUrl": "20885a31-acf0-42d5-bd5b-85c23f7a32fd",
      "resource": {
        "resourceType": "Task",
        "id": "aef77afb-7e3c-427a-8657-2c427f71a271",
        "meta": {
          "profile": [
            "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task"
          ]
        },
        "identifier": [
          {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "725ca1bd-2860-4476-8802-8d035d802e7f"
          }
        ],
        "status": "requested",
        "intent": "order",
        "focus": {
          "reference": "MedicationRequest/06c7d0e2-1022-4e47-ac55-f6463d701a4f",
          "display": "Repeat prescription for Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
        },
        "for": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        },
        "authoredOn": "2022-11-23T20:20:27+07:00",
        "lastModified": "2022-11-23T20:20:27+07:00",
        "requester": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        },
        "note": [
          {
            "authorString": "Patient",
            "text": "Ran out of previous prescription"
          }
        ]
      }
    },
    {
      "fullUrl": "15c5ee13-73cf-45f8-a1f1-a7de3e10dae6",
      "resource": {
        "resourceType": "Task",
        "id": "fjugkd8281-4tngn-j4fn-8657-2knrkfjrgu",
        "meta": {
          "profile": [
            "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task"
          ]
        },
        "identifier": [
          {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "725ca1bd-2860-4476-8802-8d035d802e7f"
          }
        ],
        "status": "rejected",
        "statusReason": {
          "text": "No longer suitable, please contact GP to organise an appointment"
        },
        "intent": "order",
        "focus": {
          "reference": "MedicationRequest/06c7d0e2-1022-4e47-ac55-f6463d701a4f"
        },
        "for": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        },
        "authoredOn": "2022-08-14T07:20:23+07:00",
        "lastModified": "2022-08-14T11:40:47+07:00",
        "requester": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        }
      }
    },
    {
      "fullUrl": "561d0bfa-a937-4d91-81ab-abe65bca2d95",
      "resource": {
        "resourceType": "Task",
        "id": "84722efb-95b0-4769-921a-eda53382b320",
        "meta": {
          "profile": [
            "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task"
          ]
        },
        "identifier": [
          {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "2270b136-7a4c-491e-8bf1-624b5c4f20b7"
          }
        ],
        "status": "in-progress",
        "intent": "order",
        "focus": {
          "reference": "MedicationRequest/06c7d0e2-1022-4e47-ac55-f6463d701a4f",
          "display": "Repeat prescription for Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
        },
        "for": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        },
        "authoredOn": "2022-10-13T16:20:27+07:00",
        "lastModified": "2022-10-15T11:28:13+07:00",
        "requester": {
          "reference": "Patient/9000000009",
          "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9000000009"
          },
          "display": "Jane Smith"
        }
      }
    }
  ]
}
```