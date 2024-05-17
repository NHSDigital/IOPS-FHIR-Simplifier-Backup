---
topic: DesignOverview
---
## Design Overview

### Pathology Business Information Model and FHIR Profile Mapping
The following diagram is a high-level logical representation of the key business entities relating to pathology test requesting and reporting:

{{render:path-diagram-information-model}}

To aid clarity, individual and organisation type entities (e.g. Performer / Performing Organisation) have been combined in the diagram but may be referenced independently. Each business entity is summarised below, together with links to the corresponding FHIR R4 resource (as defined in the base [FHIR R4 specification](https://hl7.org/fhir/R4/)) and FHIR UK Core R4 profile (as described in the {{pagelink:FHIRAssetsR4Profiles}} section of this implementation guide).

<table class="regular">
    <thead>
        <tr>
            <th width="20%">Business Entity Name</th>
            <th width="45%">Description</th>
            <th width="15%">FHIR R4 Resource</th>
            <th width="25%">FHIR UK Core R4 Profile</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Test Request Summary</td>
            <td>A summary of the original test request that is returned with the <b>Test Report</b>.</td>
            <td><a href="https://hl7.org/fhir/R4/servicerequest.html">ServiceRequest</a></td>
            <td>{{pagelink:R4ServiceRequest}}</td>         
        </tr>
        <tr>
            <td>Specimen</td>
            <td>Details relating to the specimen(s) provided for testing.</td>
            <td><a href="https://hl7.org/fhir/R4/specimen.html">Specimen</a></td>
            <td>{{pagelink:R4Specimen}}</td>
        </tr>
        <tr>
            <td>Test Report</td>
            <td>The overall findings and clinical interpretation relating to one or more pathology tests or investigations. The report may reference individual <b>Test Results</b>, <b>Test Groups</b> or a combination of these.</td>
            <td><a href="https://hl7.org/fhir/R4/diagnosticreport.html">DiagnosticReport</a></td>
            <td>{{pagelink:R4DiagnosticReport}}</td>
        </tr>
        <tr>
            <td>Test Group</td>
            <td>A set of related tests, for example a Full Blood Count. <b>Test Groups</b> are often referred to as batteries, panels or profiles. Multiple levels of <b>Test Groups</b> and <b>Test Results</b> may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity reports.</td>
            <td><a href="https://hl7.org/fhir/R4/observation.html">Observation</a></td>
            <td>{{pagelink:R4ObservationTestGroup}}</td>
        </tr>
        <tr>
            <td>Test Result</td>
            <td>A single test result. Includes the name and associated SNOMED CT code for the test (e.g. “Glucose substance concentration in plasma” – 1110521000000108) and the result, with an accompanying unit of measure where appropriate (e.g. 4.8 mmol/L).</td>
            <td><a href="https://hl7.org/fhir/R4/observation.html">Observation</a></td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
        </tr>
        <tr>
            <td>Patient</td>
            <td>Demographics and other administrative information relating to a patient.</td>
            <td><a href="https://hl7.org/fhir/R4/patient.html">Patient</a></td>
            <td>{{pagelink:R4Patient}}</td>
        </tr>
        <tr>
            <td rowspan="2">Requester</td>
            <td rowspan="2">Details relating to the individual that requested a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Requesting Organisation </td>
            <td>Details relating to the organisation that requested a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
        <tr>
            <td rowspan="2">Specimen Collector</td>
            <td rowspan="2">Details relating to the individual that collected a specimen.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Specimen Collecting Organisation</td>
            <td>Details relating to the organisation that collected a specimen.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
        <tr>
            <td rowspan="2">Performer</td>
            <td rowspan="2">Details relating to the individual that performed a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/practitioner.html">Practitioner</a></td>
            <td>{{pagelink:R4Practitioner}}</td>
        </tr>
        <tr>
            <td><a href="https://hl7.org/fhir/R4/practitionerrole.html">PractitionerRole</a></td>
            <td>{{pagelink:R4PractitionerRole}}</td>
        </tr>
        <tr>
            <td>Performing Organisation</td>
            <td>Details relating to the organisation that performed a pathology test.</td>
            <td><a href="https://hl7.org/fhir/R4/organization.html">Organization</a></td>
            <td>{{pagelink:R4Organization}}</td>
        </tr>
    </tbody>
</table>

---

### Pathology FHIR Data Model
The following diagram shows the key relationships between each of the pathology related FHIR resources (and associated profiles). It provides a detailed represention of how the high-level logical information model described above is realised in FHIR. The arrows represent the direction of the references between the resources.

{{render:path-diagram-R4-FHIR-data-model}}

---

### Design Approach
The base FHIR R4 specification describes several methods of representing test reports and  [grouping observations](https://hl7.org/fhir/R4/observation.html#obsgrouping). The design approach that has been adopted as part of this implementation guide is summarised below:

* `DiagnosticReport` contains the overall findings and clinical interpretation relating to one or more pathology tests.
* Test results and test groups are defined as `Observations` (using distinct profiles) and are referenced from `DiagnosticReport` using `DiagnosticReport.result`.
* `Observation.hasMember` relationships are used to link test result `Observations` to the associated test group `Observation`.
* Multiple levels of test group `Observations` and test result `Observations` may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MCS) reports.
* `ServiceRequest` is used to carry summary details relating to the test request that the test report was based on.
* If multiple tests or test groups are requested as part of the same “event” (generally by the same practitioner at the same time for the same subject), an instance of `ServiceRequest` is required for each requested test or test group. `ServiceRequest.requisition` acts as a common identifier to link the requests.
* The `Specimen.request` data element is used to reference the `ServiceRequest` that a specimen relates to. This should be used when a test was requested before the specimen was collected. 
* It is also possible to link a `ServiceRequest` to a specimen using the `ServiceRequest.specimen` data element. This should be used when a test is requested and the specimen has already been collected.

The following simplified data model illustrates the key aspects of this design approach for an example test report:

{{render:path-data-model-HbA1c-and-serum-lipid-levels-report}}

<br>
Further example test reports (with accompanying data models) are provided in the {{pagelink:R4Examples}}.

---

### SNOMED CT Usage
SNOMED CT concepts are used to populate the following key data elements in the FHIR profiles described in this implementation guide:

* The `code` element of {{pagelink:R4DiagnosticReport}} <b>SHALL</b> be populated using the following fixed SNOMED CT record artifact concept and description:
    * 721981007 | Diagnostic studies report
* The `code` element of {{pagelink:R4ObservationTestResult}} **SHALL** be populated using one of the following:
    * memberOf 1853551000000106 | PaLM (Pathology and Laboratory Medicine) observable entity simple reference set, OR
    * memberOf 999002881000000100 | PBCL (Pathology Bounded Code List) observables simple reference set
* The `code` element of {{pagelink:R4ObservationTestGroup}} **SHALL** be populated using one of the following:
    * memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
    * if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
    * if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the test group 
* The `code` element of {{pagelink:R4ServiceRequest}} **SHALL** be populated using one of the following:
    * memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
    * if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
    * if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the requested test or test group
* The `type` element of {{pagelink:R4Specimen}} **SHALL** be populated using one of the following:
    * descendantOf 105590001 | Substance (in which case `Specimen.collection.method` and `Specimen.collection.bodySite` **SHOULD** also be populated), OR
    * descendantOf 49755003 | Morphologically abnormal structure, OR
    * descendantOf 123037004 | Body structure, OR
    * descendantOf 123038009 | Specimen, OR
    * descendantOf 260787004 | Physical object

The use of these aspects of SNOMED CT is illustrated in the following simplified data model for an example test report:

{{render:path-data-model-HbA1c-and-serum-lipid-levels-with-SNOMED-report}}

<br>

Further information on the use of SNOMED CT for pathology reporting can be found on the  [Pathology Standards and Implementation website](https://digital.nhs.uk/services/pathology-standards-and-implementation/snomed-ct-for-pathology-reporting).

---

### Representation of Different Types of Test Results
Laboratory test results are reported using a variety of forms. These are described below with supporting examples. Each example includes a link to a corresponding FHIR `Observation` example (all of the examples are also listed in the {{pagelink:R4Examples}}).

* **Quantitative Result:** the result is expressed as a number, usually with an associated unit of measure. Comparators may be used to indicate that the actual value is greater than or less than the stated value. A range of values may be reported instead of a single value. Examples include:
    * {{pagelink:R4ObservationAlbumin}}: 47 g/L
    * {{pagelink:R4ObservationeGFR}}: >90 mL/min/1.73m2
* **Semi-quantitative Result:** the result is expressed using a descriptor to indicate the relative degree of positivity or negativity based on a scale. The scale is not always formally defined. Semi-quantitative results are widely used in microbiology, particularly for reporting microscopy and culture test results to indicate the amount or level of growth of organisms. Examples include:
    * {{pagelink:R4ObservationEpithelialCells}}: +
    * {{pagelink:R4ObservationNitrofurantoinSusceptibility}}: RESISTANT
* **Qualitative Result:** the result is expressed using a descriptor to indicate positivity or negativity. The descriptors are usually defined as pairs, for example: positive/negative, detected/not detected, isolated/not isolated. In this respect, qualitative results can be seen as a subset of semi-quantitative results in that they contain only two scale points to indicate positivity or negativity. Examples include:
    * {{pagelink:R4ObservationHBsAg}}: NEGATIVE
    * {{pagelink:R4ObservationMRSAScreeningTest}}: NOT DETECTED
* **Quantitative Result Combined with an Interpretation:** in some cases, a result may contain a combination of quantitative and non-quantitative elements. The non-quantitative element is sometimes expressed separately as an interpretation to provide a categorical assessment of the quantitative value. Examples include:
    * {{pagelink:R4ObservationLymphocyteCount}}: 0.70 10*9/L LOW
    * {{pagelink:R4ObservationRubellaIgGAntibody}}: >10 IU/ml DETECTED
* **Narrative Result:** the result is presented as text, for example:
    * {{pagelink:R4ObservationAerobicBloodCulture}}: No growth detected after 5 days incubation

The `Observation.value[x]` data element is used to represent the test result value. The `[x]` part of the element name is replaced with an appropriate data type, based on the type of result:
* for **quantitative** results, `valueQuantity`, `valueRange` or `valueRatio` **SHOULD** be used
* for **semi-quantitative** and **qualitative** results, `valueCodeable` **SHOULD** be used, with a suitable SNOMED CT concept, for example: `260385009` `Negative`
* for **narrative** results, `valueString` **SHOULD** be used.

The `Observation.interpretation` data element is used to provide a coded, categorical assessment of a test result value. The code is taken from the [ObservationInterpretationCodes]( https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/80843) FHIR value set. The associated test result value is usually **quantitative** and represented using `valueQuantity`, `valueRange` or `valueRatio` as described above.

Refer to the {{pagelink:R4ObservationTestResult}} profile definition for further information relating to the representation of test results.