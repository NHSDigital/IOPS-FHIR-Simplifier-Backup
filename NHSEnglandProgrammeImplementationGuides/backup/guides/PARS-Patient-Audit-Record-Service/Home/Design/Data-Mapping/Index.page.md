## {{page-title}}

## Entity Model

See [NHS England Confluence PARS KAD003 Schema - WIP](https://nhsd-confluence.digital.nhs.uk/display/PARS/PARS+KAD003+Schema+-+WIP)
Examples are modified versions of these [NHS England Confluence PARS examples](https://nhsd-confluence.digital.nhs.uk/pages/viewpageattachments.action?pageId=864404462)  

## Entity Mapping 

| Description | FHIR AuditEvent                                            | Comment                             |
|-------------|------------------------------------------------------------|-------------------------------------|
| DateTime the event happened | recorded                                                   |                                     |
| Patient NHS number | entity[patient].what.identifier.value                      |                                     |
| HL7V3 identifier, for FHIR there is no standard | entity[endpoint].detail[interactionIdentifier].valueString | changed                             |
| Alternative name for interactionID, looks like an historical unnecessary duplication |                                                            |                                     |
| Human readable interactionID | entity[endpoint].name                                      | changed                             |
| High level grouping of the message types | entity[endpoint].detail[productIdentifier].valueString     | changed                             |
| ODS code of the organisation | agent[organisation].identifier.value                       |                                     |
| Name of the organisation | agent[organisation].display                                |                                     | 
| Spine Accredited System Id | entity[endpoint].what.identifier.value                     |                                     |
| ODS code of the organisation submitted in the message/headers | entity[submittedOrganisation].what.identifier.value        | ?                                   |
| User identifier | agent[user].identifier.value                               |                                     |
| User Name | agent[user].display                                        |                                     | 
| Role Profile ID of the user | agent[userRole].identifier.value                           |                                     |
| Transaction ID of the message | entity[transaction].what.identifier                        |                                     | 
| Audit Creator Name (the system which has generated the event) | source.observer.display                                    |
| Audit Creator Identifier  code | source.observer.identifier.value                           | Do we also need to allow productId? |
| Audit Creator system Identifier | source.site                                                | Are these the correct way around    | 
| Type of operation - Create Read Update Delete | action                                                     |                                     | 
