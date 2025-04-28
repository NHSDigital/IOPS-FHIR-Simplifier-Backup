---
topic: STU1Sequence
---
## {{page-title}}

<table class="assets" title="STU1 Sequence release list">

<tr>
<th class="width05">Date</th>	
<th class="width10">IG Version</th>
<th class="width05">FHIR Version</th>	
<th class="Width50">Description</th>	
</tr>

<tr>
<td>31st January 2023</td>
<td>1.0.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.0.0 - STU1 First HL7 UK Ballot version of UK Core.</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<tr>
<ul>
<li>Implementation Guide and Associated FHIR Assets</li>
<li>Minor tweaks following the review period of Pre-release version.</li>
</ul>
</td>
</tr>

<tr>
<td>18th November 2022</td>
<td>1.0.0 - Pre-Release</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.0.0 - STU1 - Pre-release version of the First HL7 UK Ballot version of UK Core.</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li>Implementation Guide and Associated FHIR Assets</li>
<li>Updated to align with the resolutions agreed during the HL7 UK Ballot process.</li>
</ul>
</td>
</tr>
</table>

<br>

## STU1 Sequence - Historical releases

<table class="assets" title="Historical release list">

<tr>
<th class="width05">Date</th>	
<th class="width10">IG Version</th>
<th class="width05">FHIR Version</th>	
<th class="Width50">Description</th>	
</tr>

<tr>
<td>14th March 2022</td>
<td>0.5.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 0.5.0 - STU1 - Version of the UK Core Implementation Guide from Sprint 5 of Clinical and Technical Assurance.</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
Added the Profiles and associated FHIR assets required for Sprint 5 of C&TA.
<ul>
<li>Appointment</li>
<li>Flag</li>
<li>Healthcare Service</li>
<li>Questionnaire</li>
<li>QuestionnaireResponse</li>
<li>Schedule</li>
<li>ServiceRequest</li>
<li>Slot</li>
<li>Task</li>
</ul>
</tr>

<tr>
<td>27th January 2022</td>
<td>0.4.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 0.4.0 - STU1 - Version of the UK Core Implementation Guide from Sprint 4 of Clinical and Technical Assurance.</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li>All Sprint 4 artefacts</li>
<li>Updates and bug fixes to the FHIR assets following the 2 week review of 0.3.0 (Pre-Release).</li>
</ul>
</td>
</tr>

<tr>
<td>19th January 2022</td>
<td>0.3.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 0.3.0 - STU1 (Pre-Release) - Version of the UK Core Implementation Guide with updates from Sprint 4 of Clinical and Technical Assurance as a pre-release for external comments and feedback.</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b></td>
</tr>
<tr>
<td colspan="2"><b>Related Asset</b></td>
<td colspan="2"><b>Change Description</b></td>
</tr>
<tr>
<td colspan="2">All Sprint 4 artefacts</td>
<td colspan="2">For artefacts not covered by a previous sprint, status element set to active (unless being retired), date set to 2022-01-07, version incremented from existing value (unless being retired) or set to 1.0.0 for new artefacts.</td>
</tr>
<tr>
<td colspan="2">All profile elements that use reference data types</td>
<td colspan="2">Updated the guidance on the element page to give links to the allowable UK Core profile(s) or where no UK Core profile exists to the allowable R4 Resource in the FHIR Standard.</td>
</tr>
<tr>
<td colspan="2">Multiple profile and extension guidance pages and index pages</td>
<td colspan="2">Correction of typos, formatting issues and broken and missing links, and minor amendments that do not alter meaning.</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-Composition</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in binding to 1 extension;<br/>
-	category element: changed binding to a new UKCore-CompositionCategory ValueSet with a preferred binding strength to reflect it being a suggested set of concepts.<br/><br/>
Guidance changes:<br/>
-	Example Usage Scenarios: incorrect references to encounter changed to composition and document;<br/>
-	subject element: added in guidance for references to FHIR resources other than Patient;<br/>
-	category element: updated guidance to reflect change of binding;<br/>
-	attester element: provided additional guidance.<br/><br/>
Examples:<br/>
-	new example illustrating a discharge summary added.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-Condition</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in bindings to 5 extensions;<br/>
-	category element: changed binding to a new UKCore-ConditionCategory ValueSet;<br/>
-	code element: removed slicing and moved binding to UKCore-ConditionCode ValueSet from the slice to this element;<br/>
-	bodySite element: removed slicing and moved binding to UKCore-BodySite ValueSet from the slice to this element.<br/><br/>
Guidance changes:<br/>
-	added in pages for each of the 4 new extensions;<br/>
-	verificationStatus element: provided strong guidance to highlight potential clinical risks associated with some of the values in the FHIR Standard required ConditionVerificationStatus ValueSet associated with this element;<br/>
-	bodySite element: added in guidance relating to the use of the UKCore-BodySite ValueSet;<br/>
-	category element: updated guidance to reflect change of binding;<br/>
-	subject element: added in guidance to the Group FHIR resource.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-Encounter</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in bindings to 5 extensions;<br/>
-	type element: removed slicing and moved binding to UKCore-EncounterType ValueSet from the slice to this element;<br/>
-	serviceType element: changed binding to a new UKCore-CareSettingType ValueSet;<br/>
-	hospitalization.admitSource element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries;<br/>
-	hospitalization.reAdmission element: removed redundant slicing (there being no specific binding to a UKCore ValueSet);<br/>
-	hospitalization.dischargeDisposition element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries;<br/>
-	location.physicalType element: changed binding to a new UKCore-EncounterLocationType ValueSet, with a preferred binding strength to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.<br/><br/>
Guidance changes:<br/>
-	removed guidance page for the UKCore-EncounterTransport extension as there was no identified use case for this extension;<br/>
-	type element: removed reference to using other ValueSets and the slice being open;<br/>
-	subject element: added in guidance to the Group FHIR resource.<br/><br/>
Examples:<br/>
-	UKCore-Encounter-InpatientEncounter has two added extensions incorporated and the CodeSystem reference for DischargeDestination updated in line with changes associated with the ValueSet for this data
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-EpisodeOfCare</td>
<td colspan="2">Guidance changes:<br/>
-	added in a section describing the relationship between EpisodeOfCare and Encounter.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-List</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in bindings to 3 extensions.<br/><br/>
Guidance changes:<br/>
-	changed guidance page for the clinicalSetting extension to the careSettingType extension;<br/>
-	identifier element: incorrect reference to EpisodeOfCare changed to List;<br/>
-	subject element: added in guidance for references to FHIR resources other than Patient;<br/>
-	emptyReason element: added in guidance relating to the use of the UKCore-ListEmptyReasonCode ValueSet.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-MessageHeader</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in a binding to 1 extension;<br/>
-	event[x] element: reinstated the eventUri choice.<br/><br/>
Guidance changes:<br/>
-	added in a section relating to extending the MessageHeader resource;<br/>
-	destination element: added in guidance on some of the component elements of destination;<br/>
-	source element: added in guidance on the component elements of source.<br/><br/>
Examples:<br/>
-	new example illustrating the message header for a discharge summary added.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-OperationOutcome</td>
<td colspan="2">Structure Definition changes:<br/>
-	issue.details element: changed binding to a new UKCore-OperationOutcomeIssueDetails ValueSet with a preferred binding strength to reflect it being a suggested set of concepts.<br/><br/>
Guidance changes:<br/>
-	issue.details element: updated guidance to reflect change of binding.
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-Patient</td>
<td colspan="2">Examples:<br/>
-	UKCore-Patient-BabyPatient has changes associated with EthnicCategory<br/>
-	UKCore-Patient-RichardSmith has changes associated with EthnicCategory and PreferredContactTimes
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-Procedure</td>
<td colspan="2">Structure Definition changes:<br/>
-	added in a binding to 1 extension;<br/>
-	code element: removed slicing and moved binding to UKCore-ProcedureCode ValueSet from the slice to this element;<br/>
-	bodySite element: removed slicing and moved binding to UKCore-BodySite ValueSet from the slice to this element;<br/>
-	complication element: removed slicing and moved binding to UKCore-ConditionCode ValueSet from the slice to this element.<br/><br/>
Guidance changes:<br/>
-	status element: provided strong guidance to highlight that this element is a modifier because it contains codes that mark the resource as not currently valid and that the code element must not be processed in isolation but implementers must also process the status and statusReason elements as they may modify the context of the procedure code information;<br/>
-	performer element: added in guidance on some of the component elements of performer;<br/>
-	bodySite element: added in guidance relating to the use of the UKCore-BodySite ValueSet.<br/>
</td>
</tr>
<tr>
<td colspan="2">Profile UKCore-RelatedPerson</td>
<td colspan="2">Examples:<br/>
-	UKCore-RelatedPerson-JoySmith has changes associated with PreferredContactTimes
</td>
</tr>
<tr>
<td colspan="2">Extension Library page </td>
<td colspan="2">- Additional entries included for new UK Core and additional HL7 Common Extensions (details of the specific added Extensions are listed below).<br/>
- Extensions from Sprints 1-3 given a maturity level of 5.
</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-ActualProblem</td>
<td colspan="2">New extension, based on the Care Connect Actual Problem extension, with a context of use of the UKCore-Condition profile.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-AdmissionMethod</td>
<td colspan="2">Structure Definition changes:<br/>
-	value[x] element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.<br/><br/>
Example added.
</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-AnaestheticIssues</td>
<td colspan="2">Example added.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-CareSettingType</td>
<td colspan="2">Existing extension context of use updated to also include the UKCore-List profile. Description amended to reflect the additional context of use.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-ClinicalSetting</td>
<td colspan="2">Existing extension status changed to retired as it effectively duplicated the UKCore-CareSettingType extension.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-CodingSCTDescId</td>
<td colspan="2">Example amended to provide correct context for the extension content.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-ConditionEpisode</td>
<td colspan="2">Example added.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-ContactPreference</td>
<td colspan="2">Example amended to align with changes to the datatype for PreferredContactTimes.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-DischargeMethod</td>
<td colspan="2">Structure Definition changes:<br/>
-	value[x] element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.<br/><br/>
Example added.
</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-EmergencyCareDischargeStatus</td>
<td colspan="2">Structure Definition changes:<br/>
-	value[x] element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.
</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-EncounterTransport</td>
<td colspan="2">Existing extension status changed to retired as there was no identified use case for this extension.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-EthnicCategory</td>
<td colspan="2">Structure Definition changes:<br/>
-	value[x] element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.
</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-Evidence</td>
<td colspan="2">Existing extension status corrected to active. No other changes made.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-LegalStatus</td>
<td colspan="2">New extension to support legal status on admission and legal status on discharge, with a context of use of the UKCore-Encounter profile.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-ListWarningCode</td>
<td colspan="2">Example added.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-MessageHeaderInstruction</td>
<td colspan="2">New extension to support a specific instruction for receivers of the message, with a context of use of the UKCore-MessageHeader profile.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-OutcomeOfAttendance</td>
<td colspan="2">Structure Definition changes:<br/>
-	value[x] element: changed binding strength from extensible to preferred to reflect the important note on the ValueSets and CodeSystem page relating to ValueSets containing CodeSystems specific to individual UK countries.<br/><br/>
Guidance changes:<br/>
-	page description: removed the word "Consultant" at the end.<br/><br/>
Example added.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-RelatedClinicalContent</td>
<td colspan="2">New extension, based on the Care Connect Related Clinical Content extension, with a context of use of the UKCore-Condition profile.</td>
</tr>
<tr>
<td colspan="2">Extension UKCore-RelatedProblemHeader</td>
<td colspan="2">New extension, based on the Care Connect Related Problem Header extension, with a context of use of the UKCore-Condition and UKCore-List profiles.</td>
</tr>
<tr>
<td colspan="2">Common Extension-messageheader-response-request</td>
<td colspan="2">Newly listed extension, with a context of use of the UKCore-MessageHeader profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet and CodeSystems page </td>
<td colspan="2">- Reformatted the table to make it easier to read.<br/>
- Additional entries included for new ValueSets (details of the specific added ValueSets are listed below).<br/>
- ValueSets from Sprints 1-3 given a maturity level of 5.<br/>
- Important note regarding use of SNOMED CT and the binding strength of extensible added in.<br/>
- Important note regarding the use of the "preferred" binding strength for UK Core ValueSets containing CodeSystems specific to individual UK countries added in.<br/>
- Miscellaneous corrections also made.
</td>
</tr>
<tr>
<td colspan="2">All Sprint 4 ValueSets</td>
<td colspan="2">The description for each Sprint 4 ValueSet has been modified to align with the wording approach used for ValueSets in Sprints 1 to 3.</td>
</tr>
<tr>
<td colspan="2">All Sprint 4 ValueSets</td>
<td colspan="2">An expansion is provided for each Sprint 4 ValueSet where concepts are specified within the constituent CodeSystem(s).</td>
</tr>
<tr>
<td colspan="2">All Sprint 4 ValueSets which use SNOMED CT</td>
<td colspan="2">The Content Logical Definition for each Sprint 4 ValueSet which makes use of SNOMED CT has been modified to align with the approach used for ValueSets using SNOMED CT in Sprints 1 to 3. All SNOMED is encapsulated within the Content Logical Definition using SNOMED Expression Constraint Language (ECL) in a single statement in the value element, together with a property element value of "constraint" and an op element value of "=". The ECL informative long syntax rather than the normative brief syntax is used to identify a hierarchy or reference set. Concept display values are not included in the ECL statement.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-AdmissionMethod</td>
<td colspan="2">Existing ValueSet modified to replace the single existing NHSDataModelAndDictionaryAdmissionMethod Codesystem in the Content Logical Definition with two UK Core CodeSystems. Bound in the UKCore-AdmissionMethod extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-CompositionCategory</td>
<td colspan="2">New ValueSet, bound in the UKCore-Composition profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-ConditionCategory</td>
<td colspan="2">Existing ValueSet modified to include concepts from the FHIR standard condition-category CodeSystem and a new UKCoreConditionCategory CodeSystem. Bound in the UKCore-Condition profile. </td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-ConditionRelationship</td>
<td colspan="2">New ValueSet, bound in the UKCore-RelatedProblemHeader extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-DischargeDestination</td>
<td colspan="2">Existing ValueSet modified to replace the single existing NHSDataModelAndDictionaryDischargeDestination Codesystem in the Content Logical Definition with two UK Core CodeSystems. Bound in the UKCore-Encounter profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-DischargeMethod</td>
<td colspan="2">Existing ValueSet modified to replace the single existing NHSDataModelAndDictionaryDischargeMethod Codesystem in the Content Logical Definition with two UK Core CodeSystems. Bound in the UKCore-DischargeMethod extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-EmergencyCareDischargeStatus</td>
<td colspan="2">Existing ValueSet modified to add in a UK Core Codesystem into the Content Logical Definition. Bound in the UKCore-EmergencyCareDischargeStatus extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-EncounterLocationType</td>
<td colspan="2">New ValueSet, bound in the UKCore-Encounter profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-LegalStatusClassification</td>
<td colspan="2">New ValueSet, bound in the UKCore-LegalStatus extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-LegalStatusContext</td>
<td colspan="2">New ValueSet, bound in the UKCore-LegalStatus extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-ListEmptyReasonCode</td>
<td colspan="2">Existing ValueSet modified to include concepts from the FHIR standard List Empty Reasons CodeSystem. Bound in the UKCore-List profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-MessageEvent</td>
<td colspan="2">Existing ValueSet modified to remove the single existing SNOMED CT concept and be composed of a single UK Core CodeSystem. Bound in the UKCore-MessageHeader profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-MessageHeaderInstruction</td>
<td colspan="2">New ValueSet, bound in the UKCore-MessageHeaderInstruction extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-OperationOutcomeIssueDetails</td>
<td colspan="2">New ValueSet, bound in the UKCore-OperationOutcome profile.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-OutcomeOfAttendance</td>
<td colspan="2">Existing ValueSet modified to replace the single existing NHSDataModelAndDictionaryOutcomeofAttendance Codesystem in the Content Logical Definition with two UK Core CodeSystems. Bound in the UKCore-OutcomeofAttendance extension. Also removed the word "Consultant" at the end of the ValueSet description.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-ProblemSignificance</td>
<td colspan="2">New ValueSet, bound in the UKCore-ProblemSignificance extension.</td>
</tr>
<tr>
<td colspan="2">ValueSet UKCore-SourceOfAdmission</td>
<td colspan="2">Existing ValueSet modified to replace the single existing NHSDataModelAndDictionarySourceOfAdmission Codesystem in the Content Logical Definition with two UK Core CodeSystems. Bound in the UKCore-Encounter profile.</td>
</tr>
<tr>
<td colspan="2">CodeSystem NHSDataModelandDictionary-AdmissionMethod</td>
<td colspan="2">Existing CodeSystem retired and replaced by a similar CodeSystem UKCore-AdmissionMethodEngland.</td>
</tr>
<tr>
<td colspan="2">CodeSystem NHSDataModelandDictionary-DischargeDestination</td>
<td colspan="2">Existing CodeSystem retired and replaced by a similar CodeSystem UKCore-DischargeDestinationEngland.</td>
</tr>
<tr>
<td colspan="2">CodeSystem NHSDataModelandDictionary-DischargeMethod</td>
<td colspan="2">Existing CodeSystem retired and replaced by a similar CodeSystem UKCore-DischargeMethodEngland.</td>
</tr>
<tr>
<td colspan="2">CodeSystem NHSDataModelandDictionary-OutcomeofAttendance</td>
<td colspan="2">Existing CodeSystem retired and replaced by a similar CodeSystem UKCore-OutcomeofAttendanceEngland.</td>
</tr>
<tr>
<td colspan="2">CodeSystem NHSDataModelandDictionary-SourceOfAdmission</td>
<td colspan="2">Existing CodeSystem retired and replaced by a similar CodeSystem UKCore-SourceOfAdmissionEngland.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-AdmissionMethodEngland</td>
<td colspan="2">New CodeSystem, to replace NHSDataModelandDictionary-AdmissionMethod.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-AdmissionMethodWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Admission Method data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-ConditionCategory</td>
<td colspan="2">New CodeSystem, consisting of concepts from the Care Connect Condition Category CodeSystem not contained in the FHIR standard condition-category CodeSystem.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-ConditionRelationship</td>
<td colspan="2">New CodeSystem, based on the Care Connect Condition Relationship CodeSystem.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-DischargeDestinationEngland</td>
<td colspan="2">New CodeSystem, to replace NHSDataModelandDictionary-DischargeDestination.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-DischargeDestinationWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Discharge Destination data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-DischargeMethodEngland</td>
<td colspan="2">New CodeSystem, to replace NHSDataModelandDictionary-DischargeDestination.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-DischargeMethodWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Discharge Method data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-EncounterLocationTypeEngland</td>
<td colspan="2">New CodeSystem, derived from the NHS Data Dictionary Activity Location Type Code data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-EncounterLocationTypeWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Location Type Code data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-EPSIssueCode</td>
<td colspan="2">New CodeSystem, derived from NHS Digital defined EPS Issue Codes.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-ITKResponseCode</td>
<td colspan="2">New CodeSystem, derived from NHS Digital defined ITK Response Codes.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-LegalStatusClassificationEngland</td>
<td colspan="2">New CodeSystem, derived from the NHS Data Dictionary Mental Health Act Legal Status Classification Code data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-LegalStatusClassificationWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Legal Status data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-LegalStatusContext</td>
<td colspan="2">New CodeSystem, providing a context for the legal status classification (admission or discharge).</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-MessageHeaderInstruction</td>
<td colspan="2">New CodeSystem, intending to provide a specific instruction for a receiver of a message (currently no UK Core set of codes are specified).</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-OutcomeOfAttendanceEngland</td>
<td colspan="2">New CodeSystem, to replace NHSDataModelandDictionary-OutcomeOfAttendance.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-OutcomeOfAttendanceWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Outcome Of Attendance data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-ProblemSignificance</td>
<td colspan="2">New CodeSystem, based on the Care Connect Problem Significance CodeSystem.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-SourceOfAdmissionEngland</td>
<td colspan="2">New CodeSystem, to replace NHSDataModelandDictionary-SourceOfAdmission.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-SourceOfAdmissionWales</td>
<td colspan="2">New CodeSystem, derived from the NHS Wales Data Dictionary Source Of Admission data element.</td>
</tr>
<tr>
<td colspan="2">CodeSystem UKCore-SpineErrorOrWarningCode</td>
<td colspan="2">New CodeSystem, derived from NHS Digital defined Spine Error Or Warning Codes.</td>
</tr>
<tr>
<td colspan="2">Examples index page</td>
<td colspan="2">- New profile example added: UKCore-Composition-Discharge<br/>
- New profile example added: UKCore-MessageHeader-Discharge<br/>
- New common extension example added: MessageHeaderResponseRequest<br/>
- New extension example added: UKCore-Condition-Extension-ActualProblem<br/>
- New extension example added: UKCore-Condition-Extension-ConditionEpisode<br/>
- New extension example added: UKCore-Condition-Extension-ProblemSignificance<br/>
- New extension example added: UKCore-Condition-Extension-RelatedClinicalContent<br/>
- New extension example added: UKCore-Condition-Extension-RelatedProblemHeader<br/>
- New extension example added: UKCore-Encounter-AdmissionMethod<br/>
- New extension example added: UKCore-Encounter-DischargeMethod<br/>
- New extension example added: UKCore-Encounter-EmergencyCareDischargeStatus<br/>
- New extension example added: UKCore-Encounter-Extension-LegalStatus<br/>
- New extension example added: UKCore-Encounter-Extension-OutcomeOfAttendance<br/>
- New extension example added: UKCore-List-Extension-ListWarningCode<br/>
- New extension example added: UKCore-MessageHeader-Extension-MessageHeaderInstruction<br/>
- New extension example added: UKCore-Procedure-Extension-AnaestheticIssues<br/>
- Existing profile example updated: UKCore-Encounter-InpatientEncounter has two added extensions incorporated and the CodeSystem reference for DischargeDestination updated in line with changes associated with the ValueSet for this data<br/>
- Existing profile example updated: UKCore-Patient-BabyPatient has changes associated with EthnicCategory<br/>
- Existing profile example updated: UKCore-Patient-RichardSmith has changes associated with EthnicCategory and PreferredContactTimes<br/>
- Existing extension example updated: UKCore-Patient-ContactPreferences has changes associated with PreferredContactTimes<br/>
- Existing extension example renamed: UKCore-Composition-Extension-CareSettingType (was UKCore-Extension-Composition-CareSettingType)<br/>
- Existing extension example renamed: patientInterpreterRequired (was UKCore-InterpreterRequired but this is a FHIR standard common extension)<br/>
- Existing profile example removed: UKCore-AllergyList (a duplicate of UKCore-Bundle-BundledAllergyList)<br/>
- Existing profile example removed: UKCore-ContactPreference (a duplicate of UKCore-Patient-ContactPreference)<br/>
- Existing profile example removed: UKCore-CopyCorrespondenceIndicator (a duplicate of UKCore-Patient-CopyCorrespondenceIndicator)<br/>
- Existing profile example removed: UKCore-Extension-Patient-AddressKey (a duplicate of UKCore-Patient-AddressKey)<br/>
- Existing profile example removed: UKCore-Extension-Organization-MainLocation (a duplicate of UKCore-Organization-MainLocation)<br/>
- Existing profile example removed: UKCore-Patient-ContactRank (to remove one of two instances of the same example with the same name)
</td>
</tr>

<tr>
<td>11th October 2021</td>
<td>0.2.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 0.2.0 - STU1 - Version of the UK Core Implementation Guide from Sprint 4 of Clinical and Technical Assurance</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
Added the Profiles and associated FHIR assets required for Sprint 4 of C&TA
<ul>
<li>MessageHeader</li>
<li>OperationOutcome</li>
<li>Encounter</li>
<li>EpisodeOfCare</li>
<li>Composition</li>
<li>Condition</li>
<li>Procedure</li>
<li>List</li>
<li>RelatedPerson</li>
</ul>
</td>
</tr>

<tr id="010">
<td>10th September 2021</td>
<td>0.1.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 0.1.0 - First release of UK Core STU1 sequence, contains the content from Clinical and Technical Assurance </td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li>First release of UK Core STU1 sequence.</li>
</ul>
</td>
</tr>

</table>