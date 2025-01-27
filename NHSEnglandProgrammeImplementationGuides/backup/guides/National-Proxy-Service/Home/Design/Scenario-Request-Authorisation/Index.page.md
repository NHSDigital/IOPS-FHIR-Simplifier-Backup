## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Client Application | System | The application the Proxy uses to create the request. IHE refers to this as the `Consent Recorder` |
| NHS England Proxy Service | System | NHS England National Proxy Service |
| National Proxy Registry | System | NHS England National Proxy Data Registry. IHE refers to this as the `Consent Registry` |
| Primary Care | System | General Practice System |


### Use Case(s)

- {{pagelink:Home/Analysis/Use-Case-Create-a-Relationship.page.md}}
- {{pagelink:Home/Analysis/Use-Case-Request-Access.page.md}}

### Background Standards

- [IHE Privacy Consent on FHIR (PCF)](https://profiles.ihe.net/ITI/PCF/volume-1.html)
- [HL7 FHIR Workflow](https://hl7.org/fhir/R4/workflow.html)

### Request Authorisation

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

See {{pagelink:Home/Design/Scenario-Request-Proxy-Access}} for a description of the first part of the sequence.

<plantuml>
@startuml

participant proxy as "Client Application"
participant service as "NHS England Proxy Service"
participant repository as "National Proxy Registry"
participant gp as "Primary Care"

proxy -> service : Send Proxy Access Request
opt if Patient can not consent
service -> gp: Request Consent Verification (requested)
alt accepted 
gp -> service : Accept Consent Verification (accepted)
opt
  gp -> repository: View Proxy Access Request\n(IHE Access Consent - Read (ITI-108))
end 
gp -> service : Complete Consent Verification (completed)
service -> repository: Update National Proxy Registry\n(IHE Access Consent - Update (ITI-108))
service -> proxy : Inform Proxy of Decision
else rejected
gp -> service : Reject Consent Verification (rejected)
service -> service : Act on the rejected workflow task (to be defined)
end 
end

@enduml
</plantuml>