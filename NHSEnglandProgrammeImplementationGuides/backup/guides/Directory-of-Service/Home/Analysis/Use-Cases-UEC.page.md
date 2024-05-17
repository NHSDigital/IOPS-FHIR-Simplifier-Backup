# {{page-title}}

## Search DoS with Clinical Triage System 

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> user of a clinical triage system (e.g. 111, 111 Online)<br><strong>I want</strong> to be able to search for appropriate services that are able to meet the patient’s needs within a specified time frame<br><strong>So that</strong> patients can be directed or referred to a service that is able to assess and/or treat them</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>111 Healthcare Advisors, 111 Clinicians, 111 Online Users, Streaming and Redirection users</td></tr><tr><td><strong>Frequency of Use</strong></td><td>24/7 - Approx. 2 million searches per month</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Pathways triage completed</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td>Search system has approval to use DoS and an active DoS account</td></tr><tr><td><strong>Post Conditions</strong></td><td>A curated list of appropriate services is returned</td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>Pathways triage is completed with an outcome that the patient needs to be signposted or referred to a service</li><li>Case management system makes API call to DoS, including all required information</li><li>DoS search is completed, matching services according to clinical need and location</li><li>DoS returns an ordered list of appropriate services, taking into account search, referral and commissioning rules</li><li>Search results are displayed to the case management system</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>n/a</td></tr><tr><td><strong>Exception</strong></td><td>Invalid information is passed to DoS via the API, returning an error message to the requesting service
</td>
</tr></tbody></table>
<br>

<plantuml>
@startuml
actor Triage
participant "Case Management System"
participant "Directory of Services"
activate "Case Management System"
Triage -> "Case Management System": Referral for service
activate "Directory of Services"
"Case Management System" -> "Directory of Services": API call for list of services
"Directory of Services" --> "Case Management System": List of apropriate services
deactivate "Directory of Services"
"Case Management System" -> Triage: Search resluts displayed
deactivate "Case Management System"
@enduml
</plantuml>

## Search DoS without Clinical Triage System 

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> clinician who uses a system approved to search the DoS<br><strong>I want</strong> to be able to search for appropriate services that are able to meet the patient’s needs within a specified time frame<br><strong>So that</strong> patients can be directed or referred to a service that is able to assess and/or treat them</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Service Finder Users, Clinicians who use 3rd Party apps approved to use DoS APIs</td></tr><tr><td><strong>Frequency of Use</strong></td><td>24/7 - Approx. 2 million searches per month</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Clinician uses a search tool to find an appropriate service for the patient</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td>Search system has approval to use DoS and an active DoS account</td></tr><tr><td><strong>Post Conditions</strong></td><td>A list of services matching the search criteria is returned</td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>Clinician enters search criteria into 3rd party tool</li><li>Request is received and validated by DoS</li><li>DoS search is completed, matching services according to clinical need and location</li><li>DoS returns matching services according to search criteria </li><li>Results are displayed by 3rd party system</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>n/a</td></tr><tr><td><strong>Exception</strong></td><td>Invalid information is passed to DoS via the API, returning an error message to the requesting service
</td>
</tr></tbody></table>
<br>

<plantuml>
@startuml
actor Clinician
participant "3rd Party Tool" as ThirdPartyTool
participant "Directory of Services (DoS)" as DoS

Clinician -> Clinician: Use search tool

Clinician -> ThirdPartyTool: Enter search criteria
activate ThirdPartyTool

ThirdPartyTool -> DoS: Send search request
activate DoS

DoS -> DoS: Validate and process request
DoS --> ThirdPartyTool: Return matching services
deactivate DoS

ThirdPartyTool --> Clinician: Display results
deactivate ThirdPartyTool
@enduml
</plantuml>

## Maintain Data via the DoS UI 

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> DoS Lead or service owner responsible for the accuracy and completeness of the data in DoS<br><strong>I want</strong> to be able to search, view and update that data<br><strong>So that</strong> I can profile services so that those searching the DoS receive correct and accurate information</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>DoS Leads, Service Owners</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Multiple times per day</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Service data has changed or new services are commissioned</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td>User has an active DoS account with appropriate update permissions</td></tr><tr><td><strong>Post Conditions</strong></td><td>Service profiling is correct</td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>User logs into DoS</li><li>User navigates to the function required within the DoS</li><li>User makes profiling updates as required </li><li>User logs out</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>n/a</td></tr><tr><td><strong>Exception</strong></td><td>n/a
</td>
</tr></tbody></table>

<br>

<plantuml>
@startuml
actor "Service Owner"
participant "DoS System" as DoS
"Service Owner" -> DoS: Log into DoS
activate DoS
DoS -> "Service Owner": Display login screen
"Service Owner" -> DoS: Enter credentials
DoS -> DoS: Authenticate user
DoS -> "Service Owner": Display main dashboard
"Service Owner"-> DoS: Navigate to required function
DoS -> "Service Owner": Display required function
"Service Owner"-> DoS: Make profiling updates
DoS -> DoS: Save updates
DoS -> "Service Owner": Confirm updates saved
"Service Owner"-> DoS: Log out
DoS -> "Service Owner": Confirm logout
deactivate DoS

@enduml
</plantuml>

## Report and record Capacity Management data 

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> Capacity Management User<br><strong>I want</strong> to be able to update services with the required information about their bed capacity<br><strong>So that</strong> this can be monitored and appropriate decisions made</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Hospital Capacity Managers, Ward staff, Administrators</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Daily, generally twice per day for each user</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Daily sitution report needs to be completed</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td>User has an active DoS account with appropriate permissions</td></tr><tr><td><strong>Post Conditions</strong></td><td><ol><li>Hospital situation report has been updated</li><li>Users are able to view and compare capacity data for their hospital and those of other areas</li><li>Service profiling is correct</li></ol></td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>User logs in</li><li>User navigates to the correct service profile</li><li>User saves changes</li><li>User completes a search based on geography and service type</li><li>User views summary data for services returned in the search</li><li>User navigates to reporting page</li><li>User selects region, grid and timeframes and exports required data</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>n/a</td></tr><tr><td><strong>Exception</strong></td><td>n/a
</td>
</tr></tbody></table>