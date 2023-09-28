---
topic: Library-Extensions-38957e9d-909d-485f-adb2-8ee4ace42c75
---
## Extension Library

This extension library contains all the extensions Clinically and Technically Assured for use with UK Core. The profiles are found in the {{pagelink:Library-Profiles-d78076a0-90d5-4e11-8b6e-64697b0bcfd9}}. The table below lists all the current extensions and the context of use. The context of use column indicates the profile and /or element where the extension may be applied. The type column indicates whether the extension is a modifierExtension or not. The general rule is extensions can be ignored by receivers*. When a modifierExtension is received it SHALL NOT be ignored as it modifies the meaning of the element or elements that contains it. Typically, this means information that qualifies or negates the primary meaning of the element that contains it.

<a href="http://hl7.org/fhir/R4/extensibility.html#Extension" target="_blank"> For more information from HL7 about FHIR extensions</a>.

<a href="http://hl7.org/fhir/R4/extensibility.html#modifierExtension" target="_blank"> For more information from HL7 about FHIR modifierExtensions</a>.

*There may be specific use cases where this is not the case and the Domain Implementation Guidance associated with the use case SHOULD be consulted.

<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><h4>Important</h4></br>
The Extensions are rendered in several formats: 
<ul>
<li><b>Snapshot:</b> a fully calculated form of the structure that is not dependent on any other structure</li>
<li><b>Differential:</b> this describes only the differences that the Extension makes relative to the structure definition (FHIR resource) they constrain</li> 
<li><b>Hybrid:</b> a hybrid view of the snapshot and differential views</li>
<li><b>Table:</b> a tabular view of the Extension elements</li>
<li><b>XML:</b> a rendering of a XML view of the Extension</li>
<li><b>JSON:</b> a rendering of a JSON view of the Extension</li> 
</ul>
<br/>
<a href="http://hl7.org/fhir/R4/extensibility.html" target="_blank"> Further information from HL7 relating to extensibility is available. </a>
</div>


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><h4>Important</h4></br>The Extensions listed below have been defined as UK Core extensions. Also included in this library are some HL7 common extensions which have been added to the UK Core profiles because they have been deemed to be "core" to UK FHIR data exchanges. These will have a page with guidance on usage in the UK and examples to illustrate usage. Note: implementers of UK Core MAY use any HL7 common extension from the HL7 standard regardless of whether the extension is included in this implementation guide. The list of common extensions in FHIR R4 is available in the <a href="http://hl7.org/fhir/R4/extensibility-registry.html" target="_blank">HL7 extension registry.</a><br/>
<p>Implementers of the UK Core profiles MAY also create their own Extensions where required, but are encouraged to engage with the UK Core development process to get their extensions adopted into the UK Core for wider use by the UK FHIR Community.</p> 
</div>
<br/>

<table id="assets">
<tr>
<th width="34%">Extensions</th>
<th width="5%">Status</th>
<th width="16%">Context of Use</th>
<th width="25%">Related Profile</th>
<th width="5%">Modifier Extension</th>
<th width="5%">C&TA Sprint</th>
</tr>
<tr >
<td><h5 id="E1">{{pagelink:ExtensionUKCore-AddressKey}}</h5></td>
<td>active</td>
<td>Address</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E2">{{pagelink:ExtensionUKCore-AllergyIntoleranceEnd}}</h5></td>
<td>active</td>
<td>AllergyIntolerance</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>NO</td>
<td>2</td>
</tr>

<tr >
<td><h5 id="E27">{{pagelink:ExtensionUKCore-BirthSex}}</h5></td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E3">{{pagelink:Extension-UKCore-CodingSCTDescDisplay}}</h5></td>
<td>active</td>
<td>Coding</td>
<td>All clinical profiles that can use SNOMED CT. See the extension page for information about how this is used in profiles. </td>
<td>NO</td>
<td>2</td>
</tr>

<tr>
<td><h5 id="E4">{{pagelink:ExtensionUKCore-ContactPreference}}</h5></td>
<td>active</td>
<td>Patient,<br>RelatedPerson</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E5">{{pagelink:ExtensionUKCore-ContactRank}}</h5></td>
<td>active</td>
<td>Patient.contact</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>

<tr >
<td><h5 id="E6"> {{pagelink:ExtensionUKCore-CopyCorrespondenceIndicator}}</h5></td>
<td>active</td>
<td>Patient.contact,<br>RelatedPerson</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td> 
</tr>
<tr >
<td><h5 id="E7">{{pagelink:ExtensionUKCore-DeathNotificationStatus}}</h5></td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E9">{{pagelink:ExtensionUKCore-EthnicCategory}}</h5></td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td><h5 id="E9">{{pagelink:ExtensionUKCore-Evidence}}</h5></td>
<td>active</td>
<td>AllergyIntolerance</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>NO</td>
<td>2</td>
</tr>
<tr>
<td><h5 id="E11">{{pagelink:ExtensionUKCore-MainLocation}}</h5></td>
<td>active</td>
<td>Organization</td>
<td>{{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5>{{pagelink:Extension-UKCore-MedicationPrescribingOrganizationType}}</h5></td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5 id="E16"> {{pagelink:ExtensionUKCore-MedicationRepeatInformation}}</h5></td>
<td>active</td>
<td>MedicationRequest</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr >
<td><h5>{{pagelink:Extension-UKCore-MedicationStatementLastIssueDate}}</h5></td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5> {{pagelink:ExtensionUKCore-MedicationTradeFamily}}</h5></td>
<td>active</td>
<td>Medication</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr >
<td><h5 id="E19"> {{pagelink:ExtensionUKCore-NHSNumberVerificationStatus}}</h5></td>
<td>active</td>
<td>Patient.identifier</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr >
<td><h5 id="E21"> {{pagelink:ExtensionUKCore-OtherContactSystem}}</h5></td>
<td>active</td>
<td>ContactPoint.system</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td><h5 id="E29">{{pagelink:ExtensionUKCore-ParentPresent}}</h5></td>
<td>active</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr>
<td><h5>{{pagelink:ExtensionUKCore-PharmacistVerifiedIndicator}}</h5></td>
<td>active</td>
<td>MedicationStatement</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>NO</td>
<td>3</td>
</tr>
<tr >
<td><h5 id="E25"> {{pagelink:ExtensionUKCore-ResidentialStatus}}</h5></td>
<td>active</td>
<td>Patient</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>NO</td>
<td>1</td>
</tr>
<tr>
<td><h5 id="E28">{{pagelink:ExtensionUKCore-VaccinationProcedure}}</h5></td>
<td>active</td>
<td>Immunization</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>NO</td>
<td>3</td>
</tr>
</table>

---