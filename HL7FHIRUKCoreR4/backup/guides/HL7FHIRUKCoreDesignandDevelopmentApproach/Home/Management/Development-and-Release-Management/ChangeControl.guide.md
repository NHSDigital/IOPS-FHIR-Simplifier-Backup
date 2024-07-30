## {{page-title}}

This section details a change control process for use with the UK Core standard. The change control process is part of the overall configuration management.

### Change Control Roles

- **Requester** - Any individual or group/organisation requesting a change to an existing FHIR asset in the UK Core or requesting a new FHIR asset to be added to the UK Core.
- **UK Core Development Team** - Individuals who are involved in the UK Core FHIR assets development and/or authoring guidance contained in the UK Core Implementation Guide.
- **UK FHIR Delivery Senior Leadership Team (SLT)** - a group of people from the FHIR community who represent the interests of stakeholders in the UK Core.
- **UK FHIR Delivery Senior Leadership Team Technical Subgroup** - a group of FHIR/Interoperability and clinical subject matter experts who evaluate UK Core requests for change then triage and route them as appropriate.

### Requesting a Change to the UK Core

All requests for a change to the UK Core standard must be made using the create issue option in Simplifier. Requests may be from an individual or group/organisation looking to use the UK Core for an implementation or for an issue reported by a member of the development team. The same approach is used to feedback on issues by participants in the Clinical and Technical Assurance process. For more information on how to request a change see {{pagelink:Requests--Issues-and-Feedback}}


### Issue Triage by UK Core Development Team
Issues will be triaged by the UK Core Development Team and any change other than a minor issue (for example a typo or a bug fix) will be referred to a Senior Technical lead from the SLT Technical Subgroup or discussed at the UK FHIR Delivery Board for further appraisal. 

If the issue raised does not have a solution suggested, then the triage will include further analysis to establish a solution which may include several proposed technical options. If the requester has provided a proposed solution, this will need to be validated, which may result in alternative or other solutions being proposed. 

The response time for issues to be initially triaged does not have a formal service level agreement in place but should be responded to in a timely manner. This is managed by NHS England as part of its role in the UK Core Development Team using the Interoperability Team's mailbox, which receives auto-notifications from Simplifier on a daily basis. The mailbox is monitored daily by the NHS England Interoperability Team and initial triage will be done within a day or two, except when the issue has been raised as part of the {{pagelink:Clinical-and-Technical-Assurance}} process. 


Note: The triage of issues raised as part of Clinical and Technical Assurance process (which has a three-week review period) is done at the end of the 
Clinical and Technical Assurance process as a batch. This enables more efficient triage of issues and the identification of dependencies and issue duplication.

### Triage of Non-Clinical and Technical Assurance process issues
The triage process for issues is not something that is a tightly defined process, but more of a discussion forum of Subject Matter Experts (SMEs) where a consensus of agreement is reached about the issue and any proposed solution. The following are examples of criteria or areas that will be discussed:

- Is the reason or use case for the requested change or addition to the UK Core clear enough to triage the issue?
- Is the proposed change suitable for the use case, for example are the profiles that are being requested or requested to be changed the correct profiles for the use case?
- Is the use case already covered by another asset or set of assets?
- Is this a potential breaking or non-breaking change? This is only potential, as what is a breaking on non-breaking change can be very hard to quantify in some cases.
- Does the issue need to be referred to a wider audience or a special resource, for example a Clinical lead?

The Simplifier issue will be updated with any information that will inform the requester of progress, etc.

### Triage of Clinical and Technical Assurance process issues
The triage process for issues raised as part of the Clinical and Technical Assurance process is done as a batch process by the UK Core Development team at the end of the process. The issues raised are filtered to remove duplicates or minor issues such as typos or minor technical errors. 
The remaining issues are taken forward to the Clinical and Technical Assurance follow up meeting for discussion, agreement and resolution. 

The Simplifier issue will be updated with any information that will inform the requester of progress etc.

### Approval of issue

Once a change request is accepted, the issue is added to the UK Core Backlog. The requester will be notified via Simplifier by update of the issue. The issue will not be closed at this point, only when the development work has been completed.

### Rejection of issue

If a request for change is rejected, then the Simplifier issue is updated with all the information required to inform the requester why it  was rejected. Further calls or emails may also be used to explain the reason for rejection, if required, depending on the complexity of the issue. 

### Development Backlog
The UK Core backlog is where all the development work items are recorded and tracked. The work items are maintained using a tool called JIRA. All the work items in JIRA will be traceable back to Simplifier. The development is carried out using an agile type of methodology and managed on a Kanban board. The UK Core backlog is an internal process which only the UK Core Development team have access to, however this information is mirrored in the Simplifier issues for consumption by the FHIR community. The requester will be emailed whenever there is an update to the Simplifier issue.  

---

