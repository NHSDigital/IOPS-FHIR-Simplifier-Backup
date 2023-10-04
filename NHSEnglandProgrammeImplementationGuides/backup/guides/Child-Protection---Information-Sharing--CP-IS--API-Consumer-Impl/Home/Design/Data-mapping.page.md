## {{page-title}}

The CP-IS FHIR API Consumer Data Mapping focuses on presentation of Child protection information to the relevant health and social care professional  via the Consumer application user interface.

HL7v3 Child Protection Domain Message Specification data elements are sourced from the FHIR ReST call resource elements:

**Current Child Protection Information**

| HL7v3 data item | FHIR Source |
|--|--|
|    Type of plan                    | CareTeam.category |
|    Start Date                      | CareTeam.period.start |
|    End Date                        | CareTeam.period.end |
|    Responsible Local Authority     | CareTeam.name |
|    Emergency Duty Tel Number       | CareTeam.telecom.value where CareTeam.telecom.use = "mobile" |
|    Office Hours Tel Number         | CareTeam.telecom.value where CareTeam.telecom.use = "work |
    

**Child Protection Information Previously Viewed By**

| HL7v3 data item | FHIR Source |
|--|--|
|    Date & Time                     | AuditEvent.recorded |
|    Viewer's Name                   | PractitionerRole.practitioner.display |
|    Role                            | PractitionerRole.code.coding.display |
|    Organisation                    | PractitionerRole.organization.display |


A fuller mapping of the HL7v3 message structure to the FHIR Interaction & Resource model is provided on the [CP-IS FHIR API Producer Data mapping page](https://simplifier.net/guide/Child-Protection---Information-Sharing--CP-IS--API-Producer-Impl/Home/Design/Data-mapping.page.md?version=current) to support read and write translation to the underlying HL7v3 data repository.

