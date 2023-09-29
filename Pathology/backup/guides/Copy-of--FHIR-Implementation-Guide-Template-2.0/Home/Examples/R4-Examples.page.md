---
topic: R4Examples
---
## R4 Examples
The following examples illustrate the use of the {{pagelink:FHIRAssetsR4Profiles}} for pathology, categorised by resource type and speciality.

The Bundle examples include on-screen representations of pathology test requests and reports. These have been provided to illustrate the contents of the associated messages. They are not intended to define a standard layout or format for pathology test requests and reports and should not be used as such.

<div markdown="span" class="alert alert-nhse" role="alert">
<i class="fa fa-exclamation-circle"></i> The patient and practitioner related data used in the examples is live-like in appearance but is fictitious. Any similarity to actual persons is purely coincidental. The addresses used are valid addresses based on publicly available address data.
</div>

The Bundle examples also include simplified logical data models to illustrate the key references between the relevant FHIR resources. To aid clarity, not all of the references are shown. For a detailed description of the relationships between the FHIR resources, refer to {{pagelink:BuildContructPathologyRequestBundle}} and {{pagelink:BuildContructPathologyReportBundle}}.

<table class="regular codes">
    <thead>
        <tr>
            <th width="10%">Reference</th>
            <th width="10%">Resource</th>
            <th width="15%">Speciality</th>
            <th width="30%">Summary</th>
            <th width="35%">Example</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>PATH-R4-01</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
            <td>Request for a single test (numeric result).</td>
            <td>{{pagelink:R4BundleExampleHbA1cRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-02</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
            <td>Report for a single test (numeric result).</td>
            <td>{{pagelink:R4BundleExampleHbA1cReport}}</td>
        </tr>   
        <tr>
            <td>PATH-R4-03</td>
            <td>Bundle</td>
            <td>Haematology</td>
            <td>Request for a single test group (numeric results).</td>
            <td>{{pagelink:R4BundleExampleFullBloodCountRequest}}</td>
        </tr>   
        <tr>
            <td>PATH-R4-04</td>
            <td>Bundle</td>
            <td>Haematology</td>
            <td>Report for a single test group (numeric results).</td>
            <td>{{pagelink:R4BundleExampleFullBloodCountReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-05</td>
            <td>Bundle</td>
            <td>Immunology / Serology</td>
            <td>Request for a single test (qualitative result).</td>
            <td>{{pagelink:R4BundleExampleHBsAgRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-06</td>
            <td>Bundle</td>
            <td>Immunology / Serology</td>
            <td>Report for a single test (qualitative result).</td>
            <td>{{pagelink:R4BundleExampleHBsAgReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-07</td>
            <td>Bundle</td>
            <td>Cytology</td>
            <td>Request for a single test (qualitative result).</td>
            <td>{{pagelink:R4BundleExampleHPVRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-08</td>
            <td>Bundle</td>
            <td>Cytology</td>
            <td>Report for a single test (qualitative result).</td>
            <td>{{pagelink:R4BundleExampleHPVReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-09</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
            <td>Request for multiple test groups (numeric results).</td>
            <td>{{pagelink:R4BundleExampleLFTandUandERequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-10</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
            <td>Report for multiple test groups (numeric results).</td>
            <td>{{pagelink:R4BundleExampleLFTandUandEReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-11</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
        	<td>Request for a dynamic function test (numeric results).</td>
            <td>{{pagelink:R4BundleExampleGTTRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-12</td>
            <td>Bundle</td>
            <td>Clinical Biochemistry</td>
            <td>Report for a dynamic function test (numeric results).</td>
            <td>{{pagelink:R4BundleExampleGTTReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-13</td>
            <td>Bundle</td>
            <td>Microbiology</td>
            <td>Request for a complex test, with multiple, nested test groups (numeric, qualitative and semi-quantitative results).</td>
            <td>{{pagelink:R4BundleExampleUrineMCSRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-14</td>
            <td>Bundle</td>
            <td>Microbiology</td>
            <td>Report for a complex test, with multiple, nested test groups (numeric, qualitative and semi-quantitative results).</td>
            <td>{{pagelink:R4BundleExampleUrineMCSReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-15</td>
            <td>DiagnosticReport</td>
            <td>Microbiology</td>
            <td>A set of examples that illustrate how each supported data element within {{pagelink:R4DiagnosticReport}} may be populated.</td>
            <td>{{pagelink:R4SnippetsDiagnosticReport}}</td>
        </tr>
        <tr>
            <td>PATH-R4-16</td>
            <td>Observation (Test Group)</td>
            <td>Haematology</td>
            <td>A set of examples that illustrate how each supported data element within {{pagelink:R4ObservationTestGroup}} may be populated.</td>
            <td>{{pagelink:R4SnippetsObservationTestGroup}}</td>
        </tr>
        <tr>
            <td>PATH-R4-17</td>
            <td>Observation (Test Result)</td>
            <td>Haematology</td>
            <td>A set of examples that illustrate how each supported data element within {{pagelink:R4ObservationTestResult}} may be populated.</td>
            <td>{{pagelink:R4SnippetsObservationTestResult}}</td>
        </tr>
        <tr>
            <td>PATH-R4-18</td>
            <td>ServiceRequest</td>
            <td>Clinical Biochemistry</td>
            <td>A set of examples that illustrate how each supported data element within {{pagelink:R4ServiceRequest}} may be populated.</td>
            <td>{{pagelink:R4SnippetsServiceRequest}}</td>
        </tr>
        <tr>
            <td>PATH-R4-19</td>
            <td>Specimen</td>
            <td>Clinical Biochemistry</td>
            <td>A set of examples that illustrate how each supported data element within {{pagelink:R4Specimen}} may be populated.</td>
            <td>{{pagelink:R4SnippetsSpecimen}}</td>
        </tr>
    </tbody>
</table>