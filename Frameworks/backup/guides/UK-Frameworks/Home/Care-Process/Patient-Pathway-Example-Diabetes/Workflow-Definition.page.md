## {{page-title}}


This is defining steps along a pathway, it is currently documented in programme's such NICE, Diabetes UK Pathways, Diabetes Prevention programme, etc.
In this guide we have chosen to also use narrative and diagrams to describe workflow definitions. 
The relationship of Definition to `Request` and `Event` is shown below:

{{render:diagrams-Workflow-definition}}

The examples of definition we have used in {{pagelink:Home/Care-Process/Patient-Pathway-Example-Diabetes}} include:

| Definition | Type |  Input | Output |
|--
| NHS Health Check | Information Gathering |  Questionnaire (vital signs) | QuestionnaireResponse (vital signs) |
| Diabetes Risk Assessment | Information Gathering | Questionnaire (Type 2 Diabetes Risk) | QuestionnaireResponse (Type 2 Diabetes Risk) |
| Diabetes Prevention Programme Referral | Patient Referral |QuestionnaireResponse (Type 2 Diabetes Risk) | ServiceRequest |

This is an area for elaboration and may include the use of [FHIR PlanDefinition](https://hl7.org/fhir/R4/plandefinition.html) and 
[FHIR ActivityDefinition](https://hl7.org/fhir/R4/activitydefinition.html)
