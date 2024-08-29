## {{page-title}}

### CapabilityStatement

### MessageDefinition - Request


### MessageDefinition - Report

{{render:https://fhir.nhs.uk/England/MessageDefinition/England-Pathology-Report}}

<fql output = "transpose">

from

    CapabilityStatement
where
    id = "https://fhir.nhs.uk/England/MessageDefinition/England-Pathology-Report"
select
    format, jurisdiction.coding.system, jurisdiction.coding.code, rest.resource.documentation

</fql>