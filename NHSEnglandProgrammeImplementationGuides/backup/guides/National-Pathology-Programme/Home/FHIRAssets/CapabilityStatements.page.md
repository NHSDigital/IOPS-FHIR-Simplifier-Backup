---
topic: FHIRAssetsR4CapabilityStatements
---
## CapabilityStatements

The following `CapabilityStatement` has been created specifically for use in pathology:

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

The following table summarises the Messaging Capabilities associated with this `CapabilityStatement`. Refer to {{pagelink:FHIRAssetsR4MessageDefinitions}} for further information.

{{render:https://fhir.hl7.org.uk/England/CapabilityStatement/England-Pathology-Requirements}}
