## {{page-title}}

### Scope

Submit completed form data to an external data repository.

### Actors Roles

| Actor | Role |
|--
| Form Filler | System responsible for capturing user form input to produce partially or fully completed forms |
| Form Recipient |  Write-only destination to which forms are sent for processing |

The Form Filler (possibly with help from the Form Manager) is responsible for verifying that a completed form is complete and valid against the corresponding Questionnaire. Once valid, the form filler submits the form to one or more target repositories

### Messages

<plantuml>
@startuml

hide footbox

title Send Completed Form [ENG-1]


actor "Form Filler" as source
actor "Form Recipient" as recipient



source -> recipient: Send Completed Form [ENG-1]
recipient --> source: Acknowledgement
@enduml
</plantuml>

<br/>

```
POST [base]/QuestionnaireResponse 
Content-Type: application/fhir+json
```