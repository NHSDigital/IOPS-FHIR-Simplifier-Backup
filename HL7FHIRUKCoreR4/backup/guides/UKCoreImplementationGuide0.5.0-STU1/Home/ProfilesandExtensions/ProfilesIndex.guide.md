---
topic: Library-Profiles-d78076a0-90d5-4e11-8b6e-64697b0bcfd9
---
## Profiles

The UK Core Profiles have been assigned a maturity level similar to the maturity levels described in the FHIR standard. This is intended to indicate how stable the Profile is deemed to be, this is in addition to the publication status of the Profile  <a href="http://hl7.org/fhir/valueset-publication-status.html" target="_blank">HL7 FHIR statuses</a> of draft, active, retired and unknown.

<br/>
<table id="assets">
<tr>
<th width="10%">Maturity level</th>
<th width="90%">Definition</th>
</tr>
<tr>
<td>0</td>
<td>The Profile has been published on the current build. This Profile has had no formal review and therefore may have quality issues. It is published only to allow the review process to start</td>
</tr>
<tr>
<td>1</td>
<td>The Profile produces no warnings during the build process and has had a formal internal review by the UK Core development team</td>
</tr>
<tr>
<td>2</td>
<td>The Profile has been released for review to the UK FHIR community, any feedback received has been addressed as far as possible</td>
</tr>
<tr>
<td>3</td>	
<td>The Profile has been presented for inclusion in the Clinical and Technical Assurance process</td>
</tr>
<tr>
<td>4</td>
<td>The Profile has completed the Clinical and Technical Assurance process and the status has been changed to active</td>
</tr>
<tr>
<td>5</td>
<td>The Profile has been presented for inclusion in the HL7 UK Ballot Process</td> 
</tr>
<tr> 
<td>6</td>
<td>The Profile has completed the HL7 UK Ballot process and is now deemed to be Normative</td>
</tr>
</table>
<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>
This Release 1 implementation guide only contains Profiles with a maturity level of 4 or more. Profiles that are at a earlier stage of development (maturity level of 0-2) are available in the <a href="https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment/home" target="_blank"> UK Core Implementation Guide Assets in Development</a><br/><br/>
The Profiles are rendered in several formats: 
<ul>
<li><b>Snapshot:</b> a fully calculated form of the structure that is not dependent on any other structure</li>
<li><b>Differential:</b> this describes only the differences that the Profile  makes relative to the structure definition (FHIR resource) they constrain</li> 
<li><b>Hybrid:</b> a hybrid view of the snapshot and differential views</li>
<li><b>Table:</b> a tabular view of the Profile  elements</li>
<li><b>XML:</b> a rendering of a XML view of the profile</li>
<li><b>JSON:</b> A rendering of a JSON view of the profile</li> 
</ul>
<br/>
<a href="http://hl7.org/fhir/profiling.html" target="_blank"> Further information from HL7 relating to profiling is available. </a>
</div>
<br/>

<table id="assets">
<tr>
<th width="25%">Profile</th>
<th width="10%">Status</th>
<th width="10%">Maturity</th>
<th width="45%">Description</th>
<th width="10%">C&TA Sprint</th>
</tr>

<tr>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the AllergyIntolerance resource for the minimal set of data to query and retrieve allergy information.</td>
<td>2</td>
</tr>

<tr>
<td>{{pagelink:Profile-Appointment-90f31814-417d-46fa-8ae3-bec132f819e8}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Appointment resource for the minimal set of data to query and retrieve appointment information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-Composition-d56239ce-28c2-4193-96e4-025156ca0908}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Composition resource to enable a generic and flexible approach to FHIR document structures.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Condition resource for the minimal set of data to query and retrieve problems and health concerns information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Encounter resource for the minimal set of data to query and retrieve encounter information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-EpisodeOfCare-8410fd46-fa56-4bf8-8db5-82e67587e005}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the EpisodeOfCare resource for the minimal set of data to query and retrieve episode of care information.</td>
<td>4</td>
</tr>

<tr>
<td>{{pagelink:Profile-Flag-fc2ab1d7-beb5-4245-a62a-c17b56c4768d}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Flag resource for the minimal set of data to query and retrieve flag information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-HealthcareService-83c4b098-a858-4717-b6b8-c1c101d5ea11}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the HealthcareService resource for the minimal set of data to query and retrieve healthcare service information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Immunization resource for the minimal set of data to query and retrieve an individuals immunisation information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the List resource for the minimal set of data to query and retrieve a list of information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Location-9738cf88-9ba3-4fc6-8efb-58b9583498f2}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Location resource for the minimal set of data to query and retrieve location information.</td>
<td>1</td>
</tr>

<tr>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Medication resource for the minimal set of data to query and retrieve medication information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the MedicationAdministration resource for the minimal set of data to query and retrieve medication administration information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the MedicationDispense resource for the minimal set of data to query and retrieve dispensed medication information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the MedicationRequest resource for the minimal set of data to query and retrieve prescription information.</td>
<td>3</td>
</tr>

<tr>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the MedicationStatement resource for the minimal set of data to query and retrieve medication statement information.</td>
<td>3</td>
</tr>

<tr>
<td>{{pagelink:Profile-MessageHeader-2af0a75b-3de6-42fa-8c05-03a0c1d142c5}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the MessageHeader resource for the minimal set of data to be present in a message header.</td>
<td>4</td>
</tr>

<tr >
<td>{{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Organization resource for the minimal set of data to query and retrieve organisation information.</td>
<td>1</td>
</tr>

<tr>
<td>{{pagelink:Profile-OperationOutcome-07a0844d-75f0-4abe-b99b-7597e8de31f3}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the OperationOutcome resource for the minimal set of data to query and retrieve information about the outcome of an attempted system operation.</td>
<td>4</td>
</tr>

<tr >
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Patient resource for the minimal set of data to query and retrieve an individual’s demographic information.</td>
<td>1</td>
</tr>

<tr >
<td>{{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the Practitioner resource for the minimal set of data to query and retrieve practitioner information.</td>
<td>1</td>
</tr>
<tr >
<td>{{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}</td>
<td>active</td>
<td>5</td>
<td>Defines the UK Core constraints and extensions on the PractitionerRole resource for the minimal set of data to query and retrieve practitioner role information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Procedure resource for the minimal set of data to query and retrieve the patient’s procedure information.</td>
<td>4</td>
</tr>

<tr>
<td>{{pagelink:Profile-Questionnaire-f28dde1a-853a-4d5b-85fb-d6a066c3023a}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Questionnaire resource for the minimal set of data to query and retrieve questionnaire information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-QuestionnaireResponse-8cef38c1-2b28-4293-b570-ebae1f73efb9}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the QuestionnaireResponse resource for the minimal set of data to query and retrieve a complete or partial list of answers to a set of questions completed when responding to a questionnaire.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the RelatedPerson resource for the minimal set of data to query and retrieve related person information.</td>
<td>4</td>
</tr>

<tr>
<td>{{pagelink:Profile-Schedule-c033e93c-abb1-4e8a-b322-eecf0bf6d797}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Schedule resource for the minimal set of data to query and retrieve schedule information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-ServiceRequest-6b7f601e-1517-4596-8a8e-0f8f40caa095}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the ServiceRequest resource for the minimal set of data to query and retrieve service request information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-Slot-a23e6342-f948-4c62-bc9e-330e2a82a20d}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Slot resource for the minimal set of data to query and retrieve slot information.</td>
<td>5</td>
</tr>

<tr>
<td>{{pagelink:Profile-Task-4d1cd248-6c85-46d1-bbba-8b6f64161e6d}}</td>
<td>active</td>
<td>4</td>
<td>Defines the UK Core constraints and extensions on the Task  resource for the minimal set of data to query and retrieve task information.</td>
<td>5</td>
</tr>

</table>

<br/>

