---
topic: Library-Profiles
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

<a href="https://hl7.org/fhir/R4/profiling.html" class="external">Further information from HL7 relating to profiling is available</a>.

</div>

<div class="tab">
<button class="tablinks active" onclick="openTab(event, 'Narrative')">Narrative</button>
<button class="tablinks" onclick="openTab(event, 'Alphabetical')">Alphabetical</button>
<button class="tablinks" onclick="openTab(event, 'Sprint')">By Sprint</button>
<button class="tablinks" onclick="openTab(event, 'Resource')">By Resource</button>
</div>

<div id="Narrative" class="tabcontent"  style="display:block">
<h3>Narrative Listing</h3>

<table title="Profile" class="assets">
<tr>
<th class="width25">Profile</th>
<th class="width10">Status</th>
<th class="width45">Description</th>
<th class="width10">C&TA Sprint</th>
</tr>
<tr>
<td>{{pagelink:Profile-AllergyIntolerance,text:UKCore-AllergyIntolerance}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the AllergyIntolerance resource for the minimal set of data to query and retrieve allergy information.</td>
<td>2</td>
</tr>
<tr>
<td>{{pagelink:Profile-Appointment,text:UKCore-Appointment}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Appointment resource for the minimal set of data to query and retrieve appointment information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-Composition,text:UKCore-Composition}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Composition resource to enable a generic and flexible approach to FHIR document structures.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-Condition,text:UKCore-Condition}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Condition resource for the minimal set of data to query and retrieve problems and health concerns information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-Consent,text:UKCore-Consent}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Consent resource for the minimal set of data to query and retrieve written or verbal agreements concerning authorised or restricted actions relating to healthcare.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Device,text:UKCore-Device}}</td>
<td>draft</td>
<td>Defines the UK Core constraints and extensions on the Device resource for the minimal set of data to query and retrieve information about a medical device.</td>
<td>*</td>
</tr>
<tr>
<td>{{pagelink:Profile-Device-BloodPressure,text:UKCore-Device-BloodPressure}}</td>
<td>draft</td>
<td>A profile derived from the draft UK Core Device profile to define the minimal set of data to query and retrieve information about a device used to monitor blood pressure.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-DiagnosticReport,text:UKCore-DiagnosticReport}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the DiagnosticReport resource for the minimal set of data to query and retrieve the findings of diagnostic tests.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific UK Core profile exists.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-DiagnosticReport-Lab,text:UKCore-DiagnosticReport-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core DiagnosticReport profile to define the minimal set of data to query and retrieve the findings of laboratory tests.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Encounter,text:UKCore-Encounter}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Encounter resource for the minimal set of data to query and retrieve encounter information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-EpisodeOfCare,text:UKCore-EpisodeOfCare}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the EpisodeOfCare resource for the minimal set of data to query and retrieve episode of care information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-FamilyMemberHistory,text:UKCore-FamilyMemberHistory}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the FamilyMemberHistory resource for the minimal set of data to query and retrieve information about health events and conditions for a person related to the patient relevant in the context of care.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Flag,text:UKCore-Flag}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Flag resource for the minimal set of data to query and retrieve flag information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-HealthcareService,text:UKCore-HealthcareService}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the HealthcareService resource for the minimal set of data to query and retrieve healthcare service information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-ImagingStudy,text:UKCore-ImagingStudy}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the ImagingStudy resource for the minimal set of data to query and retrieve content of DICOM imaging studies.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Immunization,text:UKCore-Immunization}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Immunization resource for the minimal set of data to query and retrieve an individual's immunisation information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-List,text:UKCore-List}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the List resource for the minimal set of data to query and retrieve a list of information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Location,text:UKCore-Location}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Location resource for the minimal set of data to query and retrieve location information</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Medication,text:UKCore-Medication}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Medication resource for the minimal set of data to query and retrieve medication information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationAdministration,text:UKCore-MedicationAdministration}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationAdministration resource for the minimal set of data to query and retrieve medication administration information</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationDispense,text:UKCore-MedicationDispense}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationDispense resource for the minimal set of data to query and retrieve dispensed medication information.
</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationRequest,text:UKCore-MedicationRequest}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationRequest resource for the minimal set of data to query and retrieve prescription information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MedicationStatement,text:UKCore-MedicationStatement}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MedicationStatement resource for the minimal set of data to query and retrieve medication statement information.</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Profile-MessageHeader,text:UKCore-MessageHeader}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the MessageHeader resource for the minimal set of data to be present in a message header.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation,text:UKCore-Observation}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Observation resource for the minimal set of data to query and retrieve information of measurements and simple assertions made about an individual, device or other subject.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific derived profile exists.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-ACVPU,text:UKCore-Observation-ACVPU}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's level of consciousness.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-AlcoholConsumption,text:UKCore-Observation-AlcoholConsumption}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's alcohol consumption.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-AverageBloodPressure,text:UKCore-Observation-AverageBloodPressure}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's average blood pressure over a specific time period.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-BloodGlucose,text:UKCore-Observation-BloodGlucose}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's blood glucose level.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-EarlyWarningTotalScore,text:UKCore-Observation-EarlyWarningTotalScore}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's Early Warning Score, such as NEWS2.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-InspiredOxygen,text:UKCore-Observation-InspiredOxygen}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding whether a patient is breathing room air or is on oxygen.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-Lab,text:UKCore-Observation-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information of measurements and simple assertions made about an individual, device or other subject.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-Group,text:UKCore-Observation-LabGroup}}</td>
<td>active</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information for results borne from a single request panel, or profile.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-TobaccoConsumption,text:UKCore-Observation-TobaccoConsumption}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information regarding a patient's tobacco consumption.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation profile to define the minimal set of data to query and retrieve information of a patient's Vital Signs measurements, in order to be FHIR compliant with the base "Vital Signs" guidance.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific derived profile exists.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-BloodPressure,text:UKCore-Observation-VitalSigns-BloodPressure}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a single instance of a patient's blood pressure.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-BMI,text:UKCore-Observation-VitalSigns-BMI}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's body mass index.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-BodyHeight,text:UKCore-Observation-VitalSigns-BodyHeight}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's height.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-BodyTemperature,text:UKCore-Observation-VitalSigns-BodyTemperature}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's temperature.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-BodyWeight,text:UKCore-Observation-VitalSigns-BodyWeight}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's weight.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-HeadCircumference,text:UKCore-Observation-VitalSigns-HeadCircumference}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's head circumference.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-HeartRate,text:UKCore-Observation-VitalSigns-HeartRate}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's heart rate.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-OxygenSaturation,text:UKCore-Observation-VitalSigns-OxygenSaturation}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's level of oxygen saturation in their blood.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-Observation-VitalSigns-RespirationRate,text:UKCore-Observation-VitalSigns-RespirationRate}}</td>
<td>draft</td>
<td>A profile derived from the UK Core Observation Vital Signs profile to define the minimal set of data to query and retrieve information regarding a patient's breathing rate.</td>
<td>7</td>
</tr>
<tr>
<td>{{pagelink:Profile-OperationOutcome,text:UKCore-OperationOutcome}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the OperationOutcome resource for the minimal set of data to query and retrieve information about the outcome of an attempted system operation.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Organization,text:UKCore-Organization}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Organization resource for the minimal set of data to query and retrieve organisation information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Patient,text:UKCore-Patient}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Patient resource for the minimal set of data to query and retrieve an individual’s demographic information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Practitioner,text:UKCore-Practitioner}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Practitioner resource for the minimal set of data to query and retrieve practitioner information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-PractitionerRole,text:UKCore-PractitionerRole}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the PractitionerRole resource for the minimal set of data to query and retrieve practitioner role information.</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Profile-Procedure,text:UKCore-Procedure}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Procedure resource for the minimal set of data to query and retrieve the patient’s procedure information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Questionnaire,text:UKCore-Questionnaire}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Questionnaire resource for the minimal set of data to query and retrieve questionnaire information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-QuestionnaireResponse,text:UKCore-QuestionnaireResponse}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the QuestionnaireResponse resource for the minimal set of data to query and retrieve a complete or partial list of answers to a set of questions completed when responding to a questionnaire.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-RelatedPerson,text:UKCore-RelatedPerson}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the RelatedPerson resource for the minimal set of data to query and retrieve related person information.</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Profile-Schedule,text:UKCore-Schedule}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Schedule resource for the minimal set of data to query and retrieve schedule information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the ServiceRequest resource for the minimal set of data to query and retrieve service request information.<br>
<b>Note:</b> This profile SHALL NOT be used where a more specific UK Core profile exists.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-ServiceRequest-Lab,text:UKCore-ServiceRequest-Lab}}</td>
<td>active</td>
<td>A profile derived from the UK Core ServiceRequest profile to define the minimal set of data to query and retrieve the request for laboratory tests/td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Slot,text:UKCore-Slot}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Slot resource for the minimal set of data to query and retrieve slot information.</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Profile-Specimen,text:UKCore-Specimen}}</td>
<td>active</td>
<td>Defines the UK Core constraints and extensions on the Specimen resource for the minimal set of data to query and retrieve information regarding samples used for analysis.</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Profile-Task,text:UKCore-Task}}</td>
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
<li>{{pagelink:Profile-AllergyIntolerance,text:UKCore-AllergyIntolerance}}</li>
<li>{{pagelink:Profile-Appointment,text:UKCore-Appointment}}</li>
<li>{{pagelink:Profile-Composition,text:UKCore-Composition}}</li>
<li>{{pagelink:Profile-Condition,text:UKCore-Condition}}</li>
<li>{{pagelink:Profile-Consent,text:UKCore-Consent}}</li>
<li>{{pagelink:Profile-Device,text:UKCore-Device}}</li>
<li>{{pagelink:Profile-Device-BloodPressure,text:UKCore-Device-BloodPressure}}</li>
<li>{{pagelink:Profile-DiagnosticReport,text:UKCore-DiagnosticReport}}</li>
<li>{{pagelink:Profile-DiagnosticReport-Lab,text:UKCore-DiagnosticReport-Lab}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>E-L:</b></p>
<ul>
<li>{{pagelink:Profile-Encounter,text:UKCore-Encounter}}</li>
<li>{{pagelink:Profile-EpisodeOfCare,text:UKCore-EpisodeOfCare}}</li>
<li>{{pagelink:Profile-FamilyMemberHistory,text:UKCore-FamilyMemberHistory}}</li>
<li>{{pagelink:Profile-Flag,text:UKCore-Flag}}</li>
<li>{{pagelink:Profile-HealthcareService,text:UKCore-HealthcareService}}</li>
<li>{{pagelink:Profile-ImagingStudy,text:UKCore-ImagingStudy}}</li>
<li>{{pagelink:Profile-Immunization,text:UKCore-Immunization}}</li>
<li>{{pagelink:Profile-List,text:UKCore-List}}</li>
<li>{{pagelink:Profile-Location,text:UKCore-Location}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>M-P:</b></p>
<ul>
<li>{{pagelink:Profile-Medication,text:UKCore-Medication}}</li>
<li>{{pagelink:Profile-MedicationAdministration,text:UKCore-MedicationAdministration}}</li>
<li>{{pagelink:Profile-MedicationDispense,text:UKCore-MedicationDispense}}</li>
<li>{{pagelink:Profile-MedicationRequest,text:UKCore-MedicationRequest}}</li>
<li>{{pagelink:Profile-MedicationStatement,text:UKCore-MedicationStatement}}</li>
<li>{{pagelink:Profile-MessageHeader,text:UKCore-MessageHeader}}</li>
<li>{{pagelink:Profile-Observation,text:UKCore-Observation}}</li>
<li>{{pagelink:Profile-Observation-ACVPU,text:UKCore-Observation-ACVPU}}</li>
<li>{{pagelink:Profile-Observation-AlcoholConsumption,text:UKCore-Observation-AlcoholConsumption}}</li>
<li>{{pagelink:Profile-Observation-AverageBloodPressure,text:UKCore-Observation-AverageBloodPressure}}</li>
<li>{{pagelink:Profile-Observation-BloodGlucose,text:UKCore-Observation-BloodGlucose}}</li>
<li>{{pagelink:Profile-Observation-EarlyWarningTotalScore,text:UKCore-Observation-EarlyWarningTotalScore}}</li>
<li>{{pagelink:Profile-Observation-InspiredOxygen,text:UKCore-Observation-InspiredOxygen}}</li>
<li>{{pagelink:Profile-Observation-Lab,text:UKCore-Observation-Lab}}</li>
<li>{{pagelink:Profile-Observation-Group,text:UKCore-Observation-LabGroup}}</li>
<li>{{pagelink:Profile-Observation-TobaccoConsumption,text:UKCore-Observation-TobaccoConsumption}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BloodPressure,text:UKCore-Observation-VitalSigns-BloodPressure}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BMI,text:UKCore-Observation-VitalSigns-BMI}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyHeight,text:UKCore-Observation-VitalSigns-BodyHeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyTemperature,text:UKCore-Observation-VitalSigns-BodyTemperature}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyWeight,text:UKCore-Observation-VitalSigns-BodyWeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeadCircumference,text:UKCore-Observation-VitalSigns-HeadCircumference}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeartRate,text:UKCore-Observation-VitalSigns-HeartRate}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-OxygenSaturation,text:UKCore-Observation-VitalSigns-OxygenSaturation}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-RespirationRate,text:UKCore-Observation-VitalSigns-RespirationRate}}</li>
<li>{{pagelink:Profile-OperationOutcome,text:UKCore-OperationOutcome}}</li>
<li>{{pagelink:Profile-Organization,text:UKCore-Organization}}</li>
<li>{{pagelink:Profile-Patient,text:UKCore-Patient}}</li>
<li>{{pagelink:Profile-Practitioner,text:UKCore-Practitioner}}</li>
<li>{{pagelink:Profile-PractitionerRole,text:UKCore-PractitionerRole}}</li>
<li>{{pagelink:Profile-Procedure,text:UKCore-Procedure}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>Q-Z:</b></p> 
<ul>  
<li>{{pagelink:Profile-Questionnaire,text:UKCore-Questionnaire}}</li>
<li>{{pagelink:Profile-QuestionnaireResponse,text:UKCore-QuestionnaireResponse}}</li>
<li>{{pagelink:Profile-RelatedPerson,text:UKCore-RelatedPerson}}</li>
<li>{{pagelink:Profile-Schedule,text:UKCore-Schedule}}</li>
<li>{{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}}</li>
<li>{{pagelink:Profile-ServiceRequest-Lab,text:UKCore-ServiceRequest-Lab}}</li>
<li>{{pagelink:Profile-Slot,text:UKCore-Slot}}</li>
<li>{{pagelink:Profile-Specimen,text:UKCore-Specimen}}</li>
<li>{{pagelink:Profile-Task,text:UKCore-Task}}</li>
</ul>
</td></tr>

</tbody></table>
</div>



<div id="Sprint" class="tabcontent">
<h3>By Sprint</h3>

<p><b>C&TA Sprint 1:</b></p>
<ul>
<li>{{pagelink:Profile-Location,text:UKCore-Location}}</li>
<li>{{pagelink:Profile-Organization,text:UKCore-Organization}}</li>
<li>{{pagelink:Profile-Patient,text:UKCore-Patient}}</li>
<li>{{pagelink:Profile-Practitioner,text:UKCore-Practitioner}}</li>
<li>{{pagelink:Profile-PractitionerRole,text:UKCore-PractitionerRole}}</li>
</ul>

<p><b>C&TA Sprint 2:</b></p>
<ul>
<li>{{pagelink:Profile-AllergyIntolerance,text:UKCore-AllergyIntolerance}}</li>
</ul>

<p><b>C&TA Sprint 3:</b></p>
<ul>
<li>{{pagelink:Profile-Immunization,text:UKCore-Immunization}}</li>
<li>{{pagelink:Profile-Medication,text:UKCore-Medication}}</li>
<li>{{pagelink:Profile-MedicationAdministration,text:UKCore-MedicationAdministration}}</li>
<li>{{pagelink:Profile-MedicationDispense,text:UKCore-MedicationDispense}}</li>
<li>{{pagelink:Profile-MedicationRequest,text:UKCore-MedicationRequest}}</li>
<li>{{pagelink:Profile-MedicationStatement,text:UKCore-MedicationStatement}}</li>
</ul>

<p><b>C&TA Sprint 4:</b></p>
<ul>
<li>{{pagelink:Profile-Encounter,text:UKCore-Encounter}}</li>
<li>{{pagelink:Profile-EpisodeOfCare,text:UKCore-EpisodeOfCare}}</li>
<li>{{pagelink:Profile-List,text:UKCore-List}}</li>
<li>{{pagelink:Profile-MessageHeader,text:UKCore-MessageHeader}}</li>
<li>{{pagelink:Profile-OperationOutcome,text:UKCore-OperationOutcome}}</li>
<li>{{pagelink:Profile-Procedure,text:UKCore-Procedure}}</li>
<li>{{pagelink:Profile-RelatedPerson,text:UKCore-RelatedPerson}}</li>
</ul>

<p><b>C&TA Sprint 5:</b></p>
<ul>
<li>{{pagelink:Profile-Appointment,text:UKCore-Appointment}}</li>
<li>{{pagelink:Profile-Composition,text:UKCore-Composition}}</li>
<li>{{pagelink:Profile-Condition,text:UKCore-Condition}}</li>
<li>{{pagelink:Profile-Flag,text:UKCore-Flag}}</li>
<li>{{pagelink:Profile-HealthcareService,text:UKCore-HealthcareService}}</li>
<li>{{pagelink:Profile-QuestionnaireResponse,text:UKCore-QuestionnaireResponse}}</li>
<li>{{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}}</li>
<li>{{pagelink:Profile-Schedule,text:UKCore-Schedule}}</li>
<li>{{pagelink:Profile-Slot,text:UKCore-Slot}}</li>
<li>{{pagelink:Profile-Task,text:UKCore-Task}}</li>
</ul>

<p><b>C&TA Sprint 6:</b></p>
<ul>
<li>{{pagelink:Profile-Consent,text:UKCore-Consent}}</li>
<li>{{pagelink:Profile-DiagnosticReport,text:UKCore-DiagnosticReport}}</li>
<li>{{pagelink:Profile-DiagnosticReport-Lab,text:UKCore-DiagnosticReport-Lab}}</li>
<li>{{pagelink:Profile-FamilyMemberHistory,text:UKCore-FamilyMemberHistory}}</li>
<li>{{pagelink:Profile-ImagingStudy,text:UKCore-ImagingStudy}}</li>
<li>{{pagelink:Profile-Observation,text:UKCore-Observation}}</li>
<li>{{pagelink:Profile-Observation-Lab,text:UKCore-Observation-Lab}}</li>
<li>{{pagelink:Profile-Observation-Group,text:UKCore-Observation-LabGroup}}</li>
<li>{{pagelink:Profile-ServiceRequest-Lab,text:UKCore-ServiceRequest-Lab}}</li>
<li>{{pagelink:Profile-Specimen,text:UKCore-Specimen}}</li>
</ul>

<p><b>C&TA Sprint 7:</b></p>
<ul>
<li>{{pagelink:Profile-Device-BloodPressure,text:UKCore-Device-BloodPressure}}</li>
<li>{{pagelink:Profile-Observation-ACVPU,text:UKCore-Observation-ACVPU}}</li>
<li>{{pagelink:Profile-Observation-AlcoholConsumption,text:UKCore-Observation-AlcoholConsumption}}</li>
<li>{{pagelink:Profile-Observation-AverageBloodPressure,text:UKCore-Observation-AverageBloodPressure}}</li>
<li>{{pagelink:Profile-Observation-BloodGlucose,text:UKCore-Observation-BloodGlucose}}</li>
<li>{{pagelink:Profile-Observation-EarlyWarningTotalScore,text:UKCore-Observation-EarlyWarningTotalScore}}</li>
<li>{{pagelink:Profile-Observation-InspiredOxygen,text:UKCore-Observation-InspiredOxygen}}</li>
<li>{{pagelink:Profile-Observation-TobaccoConsumption,text:UKCore-Observation-TobaccoConsumption}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BloodPressure,text:UKCore-Observation-VitalSigns-BloodPressure}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BMI,text:UKCore-Observation-VitalSigns-BMI}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyHeight,text:UKCore-Observation-VitalSigns-BodyHeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyTemperature,text:UKCore-Observation-VitalSigns-BodyTemperature}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyWeight,text:UKCore-Observation-VitalSigns-BodyWeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeadCircumference,text:UKCore-Observation-VitalSigns-HeadCircumference}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeartRate,text:UKCore-Observation-VitalSigns-HeartRate}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-OxygenSaturation,text:UKCore-Observation-VitalSigns-OxygenSaturation}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-RespirationRate,text:UKCore-Observation-VitalSigns-RespirationRate}}</li>
</ul>

<p><b>Draft:</b></p>
<ul>
<li>{{pagelink:Profile-Device,text:UKCore-Device}}</li>
</ul>
</div>

<div id="Resource" class="tabcontent">
<h3>By Resource</h3>

<p><b>AllergyIntolerance:</b></p>
<ul>
<li>{{pagelink:Profile-AllergyIntolerance,text:UKCore-AllergyIntolerance}}</li>
</ul>
<p><b>Appointment:</b></p>
<ul>
<li>{{pagelink:Profile-Appointment,text:UKCore-Appointment}}</li>
</ul>
<p><b>Composition:</b></p>
<ul>
<li>{{pagelink:Profile-Composition,text:UKCore-Composition}}</li>
</ul>
<p><b>Condition:</b></p>
<ul>
<li>{{pagelink:Profile-Condition,text:UKCore-Condition}}</li>
</ul>
<p><b>Consent:</b></p>
<ul>
<li>{{pagelink:Profile-Consent,text:UKCore-Consent}}</li>
</ul>
<p><b>Device:</b></p>
<ul>
<li>{{pagelink:Profile-Device,text:UKCore-Device}}</li>
<li>{{pagelink:Profile-Device-BloodPressure,text:UKCore-Device-BloodPressure}}</li>
</ul>
<p><b>DiagnosticReport:</b></p>
<ul>
<li>{{pagelink:Profile-DiagnosticReport,text:UKCore-DiagnosticReport}}</li>
<li>{{pagelink:Profile-DiagnosticReport-Lab,text:UKCore-DiagnosticReport-Lab}}</li>
</ul>
<p><b>Encounter:</b></p>
<ul>
<li>{{pagelink:Profile-Encounter,text:UKCore-Encounter}}</li>
</ul>
<p><b>EpisodeOfCare:</b></p>
<ul>
<li>{{pagelink:Profile-EpisodeOfCare,text:UKCore-EpisodeOfCare}}</li>
</ul>
<p><b>FamilyMemberHistory:</b></p>
<ul>
<li>{{pagelink:Profile-FamilyMemberHistory,text:UKCore-FamilyMemberHistory}}</li>
</ul>
<p><b>Flag:</b></p>
<ul>
<li>{{pagelink:Profile-Flag,text:UKCore-Flag}}</li>
</ul>
<p><b>HealthcareService:</b></p>
<ul>
<li>{{pagelink:Profile-HealthcareService,text:UKCore-HealthcareService}}</li>
</ul>
<p><b>ImagingStudy:</b></p>
<ul>
<li>{{pagelink:Profile-ImagingStudy,text:UKCore-ImagingStudy}}</li>
</ul>
<p><b>Immunization:</b></p>
<ul>
<li>{{pagelink:Profile-Immunization,text:UKCore-Immunization}}</li>
</ul>
<p><b>List:</b></p>
<ul>
<li>{{pagelink:Profile-List,text:UKCore-List}}</li>
</ul>
<p><b>Location:</b></p>
<ul>
<li>{{pagelink:Profile-Location,text:UKCore-Location}}</li>
</ul>


<p><b>Medication:</b></p>
<ul>
<li>{{pagelink:Profile-Medication,text:UKCore-Medication}}</li>
</ul>
<p><b>MedicationAdministration:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationAdministration,text:UKCore-MedicationAdministration}}</li>
</ul>
<p><b>MedicationDispense:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationDispense,text:UKCore-MedicationDispense}}</li>
</ul>
<p><b>MedicationRequest:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationRequest,text:UKCore-MedicationRequest}}</li>
</ul>
<p><b>MedicationStatement:</b></p>
<ul>
<li>{{pagelink:Profile-MedicationStatement,text:UKCore-MedicationStatement}}</li>
</ul>
<p><b>MessageHeader:</b></p>
<ul>
<li>{{pagelink:Profile-MessageHeader,text:UKCore-MessageHeader}}</li>
</ul>

<p><b>Observation:</b></p>
<ul>
<li>{{pagelink:Profile-Observation,text:UKCore-Observation}}</li>
<li>{{pagelink:Profile-Observation-ACVPU,text:UKCore-Observation-ACVPU}}</li>
<li>{{pagelink:Profile-Observation-AlcoholConsumption,text:UKCore-Observation-AlcoholConsumption}}</li>
<li>{{pagelink:Profile-Observation-AverageBloodPressure,text:UKCore-Observation-AverageBloodPressure}}</li>
<li>{{pagelink:Profile-Observation-BloodGlucose,text:UKCore-Observation-BloodGlucose}}</li>
<li>{{pagelink:Profile-Observation-EarlyWarningTotalScore,text:UKCore-Observation-EarlyWarningTotalScore}}</li>
<li>{{pagelink:Profile-Observation-InspiredOxygen,text:UKCore-Observation-InspiredOxygen}}</li>
<li>{{pagelink:Profile-Observation-Lab,text:UKCore-Observation-Lab}}</li>
<li>{{pagelink:Profile-Observation-Group,text:UKCore-Observation-LabGroup}}</li>
<li>{{pagelink:Profile-Observation-TobaccoConsumption,text:UKCore-Observation-TobaccoConsumption}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BloodPressure,text:UKCore-Observation-VitalSigns-BloodPressure}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BMI,text:UKCore-Observation-VitalSigns-BMI}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyHeight,text:UKCore-Observation-VitalSigns-BodyHeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyTemperature,text:UKCore-Observation-VitalSigns-BodyTemperature}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-BodyWeight,text:UKCore-Observation-VitalSigns-BodyWeight}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeadCircumference,text:UKCore-Observation-VitalSigns-HeadCircumference}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-HeartRate,text:UKCore-Observation-VitalSigns-HeartRate}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-OxygenSaturation,text:UKCore-Observation-VitalSigns-OxygenSaturation}}</li>
<li>{{pagelink:Profile-Observation-VitalSigns-RespirationRate,text:UKCore-Observation-VitalSigns-RespirationRate}}</li>
</ul>

<p><b>OperationOutcome:</b></p>
<ul>
<li>{{pagelink:Profile-OperationOutcome,text:UKCore-OperationOutcome}}</li>
</ul>
<p><b>Organization:</b></p>
<ul>
<li>{{pagelink:Profile-Organization,text:UKCore-Organization}}</li>
</ul>
<p><b>Patient:</b></p>
<ul>
<li>{{pagelink:Profile-Patient,text:UKCore-Patient}}</li>
</ul>
<p><b>Practitioner:</b></p>
<ul>
<li>{{pagelink:Profile-Practitioner,text:UKCore-Practitioner}}</li>
</ul>
<p><b>PractitionerRole:</b></p>
<ul>
<li>{{pagelink:Profile-PractitionerRole,text:UKCore-PractitionerRole}}</li>
</ul>
<p><b>Procedure:</b></p>
<ul>
<li>{{pagelink:Profile-Procedure,text:UKCore-Procedure}}</li>
</ul>

<p><b>Questionnaire:</b></p>
<ul>
<li>{{pagelink:Profile-Questionnaire,text:UKCore-Questionnaire}}</li>
</ul>
<p><b>QuestionnaireResponse:</b></p>
<ul>
<li>{{pagelink:Profile-QuestionnaireResponse,text:UKCore-QuestionnaireResponse}}</li>
</ul>
<p><b>RelatedPerson:</b></p>
<ul>
<li>{{pagelink:Profile-RelatedPerson,text:UKCore-RelatedPerson}}</li>
</ul>
<p><b>Schedule:</b></p>
<ul>
<li>{{pagelink:Profile-Schedule,text:UKCore-Schedule}}</li>
</ul>
<p><b>ServiceRequest:</b></p>
<ul>
<li>{{pagelink:Profile-ServiceRequest,text:UKCore-ServiceRequest}}</li>
<li>{{pagelink:Profile-ServiceRequest-Lab,text:UKCore-ServiceRequest-Lab}}</li>
</ul>
<p><b>Slot:</b></p>
<ul>
<li>{{pagelink:Profile-Slot,text:UKCore-Slot}}</li>
</ul>
<p><b>Specimen:</b></p>
<ul>
<li>{{pagelink:Profile-Specimen,text:UKCore-Specimen}}</li>
</ul>
<p><b>Task:</b></p>
<ul>
<li>{{pagelink:Profile-Task,text:UKCore-Task}}</li>
</ul>

</div>


<br><br>
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> {{pagelink:Profile-Device}} is a draft Profile. It has not undergone a Clinical & Technical Assurance sprint, and is included here for comparison usage.
</div>
