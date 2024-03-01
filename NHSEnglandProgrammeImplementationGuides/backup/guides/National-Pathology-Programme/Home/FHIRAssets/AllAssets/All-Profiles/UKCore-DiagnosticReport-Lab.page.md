---
topic: R4DiagnosticReport
---
## R4 Profile: UKCore-DiagnosticReport-Lab

### Summary
A test report, containing the overall findings and clinical interpretation relating to one or more pathology tests. The report may reference individual test results, test groups or a combination of these.

Test results and test groups are defined as FHIR <code>Observations</code> and are referenced from <code>DiagnosticReport</code> using <code>DiagnosticReport.result</code>.

For information on how test results and test groups are represented, refer to the profile descriptions for {{pagelink:R4ObservationTestResult}} and {{pagelink:R4ObservationTestGroup}}. 

### Resource and Profile Links
* R4 Resource (Base): [DiagnosticReport](https://hl7.org/fhir/R4/diagnosticreport.html)
* R4 UK Core Profile (Lab): [UKCore-DiagnosticReport-Lab](https://simplifier.net/hl7fhirukcorer4/ukcore-diagnosticreport-lab)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, snapshot}}
</div>

<div id="Differential View" class="tabcontent"></h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab, hybrid}}
</div>

### Additional Guidance
The following table includes additional guidance that should be followed when implementing the `UKCore-DiagnosticReport-Lab` profile. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings.

An example of how each supported data element may be populated is provided in {{pagelink:R4SnippetsDiagnosticReport}}.

<table class="regular">
    <thead>
        <tr>
            <th width="15%">Element Name</th>
            <th width="10%">Profile Cardinality</th>
            <th width="10%">Domain Cardinality</th>
            <th width="10%">Domain Optionality</th>
            <th width="10%">Type</th>
            <th width="45%">Definition, Constraints and Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#uri">uri</a></td>
            <td>The canonical URL for the <code>UKCore-DiagnosticReport-Lab</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport-Lab</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..*</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Identifier">Identifier</a></td>
            <td>This <b>SHALL</b> be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and is therefore stored with the source data). This <b>SHALL</b> be scoped by a provider specific namespace for the identifier.<br><br>Where consuming systems are integrating data from this resource to their local system, they <b>SHALL</b> also persist this identifier at the same time.</td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>ServiceRequest</code> that contains details of the test request that was made. Where present this may include details of who requested the tests and why the test was requested.<br><br>As currently test requests are not submitted in a FHIR format this is not the original request but it is used as a container to hold details that were present in the original request.</td>
        </tr>
        <tr>
            <td>status</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#code">code</a></td>
            <td>The status of the test report. This <b>SHALL</b> be populated as follows: 
                <ul>
                    <li><code>partial</code>: when the report is issued on an initial, interim or preliminary basis, for example because some of the requested tests have not yet completed</li>
                    <li><code>final</code>: when the report is completed.</li>
                    <li><code>unknown</code>: when the status is unable to be determined</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td>category</td>
            <td>1..*</td>
            <td>1..*</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The general type of test report. This <b>SHALL</b> be populated with a fixed value of category code <code>LAB</code> for <code>Laboratory</code>.<br><br>If required, additional category codes <b>MAY</b> also be included.</td>
        </tr>
        <tr>
            <td>code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>This <b>SHALL</b> be populated with a fixed value of SNOMED CT ConceptID <code>721981007</code> for <code>Diagnostic studies report</code>.<br><br><b>Note: </b>The clinical code and name of a test result or a test group is defined in the <code>code</code> element of the relevant <code>Observation</code> resource.</td>
        </tr>
        <tr>
            <td>subject</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the test report relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>issued</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test report was issued.</td>
        </tr>
        <tr>
            <td>performer</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code>, <code>Practitioner</code> or <code>PractitionerRole</code> that produced the test report.</td>
        </tr>
        <tr>
            <td>specimen</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the <code>Specimen(s)</code> used for testing.</td>
        </tr>
        <tr>
            <td>result</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the results included in the test report. This may contain references to individual test results, test groups or a combination of these. Test results and test groups are defined as <code>Observations</code>.<br><br>Test results which are part of a test group will not be referenced by this element; the reference will be to the test group which will in turn reference the associated test results. Refer to the {{pagelink:DesignOverview}} for further information.</td>
        </tr>
            <tr>
            <td>conclusion</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>A clinical interpretation/summary of the test results in a text format.<br><br>Notes may be captured at a number of levels within a test report. There may also be notes related to the specimen, test group or individual test result. It is the consuming systems responsibility to make sure all relevant notes are displayed to the user.</td>
        </tr>
        <tr>
            <td>conclusionCode</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>A coded finding of the test report. Produced by the organisation that performed the tests.</td>
        </tr>
        <tr>
            <td>encounter</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#dateTime">dateTime</a> | <a href="https://hl7.org/fhir/R4/datatypes.html#Period">Period</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>resultsInterpreter</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>imagingStudy</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>media</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>presentedForm</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Attachment">Attachment</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>    
    </tbody>
</table>

<br>