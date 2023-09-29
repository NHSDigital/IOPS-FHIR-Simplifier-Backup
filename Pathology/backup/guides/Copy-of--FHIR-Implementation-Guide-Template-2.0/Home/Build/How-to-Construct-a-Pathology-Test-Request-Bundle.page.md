---
topic: BuildContructPathologyRequestBundle
---
## How to Construct a Pathology Test Request Bundle
### Profiles
The following is a list of the STU3 and R4 profiles that are used to construct a Bundle for a Pathology Test Request:

| STU3 Profile Name | R4 Profile Name |
|--
| {{pagelink:STU3Bundle}} | {{pagelink:R4Bundle}} |
| {{pagelink:STU3MessageHeader}} | {{pagelink:R4MessageHeader}} |
| {{pagelink:STU3Organization}} | {{pagelink:R4Organization}} |
| {{pagelink:STU3Patient}} | {{pagelink:R4Patient}} |
| {{pagelink:STU3Practitioner}} | {{pagelink:R4Practitioner}} |
| N/A | {{pagelink:R4PractitionerRole}} |
| {{pagelink:STU3ProcedureRequest}} | {{pagelink:R4ServiceRequest}} |
| {{pagelink:STU3Specimen}} | {{pagelink:R4Specimen}} |

<br>

### STU3 Bundle Diagram
The following diagram illustrates the relationships between each of the FHIR STU3 profiles that form the Bundle. The arrows represent the direction of the references between the profiles.

{{render:path-diagram-STU3-request-bundle}}

### R4 Bundle Diagram
The following diagram illustrates the relationships between each of the FHIR R4 profiles that form the Bundle. The arrows represent the direction of the references between the profiles.

{{render:path-diagram-R4-request-bundle}}