---
topic: STU3DiagnosticReport
---
## STU3 Profile: CareConnect-DiagnosticReport-1

### Summary
A test report, containing the overall findings and clinical interpretation relating to one or more pathology tests. The report may reference individual test results, test groups or a combination of these.

Test results and test groups are defined as <code>Observations</code> and are referenced from <code>DiagnosticReport</code> using <code>DiagnosticReport.result</code>.

For information on how test results and test groups are represented, refer to the profile descriptions for {{pagelink:STU3ObservationTestResult}} and {{pagelink:STU3ObservationTestGroup}}.

### Related Links
* STU3 Resource: [DiagnosticReport](http://hl7.org/fhir/STU3/diagnosticreport.html)
* STU3 CareConnect Profile: [CareConnect-DiagnosticReport-1](https://simplifier.net/HL7FHIRCareConnectBaselineforSTU3/CareConnect-DiagnosticReport-1)

### Profile Views
Refer to {{pagelink:ProfileDescriptions}} for a definition of the different profile view formats.
<div class="tab fhirTree">
    <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
    <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
    <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
    <h4>Snapshot View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
    <h4>Differential View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
    <h4>Hybrid View</h4>
    {{tree:https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1, hybrid}}
</div>

### Conformance Rules
The following table describes additional conformance rules and constraints that should be applied when implementing the `CareConnect-DiagnosticReport-1` profile as part of this specification. It should be used in conjunction with the profile definition included above. Refer to {{pagelink:ProfileDescriptions}} for a definition of the table column headings. 

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
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#id">id</a></td>
            <td>The logical identifier for the resource instance.</td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td>0..*</td>
            <td><code>1..1<code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#uri">uri</a></td>
            <td>The canonical URL for the <code>CareConnect-DiagnosticReport-1</code> profile.<br><br>This <b>SHALL</b> be populated with the following fixed value:<br><code>https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-DiagnosticReport-1</code></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..*</code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#Identifier">Identifier</a></td>
            <td>This <b>SHALL</b> be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and is therefore stored with the source data). This <b>SHALL</b> be scoped by a provider specific namespace for the identifier.<br><br>Where consuming systems are integrating data from this resource to their local system, they <b>SHALL</b> also persist this identifier at the same time.</td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>ProcedureRequest</code> that contains details of the test request that was made. Where present this may include details of who requested the tests and why the test was requested.<br><br>As currently test requests are not submitted in a FHIR format this is not the original request but it is used as a container to hold details that were present in the original request.</td>
        </tr>
        <tr>
            <td>status</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#code">code</a></td>
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
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>The general type of test report. This <b>SHALL</b> be populated with a fixed value of category code <code>LAB</code> for <code>Laboratory</code>.</td>
        </tr>
        <tr>
            <td>code</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>This <b>SHALL</b> be populated with a fixed value of SNOMED CT ConceptID <code>721981007</code> for <code>Diagnostic studies report</code>.<br><br>The clinical code and name of a test result or a test group is defined in the <code>code</code> element of the relevant <code>Observation</code> resource.</td>
        </tr>
        <tr>
            <td>subject</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Reference to the subject that the test report relates to. This is usually (but not always) a <code>Patient</code>.</td>
        </tr>
        <tr>
            <td>issued</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>Mandatory</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#instant">instant</a></td>
            <td>The date and time that the test report was issued.</td>
        </tr>
        <tr>
            <td>performer</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Reference to the <code>Organization</code> or <code>Practitioner</code> that produced the test report. A <code>Practitioner</code> resource may be referenced here but only where an <code>Organization</code> is provided.</td>
        </tr>
        <tr>
            <td>specimen</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the <code>Specimen(s)</code> used for testing.</td>
        </tr>
        <tr>
            <td>result</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Reference(s) to the results included in the test report. This may contain references to individual test results, test groups or a combination of these. Test results and test groups are defined as <code>Observations</code>.<br><br>Test results which are part of a test group will not be referenced by this element; the reference will be to the test group which will in turn reference the associated test results. Refer to the design guidance for {{pagelink:DesignRelatedTests}} for further information.</td>
        </tr>
        <tr>
            <td>conclusion</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#string">string</a></td>
            <td>A clinical interpretation/summary of the test results in a text format.<br><br>Notes may be captured at a number of levels within a test report. There may also be notes related to the specimen, test group or individual test result. It is the consuming systems responsibility to make sure all relevant notes are displayed to the user.</td>
        </tr>
        <tr>
            <td>codedDiagnosis</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Required</td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#CodeableConcept">CodeableConcept</a></td>
        <td>A coded finding of the test report. Produced by the organisation that performed the tests.</td>
        </tr>
        <tr>
            <td>context</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>  
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#dateTime">dateTime</a> | <a href="http://hl7.org/fhir/stu3/datatypes.html#Period">Period</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>imagingStudy</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="http://hl7.org/fhir/stu3/references.html#2.3.0">Reference</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>image</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="http://hl7.org/fhir/stu3/backboneelement.html">BackboneElement</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>
        <tr>
            <td>presentedForm</td>
            <td></td>
            <td></td>
            <td></td>
            <td><a href="http://hl7.org/fhir/stu3/datatypes.html#Attachment">Attachment</a></td>
            <td>Currently out of scope - element <b>SHALL NOT</b> be populated.</td>
        </tr>    
    </tbody>
</table>

<br>