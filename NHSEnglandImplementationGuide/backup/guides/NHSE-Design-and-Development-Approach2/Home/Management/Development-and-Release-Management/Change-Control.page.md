## {{page-title}}

This section details a change control process for use with the NHS England standard. The change control process is part of the overall configuration management.

### Overview of Process 

{{render:NHSEChangeControl}} 

<plantuml>
start
group [Level 1 Change Process]
group [Requestor/Customer]
if (Is the request within scope ?) then (Existing guidance issue identified)
  :Create simplifier tickets against relevant IG;
  :Interoperability email autocreated from Simplifier;
else (New project or change the existing project guidance?
Project) 
:Provide advice and request NWR from Requester;
if (Is NWR Recieved ?) then  (Yes)
  :NWR Process;  
else (No)
stop
endif
endif
:NHSE build and Release scheduling;
:Design and Build Process;
:NHSE Assurance Process;
stop
</plantuml>


### Change Control Roles

- **Requester** - Any individual or team requesting a change to an existing FHIR asset in the NHS England IG or requesting a new FHIR asset to be added to the NHS England IG.
- **NHS England IOPS Team**- Individuals who are involved in the NHS England FHIR assets development and/or authoring guidance contained in the NHS England Implementation Guide.
- **Stakeholder** – Any individual or team using the NHS England IG or involved in FHIR implementation and/or design within NHS England.

### Requesting a Change to the NHS England IG
Requests for a change to the NHS England IG shall be made using the create issue option in Simplifier if it’s not a project or programme which is formally engaging with the NHS England IOPS Team. Requests may be from an individual or team looking to use the NHS England IG for an implementation or for an issue reported by a member of the development team. The same approach is used to feedback on issues by participants in the Clinical and Technical Assurance process.

### Navigation to the NHS England IG Project
The NHS England IG Simplifier project is located [here]( https://simplifier.net/NHS-England-Implementation-Guide/~guides).

Requests for new NHS England IG FHIR assets can be raised as an issue at the NHS England IG project level in Simplifier. The requests shall indicate the use case or details of the requirement as to why the new asset is needed.

### Creating a Simplifier Issue at Project Level
The NHS England IG uses Simplifier for issue tracking and maintenance.
Although the NHS England IG is in the public domain, you will need to create an account and login to raise issues. 


Creating a Simplifier account is done by going to <a href="https://simplifier.net/NHS-England-Implementation-Guide/~introduction" target="_blank"> https://simplifier.net/</a> and using the sign-up option on the top right of the page. An email address and a chosen password are the only details needed to set up an account. 

To create a issue at the project level, navigate to the project. Once you are in the project, click on the issues tab and then the create button to create the issue.

### Login to Simplifier 
Logging in to your Simplifier account is required to raise issues. Browse to <a href="https://simplifier.net/" target="_blank">https://simplifier.net/</a> and use the login option on the top right of the page, then enter the chosen credentials. 
<a id="navigateproject"></a>

### Change to an existing NHS England IG Asset
When the change request is for a change to an existing NHSE IG FHIR asset, the preferred approach is to raise the issue at the level of the relevant asset.

### Create a Simplifier issue at NHS England IG Asset level

It is acknowledged that not everyone will have enough knowledge of FHIR Implementation Guides or Simplifier to log an issue to the correct Simplifier resource, therefore logging at the project level is allowable, if this is the case. However, issue logging at asset level is the preferred approach, as it makes triage of issues easier.    

**Note: Simplifier refers to everything as a resource whether it’s an image, example or FHIR profile and provides a mechanism to filter on type.**

#### Step 1 - How to search and filter  
<a href="https://drive.google.com/file/d/1B7c9FOgE0-SYvYZ3qzbGxIDnf1Kdsa9T/view?usp=sharing" target="_blank"> How to search and filter in Simplifier illustration</a>   

To search for a particular asset, for example to find the Patient profile, filter by resource category "Profiles" (tick the box alongside Profiles), add the word "Patient" in the search box and hit return. This will bring up a link to the Patient profile which will take you to a page with a view of the Patient profile.

Once the required Simplifier resource page is found, the last tab on the page is the issues tab. Clicking on this will bring up a page where a new issue should be raised by clicking the New Issue button.

#### Step 2 - Create new issue
<a href="https://drive.google.com/file/d/1QkFbCCnUHs48B-GFgfT0OhWpIwvL6z4Q/view?usp=sharing">Create new issue illustration</a>

This will only require a title and the details of the issue or comment. All other issues logged for this Simplifier resource will be available from this page and you can check these or find out whether this issue has already been logged, if required.

#### Step 3 - New issue information required
<a href="https://drive.google.com/file/d/1df2jCXzbX0qS4bh8ndLQEz3jqPC10cKr/view?usp=sharing" target="_blank"> New issue information required illustration</a>

If you cannot locate the Simplifier resource, or it is not appropriate to log an issue at the Simplifier resource level, then you should raise an issue at the project level. In this case, the title and/or issue text should identify which part of the NHSE IG Implementation is the subject of the issue being raised. See the Creating a Simplifier Issue at Project Level section for how to do this.

### Requesting a new NHS England IG Asset
Issues for new NHS England IG FHIR assets can be raised at the NHS England IG project level the issue shall indicate the use case or details of the requirement as to why the new asset is needed. Projects or Programmes may also raise requests for new or amended FHIR assets.

### Creating a Simplifier Issue at Project Level

To create a issue at the project level, [navigate to the project](https://simplifier.net/NHS-England-Implementation-Guide/~introduction "Title"). Once you are in the project, click on the issues tab and then the create button to create the issue.

### Issue Triage by NHS England IG Development Team
Issues will be triaged by the IOPS Team and all agreed changes will be added to draft release which will then enter a Clinical and technical assurance sprint and released on completion.

The response time for issues to be initially triaged does not have a formal service level agreement in place but should be responded to in a timely manner. This is managed by the Interoperability Standards Team (IOPS) using the Interoperability Team's mailbox, which receives auto-notifications from Simplifier on a daily basis. The mailbox is monitored daily by IOPS and initial triage will be done within a day or two, except when the issue has been raised as part of the Clinical and Technical Assurance process.

Note: The triage of issues raised as part of Clinical and Technical Assurance process is done at the end of the Clinical and Technical Assurance process as a batch. This enables more efficient triage of issues and the identification of dependencies and issue duplication.


### Triage of Non-Clinical and Technical Assurance process issues
The triage process for issues raised as part of the Clinical and Technical Assurance process is done as a batch process by IOPS at the end of the process. The issues raised are filtered to remove duplicates or minor issues such as typos or minor technical errors. The remaining issues are taken forward to the Clinical and Technical Assurance follow up meeting for discussion, agreement, and resolution.

### Approval of issue
Once a change request is accepted, the issue is added to the NHS England IG Development Backlog. The requester will be notified via Simplifier by update of the issue. The issue will not be closed at this point, only when the development work has been completed.

### Development Backlog
The NHS England IG Development backlog is where all the development work items are recorded and tracked. The work items are maintained using a tool called JIRA. All the work items in JIRA will be traceable back to Simplifier. The development is carried out using an agile type of methodology and managed on a Kanban board. The NHS England IG development backlog is an internal process which only the IOPS team have access to, however this information is mirrored in the Simplifier issues for consumption by the stakeholders. The requester will be emailed whenever there is an update to the Simplifier issue.

### Rejection of issue

If a request for change is rejected, then the Simplifier issue is updated with all the information required to inform the requester why it  was rejected. Further calls or emails may also be used to explain the reason for rejection, if required, depending on the complexity of the issue. 
 

---

