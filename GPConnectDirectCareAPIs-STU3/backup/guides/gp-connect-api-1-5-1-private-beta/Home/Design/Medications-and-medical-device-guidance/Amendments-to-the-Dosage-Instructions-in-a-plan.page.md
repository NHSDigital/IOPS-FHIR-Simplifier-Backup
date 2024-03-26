## {{page-title}}

Where the dosage instructions of a medication/medical device plan is amended the existing authorisation/plan <strong>MUST</strong> be stopped or discontinued and a new authorisation created.

When splitting the plan due to a change in dosage the original authorisation should retain the repeat information as it was at the instant before the dosage changed. The new authorisation should contain the number of authorised issues remaining from the original plan and the number of issues at the new dosage. The new plan should reference the origianl plan using the <code class="highlighter-rouge">priorPrescription</code> element.

For example,

Consider the case where Furosemide 20mg tablets had been authorised as a repeat with 6 authorised issues with a dosage of ‘twice daily as advised’, 1 issue was made at this dosage and then the dosage was changed to ‘One to be taken each morning’. The <code class="highlighter-rouge">authoredOn</code> and <code class="highlighter-rouge">validityPeriod.start</code> dates should be retained from the original authorisation.

The original plan would contain,

|element|value|
|---|---|
|MedicationRequest.id|E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1|
|MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsAllowed)|6|
|MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsIssued)|1|
|MedicationRequest.dosageIntruction.text|‘twice daily as advised’|
|authoredOn|2020-12-21T10:59:37.493+00:00|
|validityPeriod.start|2020-12-21|

<p>and the new plan would contain,</p>

|element|value|
|---|---|
|MedicationRequest.id|E9881EF6-EF3A-4556-9202-A437C5E31128|
|MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsAllowed)|5|
|MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsIssued)|0|
|MedicationRequest.dosageIntruction.text|‘One to be taken each morning’|
|MedicationRequest.priorPrescription|E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1|
|authoredOn|2020-12-21T10:59:37.493+00:00|
|validityPeriod.start|2020-12-21|

The populated resources for this example are shown below:


```json
{
  "resourceType": "Bundle",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1"
    ]
  },
  "type": "collection",
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1",
            "extension": [
              {
                "url": "numberOfRepeatPrescriptionsAllowed",
                "valueUnsignedInt": 6
              },
              {
                "url": "numberOfRepeatPrescriptionsIssued",
                "valueUnsignedInt": 1
              }
            ]
          },
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1",
                  "code": "repeat",
                  "display": "Repeat"
                }
              ]
            }
          }
        ],
        "identifier": [
          {
            "system": "https://EMISWeb/A82038",
            "value": "E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"
          }
        ],
        "groupIdentifier": {
          "value": "e9881ef6-ef3a-4556-9202-a437c5e31128-hd-1"
        },
        "status": "completed",
        "intent": "plan",
        "medicationReference": {
          "reference": "Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"
        },
        "subject": {
          "reference": "Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"
        },
        "authoredOn": "2020-12-21T10:57:18.563+00:00",
        "recorder": {
          "reference": "Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"
        },
        "dosageInstruction": [
          {
            "text": "Twice daily as advised"
          }
        ],
        "dispenseRequest": {
          "validityPeriod": {
            "start": "2020-12-21",
            "end": "2020-12-21"
          },
          "quantity": {
            "value": 28,
            "unit": "tablet"
          },
          "expectedSupplyDuration": {
            "value": 28,
            "unit": "day",
            "system": "http://unitsofmeasure.org",
            "code": "d"
          }
        }
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "A002B1FE-2184-4F8D-BD02-C74A813125F2",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1",
                  "code": "repeat",
                  "display": "Repeat"
                }
              ]
            }
          }
        ],
        "identifier": [
          {
            "system": "https://EMISWeb/A82038",
            "value": "A002B1FE-2184-4F8D-BD02-C74A813125F2"
          }
        ],
        "basedOn": [
          {
            "reference": "MedicationRequest/E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"
          }
        ],
        "groupIdentifier": {
          "value": "e9881ef6-ef3a-4556-9202-a437c5e31128-hd-1"
        },
        "status": "completed",
        "intent": "order",
        "medicationReference": {
          "reference": "Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"
        },
        "subject": {
          "reference": "Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"
        },
        "authoredOn": "2020-12-21T10:59:37.493+00:00",
        "recorder": {
          "reference": "Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"
        },
        "dosageInstruction": [
          {
            "text": "Twice daily as advised"
          }
        ],
        "dispenseRequest": {
          "validityPeriod": {
            "start": "2020-12-21",
            "end": "2021-01-18"
          },
          "quantity": {
            "value": 28,
            "unit": "tablet"
          },
          "expectedSupplyDuration": {
            "value": 28,
            "unit": "day",
            "system": "http://unitsofmeasure.org",
            "code": "d"
          }
        }
      }
    },
    {
      "resource": {
        "resourceType": "MedicationRequest",
        "id": "E9881EF6-EF3A-4556-9202-A437C5E31128",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"
          ]
        },
        "extension": [
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1",
            "extension": [
              {
                "url": "numberOfRepeatPrescriptionsAllowed",
                "valueUnsignedInt": 5
              },
              {
                "url": "numberOfRepeatPrescriptionsIssued",
                "valueUnsignedInt": 0
              }
            ]
          },
          {
            "url": "https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1",
            "valueCodeableConcept": {
              "coding": [
                {
                  "system": "https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1",
                  "code": "repeat",
                  "display": "Repeat"
                }
              ]
            }
          }
        ],
        "identifier": [
          {
            "system": "https://EMISWeb/A82038",
            "value": "E9881EF6-EF3A-4556-9202-A437C5E31128"
          }
        ],
        "groupIdentifier": {
          "value": "e9881ef6-ef3a-4556-9202-a437c5e31128"
        },
        "status": "active",
        "intent": "plan",
        "medicationReference": {
          "reference": "Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"
        },
        "subject": {
          "reference": "Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"
        },
        "authoredOn": "2020-12-21T10:59:37.493+00:00",
        "recorder": {
          "reference": "Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"
        },
        "dosageInstruction": [
          {
            "text": "One To Be Taken Each Morning"
          }
        ],
        "dispenseRequest": {
          "validityPeriod": {
            "start": "2020-12-21"
          },
          "quantity": {
            "value": 28,
            "unit": "tablet"
          },
          "expectedSupplyDuration": {
            "value": 28,
            "unit": "day",
            "system": "http://unitsofmeasure.org",
            "code": "d"
          }
        },
        "priorPrescription": {
          "reference": "MedicationRequest/E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"
        }
      }
    },
    {
      "resource": {
        "resourceType": "Medication",
        "id": "F87D9962-6D02-41C7-85C7-735214FA6FC5",
        "meta": {
          "profile": [
            "https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"
          ]
        },
        "code": {
          "coding": [
            {
              "system": "https://fhir.hl7.org.uk/Id/emis-drug-codes",
              "code": "FUTA17675NEMIS",
              "display": "Furosemide 20mg tablets",
              "userSelected": true
            },
            {
              "system": "http://snomed.info/sct",
              "code": "317971007",
              "display": "Furosemide 20mg tablets"
            }
          ]
        }
      }
    }
  ]
}
```