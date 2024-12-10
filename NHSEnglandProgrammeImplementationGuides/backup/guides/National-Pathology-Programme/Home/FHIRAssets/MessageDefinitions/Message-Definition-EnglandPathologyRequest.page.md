---
topic: FHIRAssetsR4MessageDefinitionRequest
---

{{render:https://fhir.nhs.uk/England/MessageDefinition/England-Pathology-Request}}

<fql output="transpose">
  from 
    MessageDefinition
  where 
    id = 'England-Pathology-Request'
  select
    URL: url 
</fql>

---