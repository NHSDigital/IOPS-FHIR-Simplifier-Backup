---
topic: FHIRAssetsCapabilityStatements
canonical: https://fhir.hl7.org.uk/England/CapabilityStatement/England-Pathology-Requirements
myid: %England-Pathology-Requirements
---
## CapabilityStatements

### Render
{{render:England-Pathology-Requirements}}

### Inline using url
<fql output="inline">
    from CapabilityStatement
    where url = %canonical 
    select description
</fql>

### Inline using id
<fql output="inline">
    from CapabilityStatement
    where id = %myid 
    select description
</fql>