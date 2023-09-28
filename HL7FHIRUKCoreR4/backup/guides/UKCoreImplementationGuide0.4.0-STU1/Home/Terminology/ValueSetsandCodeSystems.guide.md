---
topic: Library-ValueSetsAndCodeSystems-7b04b3ad-26b2-4281-b1a3-8edbbe398915
---
## ValueSets and CodeSystems


This is the list of ValueSets and CodeSystems defined for use within the UK Core. 

Other ValueSets are useable if the binding strength is defined as extensible. For more information see
<a href=http://hl7.org/fhir/terminologies.html#strength target="_blank">HL7 FHIR - Binding Strengths</a>.

The UK Core ValueSets have been assigned a maturity level similar to the maturity levels described in the FHIR standard. This is intended to indicate how stable the ValueSet is deemed to be, this is in addition to the publication status of the ValueSet <a href="http://hl7.org/fhir/valueset-publication-status.html" target="_blank">HL7 FHIR statuses</a> of draft, active, retired and unknown.
<br/>
<br/>
<table id="assets">
<tr>
<th width="10%">Maturity level</th>
<th width="90%">Definition</th>
</tr>
<tr>
<td>0</td>
<td>The ValueSet has been published on the current build. This ValueSet has had no formal review and therefore may have quality issues. It is published only to allow the review process to start</td>
</tr>
<tr>
<td>1</td>
<td>The ValueSet produces no warnings during the build process and has had a formal internal review by the UK Core development team</td>
</tr>
<tr>
<td>2</td>
<td>The ValueSet has been released for review to the UK FHIR community, any feedback received has been addressed as far as possible</td>
</tr>
<tr>
<td>3</td>
<td>The ValueSet has been presented for inclusion in the Clinical and Technical Assurance process</td>
</tr>
<tr>
<td>4</td> 
<td>The ValueSet has completed the Clinical and Technical Assurance process and the status has been changed to active</td>
</tr>
<tr>
<td>5</td>
<td>The ValueSet has been presented for inclusion in the HL7 UK Ballot Process</td>
</tr>
<tr> 
<td>6</td> 
<td>The ValueSet has completed the HL7 UK Ballot process and is now deemed to be Normative</td>
</tr>
</table>
<br/>
<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note:</b></br>The ValueSets and CodeSystems listed below have been defined for use in the UK Core. These ValueSets and CodeSystems have either been assured or are currently in the process of being assured.<br/>

For the current list of ValueSets and CodeSystems under development refer to the <a href="https://simplifier.net/guide/ukcoreimplementationguideassetsindevelopment?version=current"  target="blank">UK Core Implementation Guide Assets in Development</a>
<p>Where more than one CodeSystem is listed the associated ValueSet should be expanded to give the full list of codes.</p> 
</div>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding dm+d within certain UK Core ValueSets:</b></br>For ValueSets which include the use of the dm+d CodeSystem, within this release of the UK Core it has not been possible to document in the content logical definitions the constraints to specific dm+d concept classes that are referred to within the respective ValueSet descriptions. Once work is completed within NHS Digital to put dm+d into a terminology server – anticipated to be before the end of 2021 - the mechanism with which to formally describe the applicable dm+d concept class constraints in these ValueSets can be incorporated into a later release of the UK Core.
<br/>
<br/>
In the interim, the content logical definitions for these ValueSets simply include a reference to a URL for the whole of dm+d, whilst the descriptions textually provide the constraints on the applicable dm+d concept classes that are relevant to the ValueSet.
<br/>
<br/>
The ValueSets affected by this issue are:
<li>UKCoreAllergyCode</li>
<li>UKCoreAllergySubstance</li>
<li>UKCoreMedicationCode</li>
<li>UKCoreVaccineCode</li>
<br/>
If you need further information about this please contact the Interoperable Medicines Standards programme via the Contact Us page.
</div>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding ValueSet expansions:</b></br>Within this release of the UK Core, ValueSet expansions have been incorporated into the ValueSets. For some very large ValueSets containing SNOMED data in particular, whilst the expansion may state the true number of concepts that were in the ValueSet at the time the expansion was created, the accompanying table will be limited to no more than 600 of the applicable concepts. It should also be remembered that the expansions of SNOMED data in particular represent the content available at the time the expansion was generated, but that this content can subsequently change. For an up to date and complete list of values, suppliers should consult the latest SNOMED terminology release.
</div>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding use of SNOMED CT and the binding strength of extensible.</b> 
<br/>
The FHIR standard states the following for extensible: To be conformant, codes in this element SHALL be from the specified value set if any of the codes within the value set can apply to the concept being communicated. If there is no applicable concept in value set (based on human review), an alternate concept (either system/code pair, or text) may be used instead. The important part of this statement is the human review (see 3 below).  
<p>For most clinical data exchanges SNOMED CT is the preferred CodeSystem to use, however there are many use cases where this is not possible. For example:
</p>
<br/>
<ol>
<li>The data is historical and previously coded in another terminology such as READ</li>
<li>The sending system does not support SNOMED CT</li>
<li>The SNOMED CT Ref set has tens of thousands of members which makes encoding in SNOMED CT impractical or not possible based on human review</li>
</ol>
<br/>
Therefore the guidance for UK Core is: The binding of extensible should be interpreted as encode in SNOMED CT if possible but it is allowable to encode using alternative coding systems or use text.
<br/>
<br/>
<b>Important Note:</b>
Where then is a derived Implementation Guide this may override this guidance and enforce SNOMED CT encoding.  
 
</div>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b>Important note regarding the use of the "preferred" binding strength for UK Core ValueSets containing CodeSystems specific to individual UK countries.</b> 
<br/>
Where different countries within the UK use different sets of concepts for the same data item (see list of ValueSets below where this is the case), currently the default approach to supporting this data within the UK Core is to create a CodeSystem for each individual country where requirements have been confirmed, and incorporate each such CodeSystem within a ValueSet that is then bound into the profile or extension supporting the data item (referred to as the "individual country specific CodeSystem" approach).<br/><br/>
In most cases where this approach is taken, for some of the concepts the ValueSet does contain more than one entry for the same concept. For this reason, the use of the "extensible" binding strength is deemed to be inappropriate and "preferred" is determined to be the most suitable binding strength to use instead.<br/><br/>
Work has begun to look at whether an alternative way of expressing UK Core ValueSets would be preferable where similar and potentially overlapping sets of concepts are used for the same data within the UK. The alternative approach being considered is to create a single CodeSystem which amalgamates all the different concepts from UK countries where requirements can be confirmed, creating a UK Core code for each such concept, and then using concept maps to map from the UK Core CodeSystem to a CodeSystem from each country where concepts have been taken from (referred to as the "superset of concepts" approach).<br/><br/>
It is anticipated that a meeting will be held in early 2022 for interested parties to look at some examples comparing the "individual country specific CodeSystem" and "superset of concepts" approaches, with a view to determining the best approach for the UK Core going forward and what should happen with existing UK Core ValueSets where the "individual country specific CodeSystem" has already been utilised if the "superset of concepts" is deemed to be the better approach.<br/><br/>
UK Core ValueSets where this issue arises:<br/>
<br/>
<ul>
<li>UKCore-AdmissionMethod</li>
<li>UKCore-DischargeDestination</li>
<li>UKCore-DischargeMethod</li>
<li>UKCore-EmergencyCareDischargeStatus</li>
<li>UKCore-EncounterLocationType</li>
<li>UKCore-EthnicCategory</li>
<li>UKCore-LegalStatusClassification</li>
<li>UKCore-OutcomeOfAttendance</li>
<li>UKCore-SourceOfAdmission</li>
</ul>
<br/>
</div>

<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
 
</style>

<table id="valuesetlist">
<tr>
<th width="45%">ValueSet</th>
<th width="5%">Status</th>
<th width="5%">Maturity</th>
<th width="40%">Bound in Profile/Extension</th>
<th width="5%">C&TA Sprint</th>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-AddressKeyType}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-AddressKey}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AddressKeyType}}</td>
</tr>
<tr>
<td colspan="5"  class="override"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-AdmissionMethod}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-AdmissionMethod}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AdmissionMethodEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AdmissionMethodWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>

<tr>              
<td><h4>{{pagelink:ValueSetUKCore-AllergyCode}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-AllergyManifestation}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<td><h4>{{pagelink:ValueSetUKCore-AllergySubstance}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}</td>
<td>2</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-BirthSex}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-BirthSex}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-AdministrativeGender</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-BodySite}}</h4></td>
<td>active</td>
<td>5</td>
<td>
{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}<br>
{{pagelink:Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-CareSettingType}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-CareSettingType}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-CompositionCategory}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Composition-d56239ce-28c2-4193-96e4-025156ca0908}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-CompositionSectionCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Composition-d56239ce-28c2-4193-96e4-025156ca0908}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreRecordStandardHeadings}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ConditionCategory}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ConditionCategory}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/condition-category</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ConditionCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}<br/>
{{pagelink:Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451}}<br/>
{{pagelink:ExtensionUKCore-AnaestheticIssues}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ConditionEpisode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ConceptMapUKCoreConditionEpisodicity}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ConditionEpisodicity}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-ConditionEpisode}}</td>
<td>4<br/</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ConditionEpisodicity}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ConditionRelationship}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-RelatedProblemHeader}}</td>
<td>4<br/</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ConditionRelationship}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<td><h4>{{pagelink:ValueSetUKCore-DeathNotificationStatus}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-DeathNotificationStatus}}</td>
<td>1<br/</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DeathNotificationStatus}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-DischargeDestination}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DischargeDestinationEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DischargeDestinationWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-DischargeMethod}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-DischargeMethod}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DischargeMethodEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-DischargeMethodWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-DocumentType}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Composition-d56239ce-28c2-4193-96e4-025156ca0908}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-EmergencyCareDischargeStatus}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-EmergencyCareDischargeStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EmergencyCareOutcomeOfAttendanceWales}}</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-EncounterLocationType}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EncounterLocationTypeEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EncounterLocationTypeWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-EncounterType}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-EthnicCategory}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-EthnicCategory}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryScotland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EthnicCategoryWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-HumanLanguage}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreHumanLanguage}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ImmunizationAdministrationBodySite}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ImmunizationExplanationReason}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-LegalStatusClassification}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-LegalStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-LegalStatusClassificationEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-LegalStatusClassificationWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-LegalStatusContext}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-LegalStatus}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-LegalStatusContext}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ListCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ListEmptyReasonCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-List-1c0066e8-c752-4f31-8b81-3148d46ff304}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreListEmptyReasonCode}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/list-empty-reason</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ListWarningCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-ListWarningCode}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreListWarningCode}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationCode}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationDosageMethod}}</h4></td>
<td>active</td>
<td>5</td>
<td>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationForm}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Medication-c9b14f01-2a2e-479a-b71e-094d2a882605}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationPrecondition}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationPrescribingOrganization}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-MedicationPrescribingOrganization}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem {{pagelink:CodeSystemUKCore-MedicationPrescribingOrganization}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationRequestCategory}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationRequestCategory}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-category</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationRequestCourseOfTherapy}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationRequestCouseOfTherapy}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationStatementCategory}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationStatementCategory}}</td>
</tr>
<tr>
<td colspan="5">Composed of <code>http://terminology.hl7.org/CodeSystem/medication-statement-category</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationSupplyType}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MedicationSupplyType}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MedicationTradeFamily}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-MedicationTradeFamily}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MessageEvent}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-MessageHeader-2af0a75b-3de6-42fa-8c05-03a0c1d142c5}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCoreMessageEvent}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-MessageHeaderInstruction}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-MessageHeaderInstruction}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-MessageHeaderInstruction}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-NHSNumberVerificationStatus}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-NHSNumberVerificationStatus}}</td>
<td>1<br</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-NHSNumberVerificationStatus}}</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-OperationOutcomeIssueDetails}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-OperationOutcome-07a0844d-75f0-4abe-b99b-7597e8de31f3}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-SpineErrorOrWarningCode}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-EPSIssueCode}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ITKResponseCode}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-OtherContactSystem}}</h4></td>
<td>active</td>
<td>5</td>
<td>ContactPoint.system</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-OtherContactSystem}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-OutcomeOfAttendance}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-OutcomeofAttendance}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-OutcomeOfAttendanceEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-OutcomeOfAttendanceWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-PersonMaritalStatusCode}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PersonMaritalStatus}}</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-MaritalStatus</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-PersonRelationshipType}}</h4></td>
<td>active</td>
<td>5</td>
</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}<br/>
{{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem 	<code>http://terminology.hl7.org/CodeSystem/v2-0131</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-RoleCode</code></td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-AdditionalPersonRelationshipRole}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-PractitionerRoleCode}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/practitioner-role</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-PreferredContactMethod}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PreferredContactMethod}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-PreferredWrittenCommunicationFormat}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-PreferredWrittenCommunicationFormat}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ProblemSignificance}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:ExtensionUKCore-ProblemSignificance}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ProblemSignificance}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ProcedureCode}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Procedure-bd80b4d6-26ed-44b9-a824-da6d8d399451}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ReasonImmunizationNotAdministered}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-ResidentialStatus}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-ResidentialStatus}}</td>
<td>1</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-ResidentialStatus}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-SourceOfAdmission}}</h4></td>
<td>active</td>
<td>4</td>
<td>{{pagelink:Profile-Encounter-5a2f9b8c-ab14-4c75-b214-1da4cdf34cd4}}</td>
<td>4</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-SourceOfAdmissionEngland}}</td>
</tr>
<tr>
<td colspan="5">Composed of {{pagelink:CodeSystemUKCore-SourceOfAdmissionWales}}</td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-SubstanceOrProductAdministrationRoute}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-AllergyIntolerance-5e8da262-fdbc-42db-87f2-8f4db6dbfeae}}<br/>
{{pagelink:Profile-MedicationAdministration-007326ee-0cd3-4bd8-9e08-6f4defa056c8}}<br/>
{{pagelink:Profile-MedicationDispense-778fb5fa-a9b3-49b9-a64f-4ac5f7f743b9}}<br/>
{{pagelink:Profile-MedicationRequest-cd6802ba-6531-4cf0-b080-e1aee806f6f0}}<br/>
{{pagelink:Profile-MedicationStatement-bbe9ec64-b970-4ff9-9910-ecc8704c38cf}}<br/>
{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-VaccinationProcedure}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:ExtensionUKCore-VaccinationProcedure}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-VaccinationProcedureSupplementary}}</h4></td>
<td>active</td>
<td>5</td>
<td>See guidance for {{pagelink:ExtensionUKCore-VaccinationProcedure}} for usage</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
<tr>
<td><h4>{{pagelink:ValueSetUKCore-VaccineCode}}</h4></td>
<td>active</td>
<td>5</td>
<td>{{pagelink:Profile-Immunization-3af021ba-778f-4c94-ba11-eec8146df159}}</td>
<td>3</td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>https://dmd.nhs.uk</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://terminology.hl7.org/CodeSystem/v3-NullFlavor</code></td>
</tr>
<tr>
<td colspan="5">Composed of CodeSystem <code>http://snomed.info/sct</code></td>
</tr>
<tr class="override">
<td colspan="5"></td>
</tr>
</body>
</table>

