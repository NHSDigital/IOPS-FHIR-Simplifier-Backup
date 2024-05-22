# {{page-title}}


## Searching for a healthcare service

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

### Workflow
{{render:Wokflow Diagrams-Searching for Healthcare Service.jpg}}

### System Interactions
<plantuml>
@startuml
title Locating a Healthcare Service
actor "Healthcare Worker"
participant "Directory of Services"
actor Patient

"Healthcare Worker" -> "Directory of Services": Access DoS
activate "Directory of Services"
"Directory of Services" --> "Healthcare Worker": Secure access provided
"Healthcare Worker" -> "Directory of Services": Search for relevant services
"Directory of Services" --> "Healthcare Worker": Return list of services
Deactivate "Directory of Services"
"Healthcare Worker" -> Patient: Provides list of relevant services
@enduml
</plantuml>



