## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Proxy Application | System | The application the Proxy uses to create the request |
| NHS England Proxy Service | System | NHS England National Proxy Service |
| NHS England Proxy Repository | System | NHS England National Proxy Data Repository |
| Primary Care | System | General Practice System |

### Request Access and Create a Relationship Workflow 

The sequence diagram below is a high level view of the actual process which focuses on the interactions exchanged between the actors. 

<plantuml>
@startuml

participant proxy as "Proxy Application"
participant service as "NHS England Proxy Service"
participant repository as "NHS England Proxy Repository"
participant gp as "Primary Care"

proxy -> service : Send Proxy Access Request
service -> repository: Store Proxy Access Request
opt if Patient can not consent
service -> gp: Request Consent Verification (requested)
alt accepted 
gp -> service : Accept Consent Verification (accepted)
opt
  gp -> repository: Retrieve Proxy Access Request
end 
gp -> service : Complete Consent Verification (completed)
service -> repository: Update Consent
service -> proxy : Inform Proxy of Decision
else rejected
gp -> service : Reject Consent Verification (rejected)
service -> service : Act on the rejected workflow task (to be defined)
end 
end

@enduml
</plantuml>