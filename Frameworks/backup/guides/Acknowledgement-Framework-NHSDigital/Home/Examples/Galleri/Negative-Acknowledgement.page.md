## {{page-title}}

### Negative Acknowledgement of Test Result - Incorrect Data Format

The test result from GRAIL (UK) should be in a JSON format. However, the test result sent to NHS England (GPS) was sent in an XML format. So a negative acknowledgement is sent to GRAIL (UK).

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send bio-sampling test report
nhsenglandgps --> grailuk: Send negative acknowledgement
</plantuml>

<br /><br />
#### Message 1 - Send bio-sampling test report
TO BE ADDED - MUST BE IN XML FORMAT

<br /><br />
#### Message 2 - Send negative acknowledgement
```json
{
  "resourceType": "Bundle",
  "type": "message",
  "entry": [
    {
      "fullUrl": "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader",
      "resource": {
        "resourceType": "MessageHeader",
        "eventCoding": {
          "system": "https://fhir.nhs.uk/CodeSystem/message-event",
          "code": "notification",
          "display": "Event Notification"
        },
        "destination": [
          {
            "name": "GRAIL (UK)",
            "endpoint": "https://uk.grail.com/api",
            "receiver": {
              "reference": "urn:uuid:ff09cccc-2c9b-4238-91d2-66fa6ee845c3",
              "display": "GRAIL (UK)"
            }
          }
        ],
        "source": {
          "name": "NHS England",
          "version": "0.0.5",
          "contact": {
            "system": "email",
            "value": "helpdesk@england.nhs.net"
          },
          "endpoint": "https://gps.digital.nhs.uk/api"
        },
        "response": {
          "identifier": "6f4256fa-cd14-4f96-899e-008643d84ff8",
          "code": "fatal-error",
          "details": {
            "reference": "urn:uuid:e747c4e4-9228-4ba4-b3e0-6e34b928edac"
          }
        }
      }
    },
    {
      "fullUrl": "https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome",
      "resource": {
        "resourceType": "OperationOutcome",
        "issue": [
          {
            "severity": "fatal",
            "code": "structure",
            "diagnostics": "Unable to parse XML content."
          }
        ]
      }
    }
  ]
}
```

<br /><br />
### Negative Acknowledgement of Test Result - Missing Mandatory Element 

The test result from GRAIL (UK) should include all FHIR elements that are mandatory (with a minimum cardinality of 1). However, the test result sent to NHS England (GPS) is missing a FHIR element that is mandatory. So a negative acknowledgement is sent to GRAIL (UK).

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send bio-sampling test report
nhsenglandgps --> grailuk: Send negative acknowledgement
</plantuml>

<br /><br />
#### Message 1 - Send bio-sampling test report
TO BE ADDED

<br /><br />
#### Message 2 - Send negative acknowledgement
```json
{
  "resourceType": "Bundle",
  "type": "message",
  "entry": [
    {
      "fullUrl": "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader",
      "resource": {
        "resourceType": "MessageHeader",
        "eventCoding": {
          "system": "https://fhir.nhs.uk/CodeSystem/message-event",
          "code": "notification",
          "display": "Event Notification"
        },
        "destination": [
          {
            "name": "GRAIL (UK)",
            "endpoint": "https://uk.grail.com/api",
            "receiver": {
              "reference": "urn:uuid:ff09cccc-2c9b-4238-91d2-66fa6ee845c3",
              "display": "GRAIL (UK)"
            }
          }
        ],
        "source": {
          "name": "NHS England",
          "version": "0.0.5",
          "contact": {
            "system": "email",
            "value": "helpdesk@england.nhs.net"
          },
          "endpoint": "https://gps.digital.nhs.uk/api"
        },
        "response": {
          "identifier": "6f4256fa-cd14-4f96-899e-008643d84ff8",
          "code": "fatal-error",
          "details": {
            "reference": "urn:uuid:e747c4e4-9228-4ba4-b3e0-6e34b928edac"
          }
        }
      }
    },
    {
      "fullUrl": "https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome",
      "resource": {
        "resourceType": "OperationOutcome",
        "issue": [
          {
            "severity": "error",
            "code": "required",
            "diagnostics": "Line 246. Mandatory element is missing.",
            "expression": [
              "Observation.status"
            ]
          }
        ]
      }
    }
  ]
}
```