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

title Send Completed Form


actor "Form Filler" as source
actor "Form Recipient" as recipient



source -> recipient: Send Completed Form
recipient --> source: Acknowledgement
@enduml
</plantuml>

<br/>

```
POST [base]/QuestionnaireResponse 
```

#### Example

```
PUT [base]/QuestionnaireResponse
Accept: application/fhir+json
Content-Type: application/fhir+json

{
  "resourceType" : "QuestionnaireResponse",
  "questionnaire" : "https://fhir.nhs.uk/England/Questionnaire/Proxy-Access-Request|0.0.1",
  "status" : "completed",
  "authored" : "2024-03-26T09:32:51.796Z",
  "author" : {
    "reference" : "RelatedPerson/RelatedPerson-NHS-9449304130-Jane-Smith",
    "type" : "Patient",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : "9000000017"
    }
  },
  "item" : [
    {
      "linkId" : "proxyNHSNumber",
      "text" : "NHS Number of the person requesting proxy access",
      "answer" : [
        {
          "valueString" : "9000000017"
        }
      ]
    },
    {
      "linkId" : "patientNHSNumber",
      "text" : "NHS Number of the patient who the proxy will be acting on behalf of",
      "answer" : [
        {
          "valueString" : "9459304130"
        }
      ]
    },
    {
      "linkId" : "proxyRelationship",
      "text" : "What is the relationship of the proxy to the patient",
      "answer" : [
        {
          "valueCoding" : {
            "system" : "http://terminology.hl7.org/CodeSystem/v3-RoleCode",
            "code" : "SISINLAW",
            "display" : "sister-in-law"
          }
        }
      ]
    },
    {
      "linkId" : "proxyBasis",
      "text" : "What is the basic of this proxy request",
      "answer" : [
        {
          "valueCoding" : {
            "system" : "https://fhir.nhs.uk/England/CodeSystem/ToBeDetermind",
            "code" : "parental-responsibility",
            "display" : "parental responsibility"
          }
        }
      ]
    }
  ]
}
```