---
topic: R4Examples
---
## Examples Index
The following examples illustrate the use of the FHIR UK Core R4 {{pagelink:FHIRAssetsR4Profiles}} described by this implementation guide, categorised by profile type and pathology speciality.

<div markdown="span" class="alert alert-nhse" role="alert">
<i class="fa fa-exclamation-circle"></i> Whilst every effort has been made to ensure that the examples are correct, they are not a normative part of the implementation guide. The patient and practitioner related data used in the examples is live-like in appearance but is fictitious. Any similarity to actual persons is purely coincidental. The addresses used are valid addresses based on publicly available address data.
</div>

The `Bundle` examples include on-screen representations of pathology test requests and reports. These have been provided to illustrate the contents of the associated messages. They are not intended to define a standard layout or format for pathology test requests and reports and should not be used as such.

The `Bundle` examples also include simplified logical data models to illustrate the key references between the relevant FHIR resources. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR resources, refer to {{pagelink:BuildContructPathologyRequestBundle}} and {{pagelink:BuildContructPathologyReportBundle}}.

The snippet examples have been provided to illustrate how each key data element within a profile may be populated. The examples illustrate individual data element usage within a profile; the full set of data elements may not necessarily be consistent with one another or illustrate a single, complete clinical scenario.

**Note:** Most of the examples include equivalent codes from the PBCL and PaLM SNOMED CT reference sets to identify the relevant pathology test. This has been done to illustrate how the examples can be used with different reference sets. In practice, it is likely that only one code will be carried for each pathology test. To facilitate the initial adoption of SNOMED it is anticipated that codes from the PBCL SNOMED CT reference set will be used at first, to minimise the impact on existing systems and processes. 

<table class="regular">
    <thead>
        <tr>
            <th width="10%">Reference</th>
            <th width="15%">Profile</th>
            <th width="15%">Speciality</th>
            <th width="30%">Summary</th>
            <th width="30%">Example</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>PATH-R4-01</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a request for a single test with a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4BundleExampleHbA1cRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-02</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for a single test with a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4BundleExampleHbA1cReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-03</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a request for a single test with a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4BundleExampleCRPRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-04</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for a single test with a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4BundleExampleCRPReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-05</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Immunology / Serology</td>
            <td>An example of a request for a single test with a qualitative test result.</td>
            <td>{{pagelink:R4BundleExampleHBsAgRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-06</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Immunology / Serology</td>
            <td>An example of a report for a single test with a qualitative test result.</td>
            <td>{{pagelink:R4BundleExampleHBsAgReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-07</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Cytology</td>
            <td>An example of a request for a single test with a qualitative test result.</td>
            <td>{{pagelink:R4BundleExampleHPVRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-08</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Cytology</td>
            <td>An example of a report for a single test with a qualitative test result.</td>
            <td>{{pagelink:R4BundleExampleHPVReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-09</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Haematology</td>
            <td>An example of a request for a single test group with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleFullBloodCountRequest}}</td>
        </tr>   
        <tr>
            <td>PATH-R4-10</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Haematology</td>
            <td>An example of a report for a single test group with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleFullBloodCountReport}}</td>
        </tr>      
        <tr>
            <td>PATH-R4-11</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a request for a single test group and a single test with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleLipidsandHbA1cRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-12</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for a single test group and a single test with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleLipidsandHbA1cReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-13</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a request for multiple test groups with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleLFTandUandERequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-14</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for multiple test groups with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleLFTandUandEReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-15</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
        	<td>An example of a request for a dynamic function test with quantitative (numeric) test results.</td>
            <td>{{pagelink:R4BundleExampleGTTRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-16a</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for a dynamic function test with quantitative (numeric) test results. The results are represented using a single <code>Observation</code> and formatted as a blob of text.</td>
            <td>{{pagelink:R4BundleExampleGTTReportUnstructured}}</td>
        </tr>
        <tr>
            <td>PATH-R4-16b</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a report for a dynamic function test with quantitative (numeric) test results. The results are represented using a set of structured, coded  <code>Observations</code>.</td>
            <td>{{pagelink:R4BundleExampleGTTReportStructured}}</td>
        </tr>
        <tr>
            <td>PATH-R4-17</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Microbiology</td>
            <td>An example of a request for a complex test with multiple, nested test groups and quantitative (numeric), qualitative and semi-quantitative test results.</td>
            <td>{{pagelink:R4BundleExampleUrineMCSRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-18a</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Microbiology</td>
            <td>An example of a report for a complex test with multiple, nested test groups and quantitative (numeric), qualitative and semi-quantitative test results. The results are represented using a single <code>Observation</code> and formatted as a blob of text.</td>
            <td>{{pagelink:R4BundleExampleUrineMCSReportUnstructured}}</td>
        </tr>
        <tr>
            <td>PATH-R4-18b</td>
            <td>{{pagelink:R4Bundle}}</td>
            <td>Microbiology</td>
            <td>An example of a report for a complex test with multiple, nested test groups and quantitative (numeric), qualitative and semi-quantitative test results. The results are represented using a set of structured, coded  <code>Observations</code>.</td>
            <td>{{pagelink:R4BundleExampleUrineMCSReportStructured}}</td>
        </tr>
        <tr>
            <td>PATH-R4-19</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4ObservationAlbumin}}</td>
        </tr>
        <tr>
            <td>PATH-R4-20</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a quantitative (numeric) test result.</td>
            <td>{{pagelink:R4ObservationeGFR}}</td>
        </tr>
        <tr>
            <td>PATH-R4-21</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Microbiology</td>
            <td>An example of a semi-quantitative test result.</td>
            <td>{{pagelink:R4ObservationEpithelialCells}}</td>
        </tr>
        <tr>
            <td>PATH-R4-22</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Microbiology</td>
            <td>An example of a semi-quantitative test result.</td>
            <td>{{pagelink:R4ObservationNitrofurantoinSusceptibility}}</td>
        </tr>
        <tr>
            <td>PATH-R4-23</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Immunology / Serology</td>
            <td>An example of a qualitative test result.</td>
            <td>{{pagelink:R4ObservationHBsAg}}</td>
        </tr>
        <tr>
            <td>PATH-R4-24</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Microbiology</td>
            <td>An example of a qualitative test result.</td>
            <td>{{pagelink:R4ObservationMRSAScreeningTest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-25</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example of a quantitative (numeric) test result combined with an interpretation.</td>
            <td>{{pagelink:R4ObservationLymphocyteCount}}</td>
        </tr>
        <tr>
            <td>PATH-R4-26</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Microbiology</td>
            <td>An example of a quantitative (numeric) test result combined with an interpretation.</td>
            <td>{{pagelink:R4ObservationRubellaIgGAntibody}}</td>
        </tr>
        <tr>
            <td>PATH-R4-27</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Microbiology</td>
            <td>An example of a narrative test result.</td>
            <td>{{pagelink:R4ObservationAerobicBloodCulture}}</td>
        </tr>
        <tr>
            <td>PATH-R4-28</td>
            <td>{{pagelink:R4DiagnosticReport}}</td>
            <td>Microbiology</td>
            <td>An example to illustrate how each key data element within {{pagelink:R4DiagnosticReport}} may be populated.</td>
            <td>{{pagelink:R4SnippetsDiagnosticReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-29</td>
            <td>{{pagelink:R4ObservationTestGroup}}</td>
            <td>Haematology</td>
            <td>An example to illustrate how each key data element within {{pagelink:R4ObservationTestGroup}} may be populated.</td>
            <td>{{pagelink:R4SnippetsObservationTestGroup}}</td>
        </tr>
        <tr>
            <td>PATH-R4-30</td>
            <td>{{pagelink:R4ObservationTestResult}}</td>
            <td>Haematology</td>
            <td>An example to illustrate how each key data element within {{pagelink:R4ObservationTestResult}} may be populated.</td>
            <td>{{pagelink:R4SnippetsObservationTestResult}}</td>
        </tr>
        <tr>
            <td>PATH-R4-31</td>
            <td>{{pagelink:R4ServiceRequest}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example to illustrate how each key data element within {{pagelink:R4ServiceRequest}} may be populated.</td>
            <td>{{pagelink:R4SnippetsServiceRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-32</td>
            <td>{{pagelink:R4Specimen}}</td>
            <td>Clinical Biochemistry</td>
            <td>An example to illustrate how each key data element within {{pagelink:R4Specimen}} may be populated.</td>
            <td>{{pagelink:R4SnippetsSpecimen}}</td>
        </tr>
    </tbody>
</table>