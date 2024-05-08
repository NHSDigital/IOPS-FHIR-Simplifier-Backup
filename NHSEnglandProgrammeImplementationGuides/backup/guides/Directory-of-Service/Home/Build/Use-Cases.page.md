# {{page-title}}


## Generic - Searching for a healthcare service

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> Healthcare Worker (HW)<br><strong>I can</strong> search for the most appropriate healthcare service based on the patient’s needs, location and availability<br><strong>So that</strong> the patient can receive the appropriate care/treatment</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Healthcare Worker, Patient, System (DoS)</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Whenever a service is required</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>HW identifies a patient who requires specialist consultation or other healthcare services beyond the scope of primary care</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td><ol><li>HW has access to DoS</li><li>Patient information and needs are known</li></ol></td></tr><tr><td><strong>Post Conditions</strong></td><td>Suitable healthcare service is identified</td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>If no NHS number exists for the submitted individual, a new NHS number is allocated and returned to the user.</li><li>HW searches for relevant healthcare services based on patient needs</li><li>HW receives a list of relevant services, including address and opening times</li><li>HW provides the patient with a list of relevant healthcare services to enable them to select the most appropriate service</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>If the desired service is not available or suitable, the HW may need to search for alternative services</td></tr><tr><td><strong>Exception</strong></td><td>In case of technical issues or downtime with the DoS platform, the healthcare worker may resort to traditional referral methods</td>
</tr></tbody></table>
<br>


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

## Report and record Capacity Management data 

<table class="assets" title="PDS Use Case 1">

</tr><tr>
<td><strong>User Story Summary (Clinical Overview)</strong></td><td><strong>As a</strong> Capacity Management User<br><strong>I want</strong> to be able to update services with the required information about their bed capacity<br><strong>So that</strong> this can be monitored and appropriate decisions made</td>
</tr><tr>
<td><strong>Actors (Role)</strong></td><td>Hospital Capacity Managers, Ward staff, Administrators</td></tr><tr><td><strong>Frequency of Use</strong></td><td>Daily, generally twice per day for each user</td>
</tr><tr>
<td><strong>Triggers</strong></td><td>Daily sit rep needs to be completed</td>
</tr><tr>
<td><strong>Pre Conditions</strong></td><td>User has an active DoS account with appropriate permissions</td></tr><tr><td><strong>Post Conditions</strong></td><td><ol><li>Hospital sit rep has been updated</li><li>Users are able to view and compare capacity data for their hospital and those of other areas</li><li>Service profiling is correct</li></ol></td>
</tr><tr>
<td><strong>Main Course</strong></td><td><ol><li>User logs in</li><li>User navigates to the correct service profile</li><li>User saves changes</li><li>User completes a search based on geography and service type</li><li>User views summary data for services returned in the search</li><li>User navigates to reporting page</li><li>User selects region, grid and timeframes and exports required data</li></ol></td>
</tr><tr>
<td><strong>Alternate Course</strong></td><td>n/a</td></tr><tr><td><strong>Exception</strong></td><td>n/a
</td>
</tr></tbody></table>