## {{page-title}}

### Positive Acknowledgement of Test Result

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send bio-sampling test report
nhsenglandgps --> grailuk: Send positive acknowledgement
</plantuml>

<br /><br />
#### Message 1 - Send bio-sampling test report
TO BE ADDED

<br /><br />
#### Message 2 - Send positive acknowledgement
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
          "code": "ok"
        }
      }
    }
  ]
}
```


