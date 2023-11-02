## {{page-title}}

<table class="assets" title="STU2 Sequence release list">
<tr>
<th class="width05">Date</th>	
<th class="width10">IG Version</th>
<th class="width05">FHIR Version</th>	
<th class="Width50">Description</th>	
</tr>

<tr>
<td>23rd June 2023</td>
<td>1.1.3</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.1.3 - STU2 for Ballot</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li>Fixes to name/title element on <code>Extension-UKCore-CodingSCTDescDisplay</code>, <code>Extension-UKCore-CollectionCollector</code>, <code>Extension-UKCore-OutcomeOfAttendance</code>, <code>UKCore-Observation-LabGroup</code>, <code>ValueSet-UKCore-BiopsyState</code></li>
<li>Fix on incorrect wording in code tag on <code>ImagingStudy.series.performer.actor</code></li> 
<li>Fix on submenu creation on mobile devices</li> 
<li>Added ballot box on <code>Extension-UKCore-SampleCategory</code></li> 
<li>Added<code>UKCore-MessageHeader</code> to Profile Index page lists</li> 
<li>Fixed incorrect Alphabetical listing headers from A-D,D-L,M-P,P-Z to A-D,E-L,M-P,Q-Z</li> 
<li>Adjusted wording from Ballot 2, to STU2 ballot</li> 
</ul>
</tr>

<tr>
<td>25th May 2023</td>
<td>1.1.2</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.1.2 - STU2 Pre-Release For Ballot 2</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li>Added draft C&TA Sprint 6 Profiles (<code>UKCore-Consent</code>, <code>UKCore-DiagnosticReport</code>, <code>UKCore-FamilyMemberHistory</code>, <code>UKCore-ImagingStudy</code>, <code>UKCore-Observation</code>, <code>UKCore-Specimen</code>) and associated Extensions, ValueSets, and CodeSystems.<br><br></li>

<li>For <code>UKCore-DiagnosticReport</code>:
    <ul>
        <li>Added a Derived Profile: <code>UKCore-DiagnosticReport-Lab</code></li>
        <li>Removed slices on <code>category</code>, <code>code</code>, <code>conclusionCode</code></li>
        <li>Added Extension <code>UKCore-DeviceReference</code></li>
        <li>Added backported R5 elements as proxy extensions using R5 url's for <code>note</code>, <code>composition</code></li>
        <li>Reverted <code>code</code> binding from <code>UKCore-FindingCode</code> to base ValueSet as they were identical</li>
    </ul>
</li>
<li>For <code>UKCore-FamilyMemberHistory</code>:
    <ul>
        <li>Added a existing Extension <code>UKCore-AssociatedEncounter</code></li>
        <li>Added backported R5 element as proxy extensions using R5 url's for <code>participant</code></li>
        <li>Bound <code>relationship</code> to ValueSet <code>UKCore-PersonRelationshipType</code></li>
        <li>Existing base bindings have been assured, and strength raised to preferred or extensible, in line with the Design and Development Approach</li>
        <li>Retired draft Extension <code>UKCore-Recorder</code>, as this is replaced by backported R5 element <code>participant</code></li>
    </ul>
</li>
<li>For <code>UKCore-Observation</code>:
    <ul>
        <li>Added Derived Profiles: <code>UKCore-Observation-LabGroup</code> and <code>UKCore-Observation-Lab</code></li>
        <li>Removed slices on <code>code</code>, <code>bodySite</code></li>
        <li>Reverted <code>bodySite</code> binding from <code>UKCore-BodySite</code> to base ValueSet as they were identical</li>
        <li>Addded backported R5 element as proxy extensions using R5 url's for <<code>triggeredBy</code></li>
    </ul>
</li>
<li>For <code>UKCore-Specimen</code>:
    <ul>
        <li>Removed slices on <code>type</code>, <code>collection.bodySite</code></li>
        <li>Added Extension <code>UKCore-SampleCategory</code></li>
        <li>Added Extension <code>UKCore-BodySiteReference</code>, to replicate CodeableReference allowed in R5</li>
        <li>Added backported R5 element as proxy extensions using R5 url's for <code>collection.collector</code>, to replicate additional references allowed in R5</li>
        <li>Added ValueSet <code>UKCore-SpecimenCondition</code>, bound to <code>condition</code>, which extends the base ValueSet, with CodeSystem <code>UKCore-BiopsyState</code></li>
    </ul>
</li>
<li>For <code>UKCore-ServiceRequest</code>:
    <ul>
        <li>Added Derived Profiles: <code>UKCore-ServiceRequest-Lab</code></li>
        <li>Added Extensions <code>UKCore-AdditionalContact</code>, <code>UKCore-PriorityReason</code>, <code>UKCore-Coverage</code></li>
        <li>Added an open slice to <code>category</code>, discriminated by <code>coding.system</code>, to the ValueSet <code>UKCore-GenomicsSequencingCategory</code></li>
    </ul>
</li>
<li>For <code>UKCore-Patient</code>:
    <ul>
        <li>Added Extension <code>UKCore-NHSNumberUnavailableReason</code></li>
    </ul>
</li>
<li>For <code>UKCore-Organization</code>:
    <ul>
        <li>Added ValueSet <code>UKCore-OrganizationType</code>, bound to <code>type</code>, which extends the base ValueSet, with CodeSystem <code>UKCore-OrganizationTypeGenomics</code></li>
    </ul>
<br></li>

<li>Added guidance to clarify that using the FHIR UK Core also requires the base specification, following feedback from implementers.</li>
<li>Added guidance and snippet example for sending a local language translation, following feedback from implementers.</li>
<li>Added canonical urls to Extension and Profile pages via FQL, following feedback from implementers.</li>
<li>Added last updated date and version to Profile pages via FQL, following feedback from implementers.</li>
<li>Added the display of CodeSystem descriptions via FQL, following feedback from implementers.</li>
<li>Added alternative alphabetical/by sprint/by resource renderings of the Extensions, Profiles, and ValueSet/CodeSystem indexes, following feedback from implementers.<br><br></li>

<li>Updated all draft sprint 6 assets to active status.</li>
<li>Updated Extension and CodeSystem sub pages to use FQL to display the description, to improve IG consistency.</li>
<li>Updated the name of ValueSet <code>UKCore-ReportCodeSnCT</code> to <code>UKCore-ReportCode</code>.</li>
<li>Updated CodeSystem descriptions, where the CodeSystem is populated from Data Dictionary sources to include markdown links, following feedback from implementers.</li>
<li>Updated ValueSet <code>UKCore-SpecimenType</code>, added during CTA sprint 6, to include descendantOf 123037004 | Body structure and descendantOf 123038009 | Specimen.<br><br></li>

<li>Improved consistency of the ordering of elements shown in Extension and Binding (differential) tables within the IG, following feedback from implementers.</li>
<li>Improved the table based render of examples, to generate html links between referenced examples.</li>
<li>Improved the drop down menu items for better navigation, and faster page loads.<br><br></li>

<li>Removed Hybrid / Differential tree views from the Extensions Library.</li>
</ul>
</td>
</tr>


<tr>
<td colspan="4"><b>R5 pre-adoption and Proxy Extensions</b>

HL7 guidance for using R5 elements in R4 as extensions exists: <a href="https://hl7.org/fhir/versions.html#extensions">https://hl7.org/fhir/versions.html#extensions</a>, but as of 19/05/2023, the package to enable pre-adopted elements to function as per the guidance, is not available. To enable rendering and vaidation of these pre-adopted elements, we have provided UK Core proxy extensions, as per the current threads on <a href="https://chat.fhir.org/#narrow/stream/179166-implementers/topic/R5.20Extensions.20for.20R4.3F">chat.fhir.org</a>. These proxy extensions match the R5 element as closely as possible, and contain the R5 canonical urls. These proxy extensions will be removed once the HL7 package is released.</td>  
</tr>

<tr>
<td>28th April 2023</td>
<td>1.1.1</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.1.0 - STU2 Draft Release</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<ul>
<li><b>BREAKING CHANGE</b>: Updated <code>Extension-UKCore-AdmissionMethod</code> to be expressed at <code>UKCore-Encounter.hospitalization</code> level.<br><br></li>

<li>Retired <code>UKCore-MedicationPrecondition</code> ValueSet, and reverted to base binding on <code>UKCore-MedicationDispense.dosageInstruction.asNeeded[x]</code>, <code>UKCore-MedicationRequest.dosageInstruction.asNeeded[x]</code>, <code>UKCore-MedicationStaement.dosage.asNeeded[x]</code> following terminology guidance, which resulted in the valueset matching the base ValueSet.</li>
<li>Retired <code>Extension-UKCore-AnestheticIssues</code> on <code>UKCore-Procedure</code>, as this extension was not deemed appropriate for use, as it can be represented through the use of the existing resources and profiles, <code>UKCore-AllergyIntelorance</code>
and <code>AdverseEvent</code>.</li>
<li>Retired <code>Extension-UKCore-ActualProblem</code>, <code>Extension-UKCore-ProblemSignificance</code>, <code>Extension-UKCore-RelatedClinicalContent</code>, <code>Extension-UKCore-RelatedProblemHeader</code> as these extensions were deemed to be England and GPConnect specific.</li>
<li>Retired <code>Extension-UKCore-MessageHeaderInstruction</code> as the CodeSystem was empty, and the extension was deemed to be England specific.<br><br></li>

<li>Removed the retired extensions mentioned above from <code>UKCore-Condition</code> and <code>UKCore-List</code>.</li>
<li>Removed <code>UKCore-BodySite</code> ValueSet binding, and reverted to base binding on <code>UKCore-Condition.bodySite</code>, <code>UKCore-Procedure.bodySite</code>, <code>UKCore-ServiceRequest.bodySite</code> as the contents matches the base ValueSet.</li>
</ul>
</td>
</tr>

<tr>
<td>1st March 2023</td>
<td>1.1.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide 1.1.0 - STU2 Pre-Release for Ballot</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>

<ul>
<li>Added C&TA Sprint 4 Profiles (<code>UKCore-Composition</code>, <code>UKCore-Condition</code>, <code>UKCore-Encounter</code>, <code>UKCore-EpisodeOfCare</code>, <code>UKCore-List</code>, <code>UKCore-MessageHeader</code>, <code>UKCore-OperationOutcome</code>,<code>UKCore-Procedure</code>, <code>UKCore-RelatedPerson</code>) and associated Extensions, ValueSets, and CodeSystems</li>
<li>Added C&TA Sprint 5 Profiles (<code>UKCore-Appointment</code>, <code>UKCore-Flag</code>, <code>UKCore-HealthcareService</code>, <code>UKCore-Questionnaire</code>, <code>UKCore-QuestionnaireResponse</code>, <code>UKCore-Schedule</code>, <code>UKCore-ServiceRequest</code>, <code>UKCore-Slot</code>, <code>UKCore-Task</code>) and associated Extensions, ValueSets, and CodeSystems.
<br><br></li>

<li>Added missing publisher values to <code>Extension-UKCore-DeliveryChannel</code>, and <code>Extension-UKCore-RelatedClinicalContent</code>.</li>
<li>Added new CodeSystem, and ValueSet <code>UKCore-MedicationAdministrationCategory</code>, extending the FHIR International <code>medication-admin-category</code> ValueSet with a <code>discharge</code> code, and set as "extensible" against <code>UKCore-MedicationAdministration.category</code> at the request of Digital and Interoperable Medicines.</li>
<li>Added new <code>primarycare</code> code to CodeSystem, and ValueSet <code>UKCore-MedicationRequestCategory</code> at the request of Digital and Interoperable Medicines.</li>
<li>Added SNOMED CT concept <code>419841000001106 | "Clinical trial medication"</code> as an include in ValueSet <code>UKCore-MedicationCode</code> at the request of Digital and Interoperable Medicines.</li>
<li>Added SNOMED CT concepts <code>429060002 | "Procedure to meet occupational requirement"</code>, and <code>281657000 | "Travel vaccinations"</code> as an include in ValueSet <code>UKCore-ImmunisationExplanationReason</code> following clinical review.
<br><br></li>

<li>Updated CodeSystem <code>UKCore-PersonMaritalStatusEngland</code> to add missing codes, and ValueSet <code>UKCore-PersonMaritalStatusCode</code> to filter codes in order to remove duplicaton of FHIR International codes (retroactively added to 1.0.1 as well)</li>
<li>Removed Extension <code>UKCore-ContactRank</code> from the <code>UKCore-RelatedPerson</code> Profile (retroactively added to 1.0.1 as well)</li>
<li>Updated all contact tags in all Profiles, Extensions, ValueSets, and CodeSystems (retroactively added to 1.0.1 as well)</li>
<li>Updated <code>UKCore-MedicationCode</code> ValueSet binding strength from "extensible" to "preferred" on <code>UKCore-Medication</code>, <code>UKCore-MedicationAdministration</code>, <code>UKCore-MedicationDispense</code>, <code>UKCore-MedicationRequest</code>, <code>UKCore-MedicationStatement</code> (retroactively added to 1.0.1 as well)
<br><br></li>

<li>Updated all Profile description and purpose elements after clinical review, and included markdown links to enable FQL use in the IG.</li>
<li>Updated <code>UKCore-MessageHeader.event[x]</code> binding strength from "extensible" to "example", retired empty CodeSystem <code>UKCore-MessageEvent</code>, and updated ValueSet <code>UKCore-MessageEvent</code> to include and expand 2 NHS CodeSystems for message events.</li>
<li>Updated the binding strength of all ValueSets which primarily include concepts from SNOMED CT or dm+d, from "extensible" to "preferred".</li>
<li>Updated <code>UKCore-Appointment</code>, <code>UKCore-HealthcareService</code>, <code>UKCore-Schedule</code>, <code>UKCore-Slot</code> to bind their <code>specialty</code> element to  ValueSet <code>UKCore-PracticeSettingCode</code>, in line with <code>UKCore-PractitionerRole</code>.</li>
<li>Updated <code>UKCore-PractitionerRole.healthcareService</code> to replace the reference to HealthcareService with <code>UKCore-HealthcareService</code>.</li>
<li>Updated <code>UKCore-Procedure.instantiatesCanonical</code> to replace the reference to Questionnaire with <code>UKCore-Questionnaire</code>.</li>
<li>Updated ValueSet <code>UKCore-ConditionEpisodicity</code> to use the <code>https://fhir.hl7.org.uk/CodeSystem/UKCore-ConditionEpisodicity</code> system url instead of the old <code>https://fhir.nhs.uk/R4/CodeSystem/UKCore-ConditionEpisodicity</code> url.</li>
<li>Updated ValueSet <code>UKCore-ListWarningCode</code> to use the <code>https://fhir.hl7.org.uk/CodeSystem/UKCore-ListWarningCode</code> system url instead of the old <code>https://fhir.nhs.uk/R4/CodeSystem/UKCore-ListWarningCode</code> url.</li>
<li>Updated the minimum cardinality of the value[x] element on the following Extensions: <code>UKCore-ActualProblem</code>, <code>UKCore-BookingOrganization</code>, <code>UKCore-DeliveryChannel</code>, <code>UKCore-EncounterTransport (retired)</code>, <code>UKCore-LegalStatus</code>, <code>UKCore-ProblemSignificance</code>, <code>UKCore-RelatedClinicalContent</code>, <code>UKCore-RelatedProblemHeader</code>, in line with UK Core Design and Development Approach.<br><br></li>

<li>Removed filtering of FHIR International CodeSystem <code>medication-statement-category</code> codes in ValueSet <code>UKCore-MedicationStatementCategory</code>.<br><br></li>

<li>Fully qualified guidance within an IG page to include the resource, so it reads as <code>resource.element</code> rather than just <code>element</code>.</li>
</ul>
</tr>

<tr>
<td colspan="4"><b>dm+d and SNOMED CT Binding strength</b>

For most clinical data exchanges dm+d or SNOMED CT is the expected CodeSystem to use and this was why historically the ValueSet binding strength for these systems was set as 'extensible', however there are many use cases where this is not possible. For example:

- The data is historical and previously coded in another terminology such as READ,
- The sending system does not support dm+d or SNOMED CT,
- Finding a valid alternative dm+d or SNOMED CT code for one that is not in the CodeSystem is labour intensive due to the size of these CodeSystems.

For these reasons it has been decided to reduce the binding strength for all ValueSets containing dm+d or SNOMED CT codes to 'preferred'. </td>  
</tr>

</table>