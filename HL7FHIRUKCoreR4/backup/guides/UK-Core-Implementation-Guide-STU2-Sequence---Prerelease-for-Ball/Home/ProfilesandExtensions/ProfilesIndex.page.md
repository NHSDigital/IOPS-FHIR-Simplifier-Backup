---
topic: Library-Profiles-32647
---
## Profiles

This index contains all the profiles Clinically and Technically Assured for use with UK Core. 

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Important</h4>

The Profiles are rendered in several formats: 
<ul>
<li><b>Snapshot:</b> a fully calculated form of the structure that is not dependent on any other structure</li>
<li><b>Differential:</b> this describes only the differences that the Profile makes relative to the structure definition (FHIR resource or profile) they constrain</li> 
<li><b>Hybrid:</b> a hybrid view of the snapshot and differential views, with the differences highlighted</li>
<li><b>Table:</b> a differential view of the profile, rendered in a tabular format</li>
<li><b>XML:</b> a differential view of the profile, rendered in XML format</li>
<li><b>JSON:</b> a differential view of the profile, rendered in JSON format</li> 
</ul>
<br>

[Further information from HL7 relating to profiling is available](http://hl7.org/fhir/R4/profiling.html).

</div>

<div class="tab">
<button class="tablinks active" onclick="openTab(event, 'Narrative')">Narrative</button>
<button class="tablinks" onclick="openTab(event, 'Alphabetical')">Alphabetical</button>
<button class="tablinks" onclick="openTab(event, 'Sprint')">By Sprint</button>
<button class="tablinks" onclick="openTab(event, 'Resource')">By Resource</button>
</div>

<div id="Narrative" class="tabcontent"  style="display:block">
<h3>Narrative Listing</h3>

<table class="assets">
<tr>
<th width="25%">Profile</th>
<th width="10%">Status</th>
<th width="45%">Description</th>
<th width="10%">C&TA Sprint</th>
</tr>
<tr>
<td>{{pagelink:Profile-AllergyIntolerance-30748,text:UKCore-AllergyIntolerance}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the AllergyIntolerance resource for the minimal set of data to query and retrieve allergy information.</td>
<td>2</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Appointment-87479,text:UKCore-Appointment}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Appointment resource for the minimal set of data to query and retrieve appointment information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Composition-31483,text:UKCore-Composition}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Composition resource to enable a generic and flexible approach to FHIR document structures.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Condition-78787,text:UKCore-Condition}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Condition resource for the minimal set of data to query and retrieve problems and health concerns information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Consent-15646,text:UKCore-Consent}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Consent resource for the minimal set of data to query and retrieve written or verbal agreements concerning authorised or restricted actions relating to healthcare.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-DiagnosticReport-54417,text:UKCore-DiagnosticReport}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the DiagnosticReport resource for the minimal set of data to query and retrieve the findings of diagnostic tests.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific UK Core profile exists.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-DiagnosticReport-Lab-56818,text:UKCore-DiagnosticReport-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core DiagnosticReport profile to define the minimal set of data to query and retrieve the findings of laboratory tests.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Encounter-79976,text:UKCore-Encounter}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Encounter resource for the minimal set of data to query and retrieve encounter information.</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-EpisodeOfCare-32298,text:UKCore-EpisodeOfCare}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the EpisodeOfCare resource for the minimal set of data to query and retrieve episode of care information.</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-FamilyMemberHistory-69978,text:UKCore-FamilyMemberHistory}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the FamilyMemberHistory resource for the minimal set of data to query and retrieve information about health events and conditions for a person related to the patient relevant in the context of care.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Flag-45551,text:UKCore-Flag}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Flag resource for the minimal set of data to query and retrieve flag information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-HealthcareService-13702,text:UKCore-HealthcareService}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the HealthcareService resource for the minimal set of data to query and retrieve healthcare service information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-ImagingStudy-72492,text:UKCore-ImagingStudy}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the ImagingStudy resource for the minimal set of data to query and retrieve content of DICOM imaging studies.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Immunization-16790,text:UKCore-Immunization}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Immunization resource for the minimal set of data to query and retrieve an individual's immunisation information.</td>
<td>3</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-List-19037,text:UKCore-List}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the List resource for the minimal set of data to query and retrieve a list of information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Location-14324,text:UKCore-Location}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Location resource for the minimal set of data to query and retrieve location information</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Medication-73860,text:UKCore-Medication}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Medication resource for the minimal set of data to query and retrieve medication information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationAdministration-56616,text:UKCore-MedicationAdministration}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationAdministration resource for the minimal set of data to query and retrieve medication administration information</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationDispense-76932,text:UKCore-MedicationDispense}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationDispense resource for the minimal set of data to query and retrieve dispensed medication information.
</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationRequest-20572,text:UKCore-MedicationRequest}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationRequest resource for the minimal set of data to query and retrieve prescription information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationStatement-34649,text:UKCore-MedicationStatement}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationStatement resource for the minimal set of data to query and retrieve medication statement information.</td>
<td>3</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-MessageHeader-48618,text:UKCore-MessageHeader}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MessageHeader resource for the minimal set of data to be present in a message header.</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Observation-67521,text:UKCore-Observation}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Observation resource for the minimal set of data to query and retrieve information of measurements and simple assertions made about an individual, device or other subject.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific UK Core profile exists.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Observation-Lab-67452,text:UKCore-Observation-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information of measurements and simple assertions made about an individual, device or other subject.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Observation-Group-67431,text:UKCore-Observation-LabGroup}}</td>
<td>active</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information for results borne from a single request panel, or profile.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-OperationOutcome-83857,text:UKCore-OperationOutcome}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the OperationOutcome resource for the minimal set of data to query and retrieve information about the outcome of an attempted system operation.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Organization-94604,text:UKCore-Organization}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Organization resource for the minimal set of data to query and retrieve organisation information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Patient-88961,text:UKCore-Patient}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Patient resource for the minimal set of data to query and retrieve an individual’s demographic information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Practitioner-10758,text:UKCore-Practitioner}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Practitioner resource for the minimal set of data to query and retrieve practitioner information.</td>
<td>1</td>
</tr>
<tr >
<td>{{pagelink:Profile-PractitionerRole-55046,text:UKCore-PractitionerRole}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the PractitionerRole resource for the minimal set of data to query and retrieve practitioner role information.</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Procedure-10775,text:UKCore-Procedure}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Procedure resource for the minimal set of data to query and retrieve the patient’s procedure information.</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Questionnaire-47615,text:UKCore-Questionnaire}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Questionnaire resource for the minimal set of data to query and retrieve questionnaire information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-QuestionnaireResponse-37290,text:UKCore-QuestionnaireResponse}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the QuestionnaireResponse resource for the minimal set of data to query and retrieve a complete or partial list of answers to a set of questions completed when responding to a questionnaire.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-RelatedPerson-51006,text:UKCore-RelatedPerson}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the RelatedPerson resource for the minimal set of data to query and retrieve related person information.</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Schedule-96669,text:UKCore-Schedule}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Schedule resource for the minimal set of data to query and retrieve schedule information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-ServiceRequest-88746,text:UKCore-ServiceRequest}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the ServiceRequest resource for the minimal set of data to query and retrieve service request information.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific UK Core profile exists.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-ServiceRequest-Lab-37178,text:UKCore-ServiceRequest-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core ServiceRequest profile to define the minimal set of data to query and retrieve the request for laboratory tests/td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Slot-83549,text:UKCore-Slot}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Slot resource for the minimal set of data to query and retrieve slot information.</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Specimen-37178,text:UKCore-Specimen}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Specimen resource for the minimal set of data to query and retrieve information regarding samples used for analysis.</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Profile-Task-90615,text:UKCore-Task}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Task resource for the minimal set of data to query and retrieve task information.</td>
<td>5</td>
</tr>
</table>
</div>

<div id="Alphabetical" class="tabcontent">
<h3>Alphabetical Listing</h3>

<table width="100%">
<tbody>
<tr class="a-to-z"><td>
<p><b>A-D:</b></p>
<ul>
<li>{{pagelink:Profile-AllergyIntolerance-30748,text:UKCore-AllergyIntolerance}}</li>
<li class="balloted">{{pagelink:Profile-Appointment-87479,text:UKCore-Appointment}}</li>
<li class="balloted">{{pagelink:Profile-Composition-31483,text:UKCore-Composition}}</li>
<li class="balloted">{{pagelink:Profile-Condition-78787,text:UKCore-Condition}}</li>
<li class="balloted">{{pagelink:Profile-Consent-15646,text:UKCore-Consent}}</li>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-54417,text:UKCore-DiagnosticReport}}</li>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-Lab-56818,text:UKCore-DiagnosticReport-Lab}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>E-L:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Encounter-79976,text:UKCore-Encounter}}</li>
<li class="balloted">{{pagelink:Profile-EpisodeOfCare-32298,text:UKCore-EpisodeOfCare}}</li>
<li class="balloted">{{pagelink:Profile-FamilyMemberHistory-69978,text:UKCore-FamilyMemberHistory}}</li>
<li class="balloted">{{pagelink:Profile-Flag-45551,text:UKCore-Flag}}</li>
<li class="balloted">{{pagelink:Profile-HealthcareService-13702,text:UKCore-HealthcareService}}</li>
<li class="balloted">{{pagelink:Profile-ImagingStudy-72492,text:UKCore-ImagingStudy}}</li>
<li>{{pagelink:Profile-Immunization-16790,text:UKCore-Immunization}}</li>
<li class="balloted">{{pagelink:Profile-List-19037,text:UKCore-List}}</li>
<li>{{pagelink:Profile-Location-14324,text:UKCore-Location}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>M-P:</b></p>
<ul>
<li>{{pagelink:Profile-Medication-73860,text:UKCore-Medication}}</li>
<li>{{pagelink:Profile-MedicationAdministration-56616,text:UKCore-MedicationAdministration}}</li>
<li>{{pagelink:Profile-MedicationDispense-76932,text:UKCore-MedicationDispense}}</li>
<li>{{pagelink:Profile-MedicationRequest-20572,text:UKCore-MedicationRequest}}</li>
<li>{{pagelink:Profile-MedicationStatement-34649,text:UKCore-MedicationStatement}}</li>
<li class="balloted">{{pagelink:Profile-MessageHeader-48618,text:UKCore-MessageHeader}}</li>
<li class="balloted">{{pagelink:Profile-Observation-67521,text:UKCore-Observation}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Lab-67452,text:UKCore-Observation-Lab}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Group-67431,text:UKCore-Observation-LabGroup}}</li>
<li class="balloted">{{pagelink:Profile-OperationOutcome-83857,text:UKCore-OperationOutcome}}</li>
<li>{{pagelink:Profile-Organization-94604,text:UKCore-Organization}}</li>
<li>{{pagelink:Profile-Patient-88961,text:UKCore-Patient}}</li>
<li>{{pagelink:Profile-Practitioner-10758,text:UKCore-Practitioner}}</li>
<li>{{pagelink:Profile-PractitionerRole-55046,text:UKCore-PractitionerRole}}</li>
<li class="balloted">{{pagelink:Profile-Procedure-10775,text:UKCore-Procedure}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>Q-Z:</b></p> 
<ul>  
<li class="balloted">{{pagelink:Profile-Questionnaire-47615,text:UKCore-Questionnaire}}</li>
<li class="balloted">{{pagelink:Profile-QuestionnaireResponse-37290,text:UKCore-QuestionnaireResponse}}</li>
<li class="balloted">{{pagelink:Profile-RelatedPerson-51006,text:UKCore-RelatedPerson}}</li>
<li class="balloted">{{pagelink:Profile-Schedule-96669,text:UKCore-Schedule}}</li>
<li class="balloted">{{pagelink:Profile-ServiceRequest-88746,text:UKCore-ServiceRequest}}</li>
<li class="balloted">{{pagelink:Profile-ServiceRequest-Lab-37178,text:UKCore-ServiceRequest-Lab}}</li>
<li class="balloted">{{pagelink:Profile-Slot-83549,text:UKCore-Slot}}</li>
<li class="balloted">{{pagelink:Profile-Specimen-37178,text:UKCore-Specimen}}</li>
<li class="balloted">{{pagelink:Profile-Task-90615,text:UKCore-Task}}</li>
</ul>
</td></tr>

</tbody></table>
</div>



<div id="Sprint" class="tabcontent">
<h3>By Sprint</h3>

<p><b>C&TA Sprint 1:</b></p>
<ul>
<li>{{pagelink:Profile-Location-14324,text:UKCore-Location}}</li>
<li>{{pagelink:Profile-Organization-94604,text:UKCore-Organization}}</li>
<li>{{pagelink:Profile-Patient-88961,text:UKCore-Patient}}</li>
<li>{{pagelink:Profile-Practitioner-10758,text:UKCore-Practitioner}}</li>
<li>{{pagelink:Profile-PractitionerRole-55046,text:UKCore-PractitionerRole}}</li>
</ul>

<p><b>C&TA Sprint 2:</b></p>
<ul>
<li>{{pagelink:Profile-AllergyIntolerance-30748,text:UKCore-AllergyIntolerance}}</li>
</ul>

<p><b>C&TA Sprint 3:</b></p>
<ul>
<li>{{pagelink:Profile-Immunization-16790,text:UKCore-Immunization}}</li>
<li>{{pagelink:Profile-Medication-73860,text:UKCore-Medication}}</li>
<li>{{pagelink:Profile-MedicationAdministration-56616,text:UKCore-MedicationAdministration}}</li>
<li>{{pagelink:Profile-MedicationDispense-76932,text:UKCore-MedicationDispense}}</li>
<li>{{pagelink:Profile-MedicationRequest-20572,text:UKCore-MedicationRequest}}</li>
<li>{{pagelink:Profile-MedicationStatement-34649,text:UKCore-MedicationStatement}}</li>
</ul>

<p><b>C&TA Sprint 4:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Encounter-79976,text:UKCore-Encounter}}</li>
<li class="balloted">{{pagelink:Profile-EpisodeOfCare-32298,text:UKCore-EpisodeOfCare}}</li>
<li class="balloted">{{pagelink:Profile-List-19037,text:UKCore-List}}</li>
<li class="balloted">{{pagelink:Profile-MessageHeader-48618,text:UKCore-MessageHeader}}</li>
<li class="balloted">{{pagelink:Profile-OperationOutcome-83857,text:UKCore-OperationOutcome}}</li>
<li class="balloted">{{pagelink:Profile-Procedure-10775,text:UKCore-Procedure}}</li>
<li class="balloted">{{pagelink:Profile-RelatedPerson-51006,text:UKCore-RelatedPerson}}</li>
</ul>

<p><b>C&TA Sprint 5:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Appointment-87479,text:UKCore-Appointment}}</li>
<li class="balloted">{{pagelink:Profile-Composition-31483,text:UKCore-Composition}}</li>
<li class="balloted">{{pagelink:Profile-Condition-78787,text:UKCore-Condition}}</li>
<li class="balloted">{{pagelink:Profile-Flag-45551,text:UKCore-Flag}}</li>
<li class="balloted">{{pagelink:Profile-HealthcareService-13702,text:UKCore-HealthcareService}}</li>
<li class="balloted">{{pagelink:Profile-Questionnaire-47615,text:UKCore-Questionnaire}}</li>
<li class="balloted">{{pagelink:Profile-QuestionnaireResponse-37290,text:UKCore-QuestionnaireResponse}}</li>
<li class="balloted">{{pagelink:Profile-ServiceRequest-88746,text:UKCore-ServiceRequest}}</li>
<li class="balloted">{{pagelink:Profile-Schedule-96669,text:UKCore-Schedule}}</li>
<li class="balloted">{{pagelink:Profile-Slot-83549,text:UKCore-Slot}}</li>
<li class="balloted">{{pagelink:Profile-Task-90615,text:UKCore-Task}}</li>
</ul>

<p><b>C&TA Sprint 6:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Consent-15646,text:UKCore-Consent}}</li>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-54417,text:UKCore-DiagnosticReport}}</li>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-Lab-56818,text:UKCore-DiagnosticReport-Lab}}</li>
<li class="balloted">{{pagelink:Profile-FamilyMemberHistory-69978,text:UKCore-FamilyMemberHistory}}</li>
<li class="balloted">{{pagelink:Profile-ImagingStudy-72492,text:UKCore-ImagingStudy}}</li>
<li class="balloted">{{pagelink:Profile-Observation-67521,text:UKCore-Observation}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Lab-67452,text:UKCore-Observation-Lab}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Group-67431,text:UKCore-Observation-LabGroup}}</li>
<li class="balloted">{{pagelink:Profile-ServiceRequest-Lab-37178,text:UKCore-ServiceRequest-Lab}}</li>
<li class="balloted">{{pagelink:Profile-Specimen-37178,text:UKCore-Specimen}}</li>
</ul>

</div>

<div id="Resource" class="tabcontent">
<h3>By Resource</h3>

<p><b>AllergyIntolerance:</b></p>
<ul>
<li>{{pagelink:Profile-AllergyIntolerance-30748,text:UKCore-AllergyIntolerance}}</li>
</ul>
<p><b>Appointment:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Appointment-87479,text:UKCore-Appointment}}</li>
</ul>
<p><b>Composition:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Composition-31483,text:UKCore-Composition}}</li>
</ul>
<p><b>Condition:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Condition-78787,text:UKCore-Condition}}</li>
</ul>
<p><b>Consent:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Consent-15646,text:UKCore-Consent}}</li>
</ul>
<p><b>DiagnosticReport:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-54417,text:UKCore-DiagnosticReport}}</li>
<li class="balloted">{{pagelink:Profile-DiagnosticReport-Lab-56818,text:UKCore-DiagnosticReport-Lab}}</li>
</ul>


<p><b>Encounter:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Encounter-79976,text:UKCore-Encounter}}</li>
</ul>
<p><b>EpisodeOfCare:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-EpisodeOfCare-32298,text:UKCore-EpisodeOfCare}}</li>
</ul>
<p><b>FamilyMemberHistory:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-FamilyMemberHistory-69978,text:UKCore-FamilyMemberHistory}}</li>
</ul>
<p><b>Flag:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Flag-45551,text:UKCore-Flag}}</li>
</ul>
<p><b>HealthcareService:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-HealthcareService-13702,text:UKCore-HealthcareService}}</li>
</ul>
<p><b>ImagingStudy:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-ImagingStudy-72492,text:UKCore-ImagingStudy}}</li>
</ul>
<p><b>Immunization:</b></p>
<ul>
<li>{{pagelink:Profile-Immunization-16790,text:UKCore-Immunization}}</li>
</ul>
<p><b>List:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-List-19037,text:UKCore-List}}</li>
</ul>
<p><b>Location:</b></p>
<ul>
<li>{{pagelink:Profile-Location-14324,text:UKCore-Location}}</li>
</ul>


<p><b>Medication:</b></p>
<ul>
<li>{{pagelink:Profile-Medication-73860,text:UKCore-Medication}}</li>
</ul>
<p><b>MedicationAdministration:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationAdministration-56616,text:UKCore-MedicationAdministration}}</li>
</ul>
<p><b>MedicationDispense:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationDispense-76932,text:UKCore-MedicationDispense}}</li>
</ul>
<p><b>MedicationRequest:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationRequest-20572,text:UKCore-MedicationRequest}}</li>
</ul>
<p><b>MedicationStatement:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationStatement-34649,text:UKCore-MedicationStatement}}</li>
</ul>
<p><b>MessageHeader:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-MessageHeader-48618,text:UKCore-MessageHeader}}</li>
</ul>

<p><b>Observation:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Observation-67521,text:UKCore-Observation}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Lab-67452,text:UKCore-Observation-Lab}}</li>
<li class="balloted">{{pagelink:Profile-Observation-Group-67431,text:UKCore-Observation-LabGroup}}</li>
</ul>

<p><b>OperationOutcome:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-OperationOutcome-83857,text:UKCore-OperationOutcome}}</li>
</ul>
<p><b>Organization:</b></p>
<ul>
<li>{{pagelink:Profile-Organization-94604,text:UKCore-Organization}}</li>
</ul>
<p><b>Patient:</b></p>
<ul>
<li>{{pagelink:Profile-Patient-88961,text:UKCore-Patient}}</li>
</ul>
<p><b>Practitioner:</b></p>
<ul>
<li>{{pagelink:Profile-Practitioner-10758,text:UKCore-Practitioner}}</li>
</ul>
<p><b>PractitionerRole:</b></p>
<ul>
<li>{{pagelink:Profile-PractitionerRole-55046,text:UKCore-PractitionerRole}}</li>
</ul>
<p><b>Procedure:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Procedure-10775,text:UKCore-Procedure}}</li>
</ul>

<p><b>Questionnaire:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Questionnaire-47615,text:UKCore-Questionnaire}}</li>
</ul>
<p><b>QuestionnaireResponse:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-QuestionnaireResponse-37290,text:UKCore-QuestionnaireResponse}}</li>
</ul>
<p><b>RelatedPerson:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-RelatedPerson-51006,text:UKCore-RelatedPerson}}</li>
</ul>
<p><b>Schedule:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Schedule-96669,text:UKCore-Schedule}}</li>
</ul>
<p><b>ServiceRequest:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-ServiceRequest-88746,text:UKCore-ServiceRequest}}</li>
<li class="balloted">{{pagelink:Profile-ServiceRequest-Lab-37178,text:UKCore-ServiceRequest-Lab}}</li>
</ul>
<p><b>Slot:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Slot-83549,text:UKCore-Slot}}</li>
</ul>
<p><b>Specimen:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Specimen-37178,text:UKCore-Specimen}}</li>
</ul>
<p><b>Task:</b></p>
<ul>
<li class="balloted">{{pagelink:Profile-Task-90615,text:UKCore-Task}}</li>
</ul>

</div>
