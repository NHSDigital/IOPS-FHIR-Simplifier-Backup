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
<ul>
<li>Swap Examples to Simplifier templating</li>
<li>Swap ValueSets to Simplifier templating</li>
</ul>
<br>
<ul>

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
<li>NHS England IG style sort buttons have been added to CodeSystem / ValueSet tables</li>
<li>Intelligent expansion of tree nodes, to ensure altered nodes are displayed</li>
<li>Intelligent redirection withing Profile tree views, to guidance pages for referenced profiles / extensions, and bound valuesets</li>
<li>Intelligent auto hiding of expanded ValueSets, click the 'concepts' link to show / hide the table</li>
<li>CSS and HTML id changes to improve Web Accessibility</li>
<li>Fix unclosed tables causing Bindings to appear incorrectly</li>
<li>Add missing FQL for UKCore-ServiceRequest-Lab details</li>
</ul>
<b>Sprint 7 Proposals:</b><br>
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
<td colspan="4"><b>Note:</b> This content has snce been added to the STU2 Sequence
<br><br>
<b>Changes for this version</b>
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
</ul>
</td>
</tr>
</table>