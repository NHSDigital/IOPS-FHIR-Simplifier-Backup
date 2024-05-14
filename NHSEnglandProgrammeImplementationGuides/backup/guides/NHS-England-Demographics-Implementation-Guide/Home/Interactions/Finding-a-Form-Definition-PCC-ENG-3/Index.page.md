## {{page-title}}

### Scope

Typically, the form that needs to be filled out in a particular situation will be known in advance. However, if you're dealing with an electronic registry of forms, there needs to be standards on how to find the appropriate form to use.

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

title Finding a Form Definition [PCC-ENG-3]


actor "Form Filler" as source
actor "Form Manager" as recipient

== Retrieve ==

source -> recipient: Retrieve Questionnaire Resource [PCC-ENG-3]
recipient --> source: Questionnaire resource

== Query ==

source -> recipient: Query Questionnaire Resource [PCC-ENG-3]
recipient --> source: Matching Questionnaire resources

@enduml
</plantuml>

<br/>

#### Retrieve Questionnaire Resource

```
GET [base]/Questionnaire/{id} 
```

#### Query Questionnaire Resource

```
GET [base]/Questionnaire?{parameters} 
```

| Parameter | Conformance | Type | Definition |
|--
| code | SHALL | token | A code that corresponds to one of its items in the questionnaire |
| context | SHALL | token | A use context assigned to the questionnaire |
| date | SHALL | date | The questionnaire publication date |
| identifier | SHALL | token | 	External identifier for the questionnaire |
| publisher | SHALL | string | Name of the publisher of the questionnaire |
| status | SHALL | token | The current status of the questionnaire |
| title | SHALL | string | The human-friendly name of the questionnaire |
| version | SHALL | token | The business version of the questionnaire |
| definition | SHALL | uri | ElementDefinition - details for the item |


 