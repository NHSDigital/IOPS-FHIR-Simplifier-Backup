---
topic: FHIRAssetsR4MessageDefinitionReport
---

{{render:https://fhir.nhs.uk/England/MessageDefinition/England-Pathology-Report}}

<fql output="transpose">
  from 
    MessageDefinition
  where 
    id = 'England-Pathology-Report'
  select
    URL: url 
</fql>