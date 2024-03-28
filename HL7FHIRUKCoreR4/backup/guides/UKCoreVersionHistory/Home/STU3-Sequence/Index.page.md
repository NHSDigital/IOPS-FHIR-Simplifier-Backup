---
topic: STU3Sequence
---
## {{page-title}}

<table class="assets" title="STU3 Sequence release list">
<tr>
<th class="width05">Date</th>	
<th class="width10">IG Version</th>
<th class="width05">FHIR Version</th>	
<th class="Width50">Description</th>	
</tr>
<tr>
<td>Ongoing</td>
<td>draft</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide STU3 Sequence</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<br>
<b>General IG improvements:</b><br>
<ul>
<li>Added MustSupport flag to <code>UKCore-Patient.managingOrganization</code>, to give IHE alignment</li>
<li>Swap Example, ValueSet, CodeSystem, Extension, and Profile pages to use Simplifier templating</li>
<li>Updated all examples to have text elements, to describe what they are used for, and render this via the Simplifier template</li>
<li>Altered Profiles sub menu from on hover opening to click to show</li>
<li>Altered Profiles sub menu to restore its state via cookie</li>
<li>Altered Profiles sub menu to have a sub menu for derived profiles</li>
<li>Added cookie consent pop-up</li>
<li>Added Detailed View to Profile tabs</li>
<li>Added Feedback to tabs, which links to the relevant Simplifier issues page to raise an issue for the asset</li>
<li>Added "View UK Core guidance" link in pinnable panel, for elements where additional guidance is detailed on a page</li>
<li>Added "or UK Core equivalent profile" guidance in pinnable panel, for Reference datatype elements where the resources include a UK Core profile</li>
<li>Added clickable element headers, that show / hide the relevant element details from the Detailed view</li>
<li>Clicking an element in the left-hand navigation list automatically displays the detailed view as per the above item</li>
<li>Added configurable display options for displaying a UK Code profile within an iframe</li>
<li>Added configurable display options to highlight specific sections of an example</li>
</ul>
<b>C&TA Sprint 7 Assets:</b><br>
<ul>
<li>Changed proposed assets from draft to active</li>
<li>value[x] and specimen cardinality set to 0..0 on <code>UKCore-Observation-AverageBloodPressure</code> and <code>UKCore-Observation-VitalSigns-BloodPressure</code></li>
<li>Revised and simplified ECL's, and expansion of the ValueSet contents</li>
<li>Improved description and purpose of added profiles</li>
<li>Altered binding strength on <code>Observation.method</code> to bring it in line with UK Core Design and Development Approach</li>
<li>Improved cardinality on LOINC / SNOMED CT, and systolicBP / diastolicBP slices</li>
<li>Moved LOINC / SNOMED CT slicing on Observation.component from <code>UKCore-Observation-VitalSigns</code> to <code>UKCore-Observation-VitalSigns-BloodPressure</code> as they only applied for this derived profiles</li>
<li>Improved guidance on the use of code, value[x], and component elements for <code>UKCore-Observation-AverageBloodPressure</code> and <code>UKCore-Observation-VitalSigns-BloodPressure</code></li>
</ul>
<b>STU2 Sequence Ballot Assets:</b><br>
<ul>
<li>Synchronization of STU2 Ballot reconciliation actions into STU3 assets and implementation guidance - this includes multiple <b>BREAKING CHANGES</b>, for more details, see {{pagelink:STU2Sequence}}</li>
</ul>
</tr>

<tr>
<td>20th Sept 2023</td>
<td>1.7.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide STU3 Sequence - Sprint 7 Review</td>
</tr>
<tr>
<td colspan="4"><b>Changes for this version</b>
<br>
<br>
<b>General IG improvements:</b><br>
<ul>
<li>Extension based example id's and filenames have been updated</li>
<li>Example sub pages have made consistent regarding the presence of Tree View</li>
<li>New Examples Index page, showing examples alphabetically based on their type (profile / extension), the sprint they were added in, and a summary for all examples per resource type</li>
<li>NHS Digital IG style sort buttons have been added to CodeSystem / ValueSet tables</li>
<li>Intelligent expansion of tree nodes, to ensure altered nodes are displayed</li>
<li>Intelligent redirection within Profile tree views, to UK Core guidance pages for referenced profiles / extensions, and bound valuesets</li>
<li>Intelligent auto hiding of expanded ValueSets, with a clickable 'concepts' link to show / hide the table</li>
<li>Intelligent redirection of SNOMED CT concepts in examples and ValueSet tables to the SNOMED CT UK Terminology Browser</li>
<li>CSS and HTML id changes to improve Web Accessibility</li>
<li>Fix unclosed tables causing Bindings to appear incorrectly</li>
<li>Add missing FQL for UKCore-ServiceRequest-Lab details</li>
<li>Added links to raise issues, on new assets callout box</li>
<li>Added Usage view to Profile tabs</li>
<li>Swapped Snapshot/Differential/Hybrid renders to the new single Simplifier render with swappable view buttons</li>
</ul>
<b>C&TA Sprint 7 Proposals:</b><br>
<ul>
<li>Changes to the existing draft <code>UKCore-Observation-VitalSigns</code> derived profile</li>
<li>Addition of draft proposed profiles for vital signs: Blood Pressure, BMI, Head Circumference, Heart Rate, Height, Oxygen Saturation, Respiratory Rate, Temperature, and Weight, derived from <code>UKCore-Observation-VitalSigns</code></li>
<li>Addition of draft proposed profiles for clinical observations: ACVPU, Alcohol Consumption, Blood Glucose, Early Warning Total Score, Inspired Oxygen, Tobacco Consumption, derived from <code>UKCore-Observation</code></li>
<li>Addition of associated draft proposed Extensions, CodeSystems, and ValueSets</li>
<li>Addition of guidance for draft <code>UKCore-Device</code> profile, along with draft proposed <code>UKCore-Device-BloodPressure</code></li>
</tr>

<tr>
<td>27th February 2023</td>
<td>1.6.0</td>
<td>4.0.1</td>
<td>UK Core Implementation Guide STU3 Sequence - Sprint 6 Review</td>
</tr>
<tr>
<td colspan="4"><b>Note:</b> This content has since been added to the STU2 Sequence, and this version is listed for historic purposes only
<br><br>
<b>Changes for this version</b>
<ul>
<li>Added draft C&TA Sprint 6 Profiles (<code>UKCore-Consent</code>, <code>UKCore-DiagnosticReport</code>, <code>UKCore-FamilyMemberHistory</code>, <code>UKCore-ImagingStudy</code>, <code>UKCore-Observation</code>, <code>UKCore-Specimen</code>) and associated Extensions, ValueSets, and CodeSystems.<br><br></li>

<li>For <code>UKCore-DiagnosticReport</code>:
    <ul>
        <li>Added a Derived Profile: <code>UKCore-DiagnosticReport-Lab</code></li>
        <li>Removed slices on <code>category</code>, <code>code</code>, <code>conclusionCode</code></li>
        <li>Added Extension <code>UKCore-DeviceReference</code></li>
        <li>Added backported R5 elements as proxy extensions using R5 URL's for <code>note</code>, <code>composition</code></li>
        <li>Reverted <code>code</code> binding from <code>UKCore-FindingCode</code> to base ValueSet as they were identical</li>
    </ul>
</li>
<li>For <code>UKCore-FamilyMemberHistory</code>:
    <ul>
        <li>Added an existing Extension <code>UKCore-AssociatedEncounter</code></li>
        <li>Added backported R5 element as proxy extensions using R5 URL's for <code>participant</code></li>
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
        <li>Added backported R5 element as proxy extensions using R5 URL's for <code>triggeredBy</code></li>
    </ul>
</li>
<li>For <code>UKCore-Specimen</code>:
    <ul>
        <li>Removed slices on <code>type</code>, <code>collection.bodySite</code></li>
        <li>Added Extension <code>UKCore-SampleCategory</code></li>
        <li>Added Extension <code>UKCore-BodySiteReference</code>, to replicate CodeableReference allowed in R5</li>
        <li>Added backported R5 element as proxy extensions using R5 URL's for <code>collection.collector</code>, to replicate additional references allowed in R5</li>
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
</ul>
</td>
</tr>
</table>