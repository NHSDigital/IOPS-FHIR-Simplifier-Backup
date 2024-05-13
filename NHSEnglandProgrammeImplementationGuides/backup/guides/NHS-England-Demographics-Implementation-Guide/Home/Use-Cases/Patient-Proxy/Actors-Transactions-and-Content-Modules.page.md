## {{page-title}}

### Actors

- **Patient Proxy Requester** A carer for a Patient who wishes to access the Patients data and services.
- **Patient Proxy Registry** A central service for managing Patient Proxy Requests
- **Patient Proxy Authoriser** A person (normally a GP) who can confirm the Patient Proxy Request.


### Use Case

> Joshua mother has become blah blah TODO

### Process Flow

<plantuml>
@startuml

hide footbox

title Create Patient Proxy

actor "Patient Proxy Requester" as patient
actor "Patient Identity Source" as source
actor "Patient Proxy Authoriser" as GP


patient -> patient : Patient Proxy completes proxy request
patient -> source: Completed Patient Proxy Request Form
source --> patient: Acknowledgement
source -> source: Create Consent
source -> source: Share Consent
opt Needs Validating
source -> GP: Request Patient Proxy Request is validated
GP -> source: Retrieve Patient Proxy Request
GP -> source: accept or reject Patient Proxy Request
else 
source -> source: automatically accept Patient Proxy Request 
end
source -> source: Update Consent
@enduml
</plantuml>


#### Pre-conditions:

TODO

#### Main Flow:

TODO

#### Post-conditions:

TODO


<plantuml>
@startuml


state Consentstatus as "Consent.status (Proxy Request)" {
}

state Taskstatus as "Tasks.status (Proxy Validation Request)" {
}



[*] --> Consentstatus.proposed
Consentstatus.proposed --> Taskstatus.requested
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
Taskstatus.completed --> Consentstatus.active
Taskstatus.rejected --> Taskstatus.requested
note on link
  The Task is amended, maybe
  edited to add a new performer
end note
Taskstatus.rejected --> Consentstatus.rejected
Taskstatus.cancelled --> [*]
Consentstatus.active --> RelatedPerson
note on link
  This is an implied action based
  on the change of state
end note
Consentstatus.rejected --> [*]
RelatedPerson --> [*]

RelatedPerson : [created or updated]

@endum
</plantuml>



### Access Consent

Maybe move the follow to a different page as this is getting into specifics

This describes how a Consent can be used to control API access  [IHE Privacy Consent on FHIR -  Access Consent [ITI-108]](https://profiles.ihe.net/ITI/PCF/ITI-108.html)

<plantuml>
@startuml

hide footbox

title National Proxy Service - View a Relationship


participant User as "Consent Authoriser"
participant "Patient Proxy Registry" as NationalProxy


User -> NationalProxy : Access Consent \nGET /RelatedPerson?{queryParameters}
NationalProxy --> User: A collection of matching Consents

@enduml
</plantuml>

