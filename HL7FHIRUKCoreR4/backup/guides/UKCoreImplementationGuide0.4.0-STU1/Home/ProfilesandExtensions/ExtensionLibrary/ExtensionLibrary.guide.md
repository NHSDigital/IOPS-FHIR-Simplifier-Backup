---
topic: Library-Extensions-38957e9d-909d-485f-adb2-8ee4ace42c75
---
## Extension Library


This extension library contains all the extensions Clinically and Technically assured for use with UK Core. The profiles are found in the {{pagelink:Library-Profiles-d78076a0-90d5-4e11-8b6e-64697b0bcfd9}}. The table below lists all the current extensions and the context of use. The context of use column indicates the profile and /or element where the extension may be applied. The type column indicates whether the extension is a modifierExtension or not. The general rule is extensions can be ignored by receivers*. When a modifierExtension is received it MUST NOT be ignored as it modifies the meaning of the element or elements that contains it. Typically, this means information that qualifies or negates the primary meaning of the element that contains it.

<a href="http://hl7.org/fhir/extensibility.html#Extension" target="_blank"> For more information from HL7 about FHIR extensions</a>.

<a href="http://hl7.org/fhir/extensibility.html#modifierExtension" target="_blank"> For more information from HL7 about FHIR modifierExtensions</a>.

*There may be specific use cases where this is not the case and the Domain Implementation Guidance associated with the use case should be consulted.

All the extensions have been assured as suitable for inclusion in the UK Core, however all extensions have been assigned a maturity level similar to the maturity levels described in the FHIR standard. This is intended to indicate how stable the extension is deemed to be, this is in addition to the publication status of the profile <a href="http://hl7.org/fhir/valueset-publication-status.html" target="_blank">HL7 FHIR statuses</a> of draft, active, retired and unknown. 
<br/>
<br/>
<br/>
<table id="assets">
<tr>
<th width="10%">Maturity level</th>
<th width="90%">Definition</th>
</tr>
<tr>
<td>0</td>
<td>The Extension has been published on the current build. This Extension has had no formal review and therefore may have quality issues. It is published only to allow the review process to start</td>
</tr>
<tr>
<td>1</td>
<td>The Extension produces no warnings during the build process and has had a formal internal review by the UK Core development team</td>
</tr>
<tr>
<td>2</td>
<td>The Extension has been released for review to the UK FHIR community, any feedback received has been addressed as far as possible</td>
</tr>
<tr>
<td>3</td>
<td>The Extension has been presented for inclusion in the Clinical and Technical Assurance process</td>
</tr>
<tr>
<td>4</td>
<td>The Extension has completed the Clinical and Technical Assurance process and the status has been changed to active</td>
</tr>
<tr>
<td>5</td>
<td>The Extension has been presented for inclusion in the HL7 UK Ballot Process</td> 
</tr>
<tr> 
<td>6</td>
<td>The Extension has completed the HL7 UK Ballot process and is now deemed to be Normative</td>
</tr>
</table>

<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>
This implementation guide only contains Extensions with a maturity level of 4 or more. Extensions that are at an earlier stage of development (maturity level of 0-2) are available in the <a href="https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment?version=current" target="_blank"> UK Core Implementation Guide Assets in Development</a>.<br/><br/>
The Extensions are rendered in several formats: 
<ul>
<li><b>Snapshot:</b> a fully calculated form of the structure that is not dependent on any other structure</li>
<li><b>Differential:</b> this describes only the differences that the Extension makes relative to the structure definition (FHIR resource) they constrain</li> 
<li><b>Hybrid:</b> a hybrid view of the snapshot and differential views</li>
<li><b>Table:</b> a tabular view of the Extension elements</li>
<li><b>XML:</b> a rendering of an XML view of the Extension</li>
<li><b>JSON:</b> a rendering of a JSON view of the Extension</li> 
</ul>
<br/>
<a href="http://hl7.org/fhir/R4/extensibility.html" target="_blank"> Further information from HL7 relating to extensibility is available. </a>
</div>


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>The Extensions listed below have been defined as UK Core extensions. Also included in this library are some HL7 common extensions which have been added to the UK Core profiles because they have been deemed to be "core" to UK FHIR data exchanges. These will have a page with guidance on usage in the UK and examples to illustrate usage. Note: implementers of UK Core may use any HL7 common extension from the HL7 standard regardless of whether the extension is included in this implemention guide. The list of common extensions in FHIR R4 is available in the <a href="http://hl7.org/fhir/R4/extensibility-registry.html" target="_blank">HL7 extension registry.</a><br/>
<p>Implementers of the UK Core profiles may also create their own Extensions where required, but are encouraged to engage with the UK Core development process to get their extensions adopted into the UK Core for wider use by the UK FHIR Community.</p> 
<br/> 
For the current list of UK Core extensions under development refer to 
<a href="https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment?version=current" target="_blank"> UK Core Implementation Guide Assets in Development Extension Library</a>
</div>
<br/>


<table id="assets">
<tr>
<th width="34%">Extensions</th>
<th width="5%">Status</th>
<th width="5%">Maturity</th>
<th width="16%">Context of Use</th>
<th width="25%">Related Profile</th>
<th width="10%">modifierExtension</th>
<th width="5%">C&TA Sprint</th>
</tr>

<tr >
<td><h5>{{pagelink:ExtensionUKCore-ActualProblem}}</h5></td>
<td>active</td>
<td>4</td>
<td>Condition</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5 id="E1">{{pagelink:ExtensionUKCore-AddressKey}}</h5></td>
<td>active</td>
<td>5</td>
<td>Address</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>


<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-AdmissionMethod}}</h5></td>
<td>active</td>
<td>4</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5 id="E2">{{pagelink:ExtensionUKCore-AllergyIntoleranceEnd}}</h5></td>
<td>active</td>
<td>5</td>
<td>AllergyIntolerance</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>NO</td>
<td>2</td>
</tr>
<tr>
<td><h5>{{pagelink:ExtensionUKCore-AnaestheticIssues}}</h5></td>
<td>active</td>
<td>4</td>
<td>Procedure</td>
<td>{{pagelink:Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5 id="E27">{{pagelink:ExtensionUKCore-BirthSex}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-CareSettingType}}</h5>
<td>active</td>
<td>4</td>
<td>Composition <br/> List  </td>
<td>{{pagelink:Profile-Composition-d56239ce-28c2-4193-96e4-025156ca0908}} <br/> 
{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5 id="E3">{{pagelink:ExtensionUKCore-CodingSCTDescId}}</h5></td>
<td>active</td>
<td>5</td>
<td>CodeableConcept</td>
<td>All clinical profiles that can use SNOMED CT. See the extension page for information about how this is used in profiles. </td>
<td>NO</td>
<td>2</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-ConditionEpisode}}</h5></td>
<td>active</td>
<td>4</td>
<td>Condition</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr>
<td><h5 id="E4">{{pagelink:ExtensionUKCore-ContactPreference}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient, <br/>RelatedPerson</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}} <br/>
{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E5">{{pagelink:ExtensionUKCore-ContactRank}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient.contact, <br/>RelatedPerson<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}<br/>
{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>NO</td>
<td>1</td>
</tr>

<tr >
<td><h5 id="E6"> {{pagelink:ExtensionUKCore-CopyCorrespondenceIndicator}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient.contact<br/> RelatedPerson</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}<br/>
{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>NO</td>
<td>1</td> 
</tr>
<tr >
<td><h5 id="E7">{{pagelink:ExtensionUKCore-DeathNotificationStatus}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-DischargeMethod}}</h5></td>
<td>active</td>
<td>4</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-EmergencyCareDischargeStatus}}</h5></td>
<td>active</td>
<td>4</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-EthnicCategory}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-Evidence}}</h5></td>
<td>active</td>
<td>5</td>
<td>AllergyIntolerance</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>NO</td>
<td>2</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-LegalStatus}}</h5></td>
<td>active</td>
<td>4</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-ListWarningCode}}</h5></td>
<td>active</td>
<td>4</td>
<td>List</td>
<td>{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5 id="E11">{{pagelink:ExtensionUKCore-MainLocation}}</h5></td>
<td>active</td>
<td>5</td>
<td>Organization</td>
<td>{{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-MedicationPrescribingOrganization}}</h5></td>
<td>active</td>
<td>5</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-MedicationStatementLastIssueDate}}</h5></td>
<td>active</td>
<td>5</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5 id="E16"> {{pagelink:ExtensionUKCore-MedicationRepeatInformation}}</h5></td>
<td>active</td>
<td>5</td>
<td>MedicationRequest</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5> {{pagelink:ExtensionUKCore-MedicationTradeFamily}}</h5></td>
<td>active</td>
<td>5</td>
<td>Medication</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-MessageHeaderInstruction}}</h5></td>
<td>active</td>
<td>4</td>
<td>MessageHeader</td>
<td>{{pagelink:Profile-MessageHeader-2af0a75b-3de6-42fa-8c05-03a0c1d142c5}}</td>
<td>NO</td>
<td>4</td>
</tr>
<tr >
<td><h5 id="E19"> {{pagelink:ExtensionUKCore-NHSNumberVerificationStatus}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient.identifier</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E21"> {{pagelink:ExtensionUKCore-OtherContactSystem}}</h5></td>
<td>active</td>
<td>5</td>
<td>ContactPoint.system</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}<br/>
{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:ExtensionUKCore-OutcomeofAttendance}}</h5></td>
<td>active</td>
<td>4</td>
<td>Encounter</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr>
<td><h5 id="E29">{{pagelink:ExtensionUKCore-ParentPresent}}</h5></td>
<td>active</td>
<td>5</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5>{{pagelink:ExtensionUKCore-PharmacistVerifiedIndicator}}</h5></td>
<td>active</td>
<td>5</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>

<tr >
<td><h5>{{pagelink:ExtensionUKCore-ProblemSignificance}}</h5></td>
<td>active</td>
<td>4</td>
<td>Condition</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5>{{pagelink:ExtensionUKCore-RelatedClinicalContent}}</h5></td>
<td>active</td>
<td>4</td>
<td>Condition</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5>{{pagelink:ExtensionUKCore-RelatedProblemHeader}}</h5></td>
<td>active</td>
<td>4</td>
<td>Condition, <br/>List</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}<br/>
{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>NO</td>
<td>4</td>
</tr>

<tr >
<td><h5 id="E25"> {{pagelink:ExtensionUKCore-ResidentialStatus}}</h5></td>
<td>active</td>
<td>5</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td><h5 id="E28">{{pagelink:ExtensionUKCore-VaccinationProcedure}}</h5></td>
<td>active</td>
<td>5</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>NO</td>
<td>3</td>
</tr>
</table>

---








