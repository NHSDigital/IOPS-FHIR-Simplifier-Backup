## {{page-title}}

### Scope

Submits a new or updated Task to a recipient.

### Actors Roles

| Actor | Role |
|--
| Requester | System responsible for sending the original request |
| Filler |  Write-only destination to which requests are sent for processing |


### Messages


<plantuml>
@startuml

hide footbox

title Send Task [PCC-ENG-2]


actor "Request" as source
actor "Filler" as recipient

source -> recipient: Send Task [PCC-ENG-2]
recipient --> source: Acknowledgement
@enduml
</plantuml>

<plantuml>
@startuml

hide footbox

title Respond to Task [PCC-ENG-2]


actor "Request" as source
actor "Filler" as recipient

recipient -> source : Respond to Task [PCC-ENG-2]
source --> recipient: Acknowledgement
@enduml
</plantuml>
<br/>

```
PUT [base]/Task?identifier={system}|{value}
```

The Requester and Filler communicate by exchanging FHIR Task resources. The entire resource  is sent on each exchange and will often a change of status. 

The Task status is shown below which shows the different stages a Task will go through as it is actioned.

<plantuml>
@startuml


state Taskstatus as "Tasks.status (Proxy Validation Request)" {
}



[*] --> Taskstatus.draft
Taskstatus.draft --> Taskstatus.requested
Taskstatus.requested --> Taskstatus.accepted: internal provider Workflow
Taskstatus.requested --> Taskstatus.rejected
note on link
  This may be for several reasons such as
  the requested performer can't verify
  the relationship
end note
Taskstatus.accepted --> Taskstatus.inprogress: internal provider Workflow
Taskstatus.accepted --> Taskstatus.cancelled
Taskstatus.inprogress --> Taskstatus.completed
Taskstatus.inprogress --> Taskstatus.cancelled
Taskstatus.requested --> Taskstatus.cancelled
Taskstatus.completed --> [*]
Taskstatus.rejected --> Taskstatus.requested
note on link
  The Task is amended, maybe
  edited to add a new performer
end note
Taskstatus.rejected --> [*]
Taskstatus.cancelled --> [*]

@enduml
</plantuml>



#### Example

```
PUT [base]/Task?identifier=https://tools.ietf.org/html/rfc4122|41bf06bf-83f3-4004-98d3-480e3f048d55
Accept: application/fhir+json
Content-Type: application/fhir+json

{
  "resourceType" : "Task",
  "identifier" : [
    {
      "system" : "https://tools.ietf.org/html/rfc4122",
      "value" : "41bf06bf-83f3-4004-98d3-480e3f048d55"
    }
  ],
  "status" : "requested",
  "intent" : "order",
   "code" : {
    "text" : "Validate Consent"
  },
  "focus" : {
    "reference" : "Consent/national-proxy-proposed"
  },
  "for" : {
    "reference" : "Patient/Patient_NHS_9459304130",
    "type" : "Patient",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : "9459304130"
    }
  },
  "authoredOn" : "2024-03-26T06:26:00+00:00",
  "requester" : {
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/ods-organization-code",
      "value" : "X26"
    }
  },
  "owner" : {
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/ods-organization-code",
      "value" : "Y12345"
    }
  },
  "note" : [
    {
      "text" : "Please verify the national proxy request for Jayne Smith to access Jayne Smith records. Relationship is MOTHER"
    }
  ]
}
```