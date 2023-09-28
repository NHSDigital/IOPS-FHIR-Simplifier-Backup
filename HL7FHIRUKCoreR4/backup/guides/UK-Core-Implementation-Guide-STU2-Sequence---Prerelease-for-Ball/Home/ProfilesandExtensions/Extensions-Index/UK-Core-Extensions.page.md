---
topic: Library-Extensions-UKCore-82900
---
## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Important</h4>

The Extensions listed below have been defined as UK Core extensions. Also included in this library are some HL7 core-defined extensions which have been added to the UK Core profiles because they have been deemed to be "core" to UK FHIR data exchanges. These will have a page with guidance on usage in the UK and examples to illustrate usage. Note: implementers of UK Core MAY use any HL7 core-defined extension from the HL7 standard regardless of whether the extension is included in this implementation guide. The list of core-defined extensions in FHIR R4 is available in the [HL7 Core-defined Extension Registry](http://hl7.org/fhir/R4/extensibility-registry.html).

<br/>
<p>Implementers of the UK Core profiles MAY also create their own Extensions where required, but are encouraged to engage with the UK Core development process to get their extensions adopted into the UK Core for wider use by the UK FHIR Community.</p> 
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
<th>Extensions</th>
<th>Status</th>
<th>Context of Use</th>
<th>Related Profile</th>
<th>Modifier Extension</th>
<th>C&TA Sprint</th>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-AdditionalContact}}</td>
<td>active</td>
<td>ServiceRequest</td>
<td>{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-AddressKey}}</td>
<td>active</td>
<td>Address</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-AdmissionMethod}}</td>
<td>active</td>
<td>Encounter.hospitalization</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-AllergyIntoleranceEnd}}</td>
<td>active</td>
<td>AllergyIntolerance.<br>clinicalStatus</td>
<td>{{pagelink:Profile-AllergyIntolerance-30748}}</td>
<td>NO</td>
<td>2</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-AssociatedEncounter}}</td>
<td>active</td>
<td>FamilyMemberHistory</td>
<td>{{pagelink:Profile-FamilyMemberHistory-69978}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-BirthSex}}</td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-BodySiteReference}}</td>
<td>active</td>
<td>Specimen.collection.bodySite</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-BookingOrganization}}</td>
<td>active</td>
<td>Appointment</td>
<td>{{pagelink:Profile-Appointment-87479}}</td>
<td>NO</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-CareSettingType}}</td>
<td>active</td>
<td>Composition <br/>List  </td>
<td> {{pagelink:Profile-Composition-31483}} <br> 
{{pagelink:Profile-List-19037}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-CodingSCTDescDisplay}}</td>
<td>active</td>
<td>Coding</td>
<td>All clinical profiles that can use SNOMED CT. See the extension page for information about how this is used in profiles. </td>
<td>NO</td>
<td>2</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-ConditionEpisode}}</td>
<td>active</td>
<td>Condition</td>
<td>{{pagelink:Profile-Condition-78787}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-ContactPreference}}</td>
<td>active</td>
<td>Patient,<br>RelatedPerson</td>
<td> {{pagelink:Profile-Patient-88961}} <br> 
{{pagelink:Profile-RelatedPerson-51006}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-ContactRank}}</td>
<td>active</td>
<td>Patient.contact</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-Coverage}}</td>
<td>active</td>
<td>ServiceRequest</td>
<td>{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator}}</td>
<td>active</td>
<td>Patient.contact,<br>RelatedPerson</td>
<td>{{pagelink:Profile-Patient-88961}} <br> 
{{pagelink:Profile-RelatedPerson-51006}}</td>
<td>NO</td>
<td>1</td> 
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-DeathNotificationStatus}}</td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-DeliveryChannel}}</td>
<td>active</td>
<td>Appointment, Slot</td>
<td>{{pagelink:Profile-Appointment-87479}}<br>
{{pagelink:Profile-Slot-83549}}</td>
<td>NO</td>
<td>5</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-DeviceReference}}</td>
<td>active</td>
<td>DiagnosticReport.performer,<br>DiagnosticReport.<br>resultsInterpreter</td>
<td>{{pagelink:Profile-DiagnosticReport-54417}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-DischargeMethod}}</td>
<td>active</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-EmergencyCareDischargeStatus}}</td>
<td>active</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-EthnicCategory}}</td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-Evidence}}</td>
<td>active</td>
<td>AllergyIntolerance</td>
<td>{{pagelink:Profile-AllergyIntolerance-30748}}</td>
<td>NO</td>
<td>2</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-LegalStatus}}</td>
<td>active</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-ListWarningCode}}</td>
<td>active</td>
<td>List</td>
<td>{{pagelink:Profile-List-19037}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-MainLocation}}</td>
<td>active</td>
<td>Organization</td>
<td>{{pagelink:Profile-Organization-94604}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType}}</td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-34649}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-MedicationRepeatInformation}}</td>
<td>active</td>
<td>MedicationRequest</td>
<td>{{pagelink:Profile-MedicationRequest-20572}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-MedicationStatementLastIssueDate}}</td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-34649}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td> {{pagelink:Extension-UKCore-MedicationTradeFamily}}</td>
<td>active</td>
<td>Medication</td>
<td>{{pagelink:Profile-Medication-73860}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-NHSNumberUnavailableReason}}</td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-NHSNumberVerificationStatus}}</td>
<td>active</td>
<td>Patient.identifier</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-OtherContactSystem}}</td>
<td>active</td>
<td>ContactPoint.system,<br>
Patient.telecom.system,<br>
RelatedPerson.telecom.system</td>
<td>{{pagelink:Profile-Patient-88961}} <br> 
{{pagelink:Profile-RelatedPerson-51006}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-OutcomeOfAttendance}}</td>
<td>active</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-79976}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-ParentPresent}}</td>
<td>active</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-PharmacistVerifiedIndicator}}</td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-34649}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-PriorityReason}}</td>
<td>active</td>
<td>ServiceRequest.priority</td>
<td>{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-ResidentialStatus}}</td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-88961}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-SampleCategory}}</td>
<td>active</td>
<td>Specimen</td>
<td>{{pagelink:Profile-Specimen-37178}}</td>
<td>NO</td>
<td>6</td>
</tr>
<tr class="balloted">
<td>{{pagelink:Extension-UKCore-SourceOfServiceRequest}}</td>
<td>active</td>
<td>ServiceRequest</td>
<td>{{pagelink:Profile-ServiceRequest-88746}}</td>
<td>NO</td>
<td>5</td>
</tr>
<tr>
<td>{{pagelink:Extension-UKCore-VaccinationProcedure}}</td>
<td>active</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-16790}}</td>
<td>NO</td>
<td>3</td>
</tr>
</table>
</div>

<div id="Alphabetical" class="tabcontent">
<h3>Alphabetical Listing</h3>

<table>
<tbody>
<tr class="a-to-z"><td>
<p><b>A-D:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AdditionalContact,text:UKCore-AdditionalContact}}</li>
<li>{{pagelink:Extension-UKCore-AddressKey,text:UKCore-AddressKey}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-AdmissionMethod,text:UKCore-AdmissionMethod}}</li>
<li>{{pagelink:Extension-UKCore-AllergyIntoleranceEnd,text:UKCore-AllergyIntoleranceEnd}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-AssociatedEncounter,text:UKCore-AssociatedEncounter}}</li>
<li>{{pagelink:Extension-UKCore-BirthSex,text:UKCore-BirthSex}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-BodySiteReference,text:UKCore-BodySiteReference}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-BookingOrganization,text:UKCore-BookingOrganization}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-CareSettingType,text:UKCore-CareSettingType}}</li>
<li>{{pagelink:Extension-UKCore-CodingSCTDescDisplay,text:UKCore-CodingSCTDescDisplay}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-ConditionEpisode,text:UKCore-ConditionEpisode}}</li>
<li>{{pagelink:Extension-UKCore-ContactPreference,text:UKCore-ContactPreference}}</li>
<li>{{pagelink:Extension-UKCore-ContactRank,text:UKCore-ContactRank}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-Coverage,text:UKCore-Coverage}}</li>
<li>{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator,text:UKCore-CopyCorrespondenceIndicator}}</li>
<li>{{pagelink:Extension-UKCore-DeathNotificationStatus,text:UKCore-DeathNotificationStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DeliveryChannel,text:UKCore-DeliveryChannel}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DeviceReference,text:UKCore-DeviceReference}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DischargeMethod,text:UKCore-DischargeMethod}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>E-L:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-EmergencyCareDischargeStatus,text:UKCore-EmergencyCareDischargeStatus}}</li>
<li>{{pagelink:Extension-UKCore-EthnicCategory,text:UKCore-EthnicCategory}}</li>
<li>{{pagelink:Extension-UKCore-Evidence,text:UKCore-Evidence}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-LegalStatus,text:UKCore-LegalStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-ListWarningCode,text:UKCore-ListWarningCode}}</li>
</ul>
</td></tr>
<tr class="a-to-z"><td>
<p><b>M-P:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MainLocation,text:UKCore-MainLocation}}</li>
<li>{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType,text:UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:Extension-UKCore-MedicationRepeatInformation,text:UKCore-MedicationRepeatInformation}}</li>
<li>{{pagelink:Extension-UKCore-MedicationStatementLastIssueDate,text:UKCore-MedicationStatementLastIssueDate}}</li>
<li>{{pagelink:Extension-UKCore-MedicationTradeFamily,text:UKCore-MedicationTradeFamily}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-NHSNumberUnavailableReason,text:UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:Extension-UKCore-NHSNumberVerificationStatus,text:UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:Extension-UKCore-OtherContactSystem,text:UKCore-OtherContactSystem}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-OutcomeOfAttendance,text:UKCore-OutcomeOfAttendance}}</li>
<li>{{pagelink:Extension-UKCore-ParentPresent,text:UKCore-ParentPresent}}</li>
<li>{{pagelink:Extension-UKCore-PharmacistVerifiedIndicator,text:UKCore-PharmacistVerifiedIndicator}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-PriorityReason,text:UKCore-PriorityReason}}</li>
</ul>
</td><td style="border-left: 1px solid #eeeeee">
<p><b>Q-Z:</b></p> 
<ul>  
<li>{{pagelink:Extension-UKCore-ResidentialStatus,text:UKCore-ResidentialStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SampleCategory,text:UKCore-SampleCategory}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SourceOfServiceRequest,text:UKCore-SourceOfServiceRequest}}</li>
<li>{{pagelink:Extension-UKCore-VaccinationProcedure,text:UKCore-VaccinationProcedure}}</li>
</ul>
</td></tr>

</tbody></table>
</div>


<div id="Sprint" class="tabcontent">
<h3>By Sprint</h3>

<p><b>C&TA Sprint 1:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-AddressKey,text:UKCore-AddressKey}}</li>
<li>{{pagelink:Extension-UKCore-BirthSex,text:UKCore-BirthSex}}</li>
<li>{{pagelink:Extension-UKCore-ContactPreference,text:UKCore-ContactPreference}}</li>
<li>{{pagelink:Extension-UKCore-ContactRank,text:UKCore-ContactRank}}</li>
<li>{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator,text:UKCore-CopyCorrespondenceIndicator}}</li>
<li>{{pagelink:Extension-UKCore-DeathNotificationStatus,text:UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:Extension-UKCore-EthnicCategory,text:UKCore-EthnicCategory}}</li>
<li>{{pagelink:Extension-UKCore-MainLocation,text:UKCore-MainLocation}}</li>
<li>{{pagelink:Extension-UKCore-NHSNumberVerificationStatus,text:UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:Extension-UKCore-OtherContactSystem,text:UKCore-OtherContactSystem}}</li>
<li>{{pagelink:Extension-UKCore-ResidentialStatus,text:UKCore-ResidentialStatus}}</li>
</ul>

<p><b>C&TA Sprint 2:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-AllergyIntoleranceEnd,text:UKCore-AllergyIntoleranceEnd}}</li>
<li>{{pagelink:Extension-UKCore-CodingSCTDescDisplay,text:UKCore-CodingSCTDescDisplay}}</li>
<li>{{pagelink:Extension-UKCore-Evidence,text:UKCore-Evidence}}</li>
</ul>

<p><b>C&TA Sprint 3:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType,text:UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:Extension-UKCore-MedicationRepeatInformation,text:UKCore-MedicationRepeatInformation}}</li>
<li>{{pagelink:Extension-UKCore-MedicationStatementLastIssueDate,text:UKCore-MedicationStatementLastIssueDate}}</li>
<li>{{pagelink:Extension-UKCore-MedicationTradeFamily,text:UKCore-MedicationTradeFamily}}</li>
<li>{{pagelink:Extension-UKCore-ParentPresent,text:UKCore-ParentPresent}}</li>
<li>{{pagelink:Extension-UKCore-PharmacistVerifiedIndicator,text:UKCore-PharmacistVerifiedIndicator}}</li>
<li>{{pagelink:Extension-UKCore-VaccinationProcedure,text:UKCore-VaccinationProcedure}}</li>
</ul>

<p><b>C&TA Sprint 4:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AdmissionMethod,text:UKCore-AdmissionMethod}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-CareSettingType,text:UKCore-CareSettingType}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-ConditionEpisode,text:UKCore-ConditionEpisode}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DischargeMethod,text:UKCore-DischargeMethod}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-EmergencyCareDischargeStatus,text:UKCore-EmergencyCareDischargeStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-LegalStatus,text:UKCore-LegalStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-ListWarningCode,text:UKCore-ListWarningCode}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-OutcomeOfAttendance,text:UKCore-OutcomeOfAttendance}}</li>
</ul>

<p><b>C&TA Sprint 5:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-BookingOrganization,text:UKCore-BookingOrganization}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DeliveryChannel,text:UKCore-DeliveryChannel}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SourceOfServiceRequest,text:UKCore-SourceOfServiceRequest}}</li>
</ul>

<p><b>C&TA Sprint 6:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AdditionalContact,text:UKCore-AdditionalContact}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-AssociatedEncounter,text:UKCore-AssociatedEncounter}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-BodySiteReference,text:UKCore-BodySiteReference}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-Coverage,text:UKCore-Coverage}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DeviceReference,text:UKCore-DeviceReference}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-NHSNumberUnavailableReason,text:UKCore-NHSNumberUnavailableReason}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-PriorityReason,text:UKCore-PriorityReason}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SampleCategory,text:UKCore-SampleCategory}}</li>
</ul>

</div>

<div id="Resource" class="tabcontent">
<h3>By Resource (US Core style)</h3>

<p><b>AllergyIntolerance:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-AllergyIntoleranceEnd,text:UKCore-AllergyIntoleranceEnd}}</li>
<li>{{pagelink:Extension-UKCore-Evidence,text:UKCore-Evidence}}</li>
</ul>
<p><b>Appointment:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-BookingOrganization,text:UKCore-BookingOrganization}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DeliveryChannel,text:UKCore-DeliveryChannel}}</li>
</ul>
<p><b>Composition:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-CareSettingType,text:UKCore-CareSettingType}}</li>
</ul>
<p><b>Condition:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-ConditionEpisode,text:UKCore-ConditionEpisode}}</li>
</ul>
<p><b>DiagnosticReport:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-DeviceReference,text:UKCore-DeviceReference}}</li>
</ul>
<p><b>Encounter:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AdmissionMethod,text:UKCore-AdmissionMethod}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-DischargeMethod,text:UKCore-DischargeMethod}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-EmergencyCareDischargeStatus,text:UKCore-EmergencyCareDischargeStatus}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-LegalStatus,text:UKCore-LegalStatus}}</li>
</ul>
<p><b>FamilyMemberHistory:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AssociatedEncounter,text:UKCore-AssociatedEncounter}}</li>
</ul>
<p><b>Immunization:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-ParentPresent,text:UKCore-ParentPresent}}</li>
<li>{{pagelink:Extension-UKCore-VaccinationProcedure,text:UKCore-VaccinationProcedure}}</li>
</ul>
<p><b>List:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-CareSettingType,text:UKCore-CareSettingType}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-ListWarningCode,text:UKCore-ListWarningCode}}</li>
</ul>
<p><b>Medication:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MedicationTradeFamily,text:UKCore-MedicationTradeFamily}}</li>
</ul>
<p><b>MedicationRequest:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MedicationRepeatInformation,text:UKCore-MedicationRepeatInformation}}</li>
</ul>
<p><b>MedicationStatement:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType,text:UKCore-MedicationPrescribingOrganizationType}}</li>
<li>{{pagelink:Extension-UKCore-MedicationStatementLastIssueDate,text:UKCore-MedicationStatementLastIssueDate}}</li>
<li>{{pagelink:Extension-UKCore-PharmacistVerifiedIndicator,text:UKCore-PharmacistVerifiedIndicator}}</li>
</ul>
<p><b>Organization:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-MainLocation,text:UKCore-MainLocation}}</li>
</ul>
<p><b>Patient:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-AddressKey,text:UKCore-AddressKey}}</li>
<li>{{pagelink:Extension-UKCore-BirthSex,text:UKCore-BirthSex}}</li>
<li>{{pagelink:Extension-UKCore-ContactPreference,text:UKCore-ContactPreference}}</li>
<li>{{pagelink:Extension-UKCore-ContactRank,text:UKCore-ContactRank}}</li>
<li>{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator,text:UKCore-CopyCorrespondenceIndicator}}</li>
<li>{{pagelink:Extension-UKCore-DeathNotificationStatus,text:UKCore-DeathNotificationStatus}}</li>
<li>{{pagelink:Extension-UKCore-EthnicCategory,text:UKCore-EthnicCategory}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-NHSNumberUnavailableReason,text:UKCore-NHSNumberUnavailableReason}}</li>
<li>{{pagelink:Extension-UKCore-NHSNumberVerificationStatus,text:UKCore-NHSNumberVerificationStatus}}</li>
<li>{{pagelink:Extension-UKCore-OtherContactSystem,text:UKCore-OtherContactSystem}}</li>
<li>{{pagelink:Extension-UKCore-ResidentialStatus,text:UKCore-ResidentialStatus}}</li>
</ul>
<p><b>RelatedPerson:</b></p>
<ul>
<li>{{pagelink:Extension-UKCore-ContactPreference,text:UKCore-ContactPreference}}</li>
<li>{{pagelink:Extension-UKCore-CopyCorrespondenceIndicator,text:UKCore-CopyCorrespondenceIndicator}}</li>
<li>{{pagelink:Extension-UKCore-OtherContactSystem,text:UKCore-OtherContactSystem}}</li>
</ul>
<p><b>ServiceRequest:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-AdditionalContact,text:UKCore-AdditionalContact}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-Coverage,text:UKCore-Coverage}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-PriorityReason,text:UKCore-PriorityReason}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SourceOfServiceRequest,text:UKCore-SourceOfServiceRequest}}</li>
</ul>
<p><b>Slot:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-DeliveryChannel,text:UKCore-DeliveryChannel}}</li>
</ul>
<p><b>Specimen:</b></p>
<ul>
<li class="balloted">{{pagelink:Extension-UKCore-BodySiteReference,text:UKCore-BodySiteReference}}</li>
<li class="balloted">{{pagelink:Extension-UKCore-SampleCategory,text:UKCore-SampleCategory}}</li>
</ul>
</div>

---