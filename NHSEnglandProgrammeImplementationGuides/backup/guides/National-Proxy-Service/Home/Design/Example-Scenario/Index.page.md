## {{page-title}}

### Actors

| Name | Type | Description |
|------|------|-------------|
| Proxy Application | system | The application the Proxy uses to create the request |
| NHS England Proxy Service | System | NHS England National Proxy Service |
| NHS England Proxy Repository | System | NHS England National Proxy Data Repository |
| Primary Care | System | General Practice System |

### Consent Verification Workflow 

<plantuml>
@startuml

participant proxy as "Proxy Application"
participant service as "NHS England Proxy Service"
participant repository as "NHS England Proxy Service"
participant gp as "Primary Care"

proxy -> service : Send Proxy Access Request
service -> repository: Store Proxy Access Request
service -> gp: Request Consent Verification (requested)
alt accepted 
gp -> service : Accept Consent Verification (accepted)
gp -> service : Complete Consent Verification (completed)
service -> repository: update Consent
service -> proxy : Inform Proxy of Decision
else rejected
gp -> service : Reject Consent Verification (rejected)
end 

@enduml
</plantuml>