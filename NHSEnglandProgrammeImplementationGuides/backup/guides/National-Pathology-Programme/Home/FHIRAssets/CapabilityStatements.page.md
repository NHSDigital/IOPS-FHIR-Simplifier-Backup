---
topic: FHIRAssetsR4CapabilityStatements
---
## CapabilityStatements

<fql output="transpose">
  from 
    CapabilityStatement
  where 
    id = 'England-Pathology-Requirements'
  select
    Id: id,
    URL: url,
    Version: version,
    Name: name,
    Description: description,
    Status: status,
    Date: date,
    Publisher: publisher,
    Kind: kind,
    Format: format
</fql>

{{render:https://fhir.hl7.org.uk/England/CapabilityStatement/England-Pathology-Requirements}}
