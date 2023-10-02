## {{page-title}}

The CP-IS FHIR API Producer Data Mapping focuses on:
- translation of the inbound FHIR GET request into a well-formed call to the existing HL7v3 repository, as a CP-IS NHS Query (QUPC_MT000006GB01)
- translation of any Child Protection information in the response, CP-IS NHS Query Response (REPC_MT000007GB01), to a FHIR response as CareTeam resources
- translation of any Access History information in the response, CP-IS NHS Query Response (REPC_MT000007GB01), to a FHIR response as AuditEvent (and PractitionerRole) resources
 presentation of Child protection information to the relevant health and social care professional  via the Consumer application user interface.

### GET /[resource] request


| Request Source | HL7v3 CP-IS NHS Query target |
|--|--|
| time of http query                                        | Time of query                     |
| Resolved by API Producer from Authorization access token  | Requesting clinician role code    |
| Resolved by API Producer from Authorization access token  | Requesting clinician role name    |
| Resolved by API Producer from Authorization access token  | Requesting clinician name         |
| Resolved by API Producer from Authorization access token  | Requesting clinician represented organisation name |
| http query parameter                                      | Child NHS Number                  |
| http custom header                                        | Scheduled/unscheduled care        |


### GET /CareTeam response


| HL7v3 Data item | HL7v3 source (xpath) | FHIR element target (fhirpath)
|--|--|--|
| Time of response                                      | /CP-ISNHSQueryResponse/effectiveTime/@value                                                   | Not used |
| Total Returned Child Protection Plan Records          | /CP-ISNHSQueryResponse/pertinentInformation12/pertinentTotalReturnedChildRecords/value/@value | Bundle.total |
| Responsible Local Authority Care Team                 | /CP-ISNHSQueryResponse/pertinentInformation14/pertinentCP-ISRecordControlAct/record/communicationFunctionSnd/organisation/name    | CareTeam.name |
| Responsible Local Authority Care Team Phone details   | /CP-ISNHSQueryResponse/pertinentInformation14/pertinentCP-ISRecordControlAct/record/communicationFunctionSnd/organisation/telecom | CareTeam.telecom |
| Plan Type                                             | /CP-ISNHSQueryResponse/pertinentInformation14/pertinentCP-ISRecordControlAct/record/CP-ISRecord/pertinentInformation15/npfitlc:contentId/@extension                                                                                                                                 | CareTeam.category |
| Plan Start Date                                       | /CP-ISNHSQueryResponse/pertinentInformation14/pertinentCP-ISRecordControlAct/record/CP-ISRecord/pertinentInformation15/COCT_TP146104GB01.UCPInformation/component/uCPStartDate/value/@value | CareTeam.period.start |
| Plan End Date                                         | /CP-ISNHSQueryResponse/pertinentInformation14/pertinentCP-ISRecordControlAct/record/CP-ISRecord/pertinentInformation15/COCT_TP146104GB01.UCPInformation/component1/uCPEndDate/value/@value  | CareTeam.period.end |
| Subject NHS Number                                    | /CP-ISNHSQueryResponse/pertinentInformation13/pertinentCP-ISNHSQuery/queryByParameter/person.NHSnumber/value/@extension           | CareTeam.subject |

### GET /AuditEvent response

| HL7v3 Data item                               | HL7v3 source (xmlpath) | FHIR element target
|--|--|--|
| Time of access                                | /CP-ISNHSQueryResponse/pertinentInformation13/pertinentCP-ISNHSQuery/effectiveTime/@value             | AuditEvent.recorded   |
| Total Returned Access Records                 | /CP-ISNHSQueryResponse/pertinentInformation11/pertinentTotalReturnedAccessRecords/value/@value        | Bundle.total |
| Querying clinician name                       | /CP-ISNHSQueryResponse/pertinentInformation13/pertinentCP-ISNHSQuery/author/COCT_TP145102GB01.AssignedAuthor/assignedAuthorPerson/name    | PractitionerRole.practitioner.display |
| Querying clinician role                       | /CP-ISNHSQueryResponse/pertinentInformation13/pertinentCP-ISNHSQuery/author/COCT_TP145102GB01.AssignedAuthor/code/@displayName            | PractitionerRole.code.coding.display |
| Querying clinician represented organisation   | /CP-ISNHSQueryResponse/pertinentInformation13/pertinentCP-ISNHSQuery/author/COCT_TP145102GB01.AssignedAuthor/representedOrganization/name | PractitionerRole.organization.display |