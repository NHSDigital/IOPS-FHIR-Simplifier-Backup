---
topic: Profile-UKCore-DiagnosticReport
issue: UKCore-DiagnosticReport
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport
expand: yes
---

## StructureDefinition {{variable:issue}}

The  requirements of a specific Genomics DiagnosticReport is currently under review.

The draft profile is provided below for completeness.

Currently, only requirements for initial Pathology reports, provided with a test order, have been reviewed. DiagnosticReports containing the results of genomic testing are expected to be attached/provided as PDF documents during the alpha phase of the GMS development programme. 

It is expected structured DiagnosticReports will mimic the structure proposed within the [HL7 International Genomic Reporting IG](https://hl7.org/fhir/uv/genomics-reporting/index.html), though customizations for use within the UK still need to be investigated.

Genomic DiagnosticReports which have been updated post submission SHALL be accompanied by Provenance resources, referencing the DiagnosticReport which detail when the resource was changed, who made the change and why.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <br>
            <ul>
            <li> {{pagelink:DiagnosticReport-AnitaLamberts-Example}} </li>
            <li> {{pagelink:DiagnosticReport-FayMutlowGeneticReport-Example}} </li>
            <li> {{pagelink:DiagnosticReport-JamesMetcalfeGeneticReport-Example}} </li>
            <li>  {{pagelink:DiagnosticReport-PhoebeSmithGeneticReport-Example}} </li>
            <li> {{pagelink:DiagnosticReport-MichaelJonesReport}} </li>
            <li> {{pagelink:DiagnosticReport-MichaelJonesReport-Minimal}} </li>
            </ul>
</div>

<div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>DiagnosticReport</td><td>Previous Genomic Report, Previous Diagnostic Report</td><td>OBX</td></tr>
                    <tr><td>DiagnosticReport.effectiveDateTime</td><td>PLCM activity - Date and time dataset created, PLCM activity - Turnaround time (calendar days), Previous genomic report - Test performed date, Previous non genomic report - Test performed date</td><td>Derived from OBR-7 in the ORU response message for the activity based on the OML request, OBX-19</td></tr>
                    <tr><td>DiagnosticReport.identifier</td><td>PLCM activity - Local report identifier, Previous genomic report - Report identifier, Previous non genomic report - Report identifier</td><td>OBR-3 for report</td></tr>
                    <tr><td>DiagnosticReport.result</td><td>PLCM activity - Test outcome code (Many), Previous non genomic report - Test result value comparator, Previous non genomic report - Test result value unit of measure, Previous non genomic report - Test result reference range low, Previous non genomic report - Test result reference range high, Previous non genomic report - Test result test method, Previous non genomic report - Test result reference range text, Previous non genomic report - Test result clinical summary</td><td>OBX-3 elements for resulting report, OBX-5, OBX-6, OBX-7 (before operator), OBX-7 (after operator), OBX-17, OBX-7, OBX-8</td></tr>
                    <tr><td>DiagnosticReport.conclusion</td><td>Previous genomic report - Report referral summary, Previous non genomic report - Report referral summary</td><td>OBX-5</td></tr>
                    <tr><td>DiagnosticReport.presentedForm</td><td>Previous genomic report - Report file/link, Previous non genomic report - Report file/link</td><td>OBX-5 where OBX-2=ED or RP</td></tr>
                    <tr><td>DiagnosticReport.subject</td><td>Previous genomic report - Patient's first name, Previous genomic report - Patient's surname, Previous genomic report - Patient's address, Previous genomic report - Patient's post code, Previous genomic report - Patient's country, Previous genomic report - Patient's date of birth, Previous genomic report - Patient's NHS number, Previous genomic report - Patient's alternative identifier, Previous genomic report - Patient's relationship to requesting patient, Previous genomic report - Patient's clinical genetics number, Previous genomic report - Patient's pedigree number</td><td>PID attached to Patient Prior</td></tr>
                    <tr><td>DiagnosticReport.basedOn</td><td>Previous genomic report - Report lab test number, Previous genomic report - Original requester full name, Previous genomic report - Original requester organisation ODS code, Previous genomic report - Original requester reason for request, Previous non genomic report - Original requester full name, Previous non genomic report - Original requester organisation ODS code, Previous non genomic report - Original requester reason for request</td><td>ORC-2, ORC-12, ORC-21.10, ORC-16</td></tr>
                    <tr><td>DiagnosticReport.conclusionCode</td><td>Previous genomic report - Report of genetic analysis, Previous non genomic report - Report result</td><td>OBR-5</td></tr>
                    <tr><td>DiagnosticReport.performer</td><td>Previous genomic report - Report performer full name, Previous genomic report - Report performer organisation ODS code, Previous non genomic report - Report performer full name, Previous non genomic report - Report performer organisation ODS code</td><td>OBX-16, OBX-23.10</td></tr>
                    <tr><td>DiagnosticReport.code</td><td>Previous non genomic report - Test type</td><td>OBR-4</td></tr>
</table>
</div>

<div id="Feedback" class="tabcontent">

{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#extension:mediaR5">extension:mediaR5</a>
- <a href="#extension:recommended-action">extension:recommended-action</a>
- <a href="#extension:genomic-study">extension:genomic-study</a>
- <a href="#extension:supporting-info">extension:supporting-info</a>
- <a href="#extension:workflow-relatedArtifact">extension:workflow-relatedArtifact</a>
- <a href="#basedOn">basedOn</a>
- <a href="#status">status</a>
- <a href="#code">code</a>
- <a href="#subject">subject</a>
- <a href="#performer">performer</a>
- <a href="#resultsInterpreter">resultsInterpreter</a>
- <a href="#specimen">specimen</a>
- <a href="#conclusionCode">conclusionCode</a>
- <a href="#presentedForm">presentedForm</a>
- <a href="#result">result</a>

<a name="#extension:mediaR5"></a>
<h4 class='additional-Guidance-Submenu'> extension:mediaR5 </h4>
TBC. Only relevant for structured genomic reports. Reference to DocumentReference resources pointing to the Genomic Data Files used as the basis for the report. Usage of this field over extension:supporting-info is pending further investigation.

```json
"extension" : [
        {
            "url" : "http://hl7.org/fhir/5.0/StructureDefinition/extension-DiagnosticReport.media.link",
            "extension" : [
                    {
                        "url" : "link",
                        "valueReference": {
                            "reference" : "DocumentReference/DocumentReference-PharmCAT-Example"
                        }
                    }
                ]
            }
        }
    ],
```

<a name="extension:recommended-action"></a>
<h4 class='additional-Guidance-Submenu'> extension:recommended-action </h4>
TBC. Only relevant for structured genomic reports (included in the [Genomic Report Profile in the Genomics Reporting IG](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-report.html)). Reference to Task resource indicating recommended action to take in response to the report's result/conclusion.

```json
"extension" : [
        {
            "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/recommended-action",
            "valueReference" : {
                "reference" : "Task/MedicationRecommendationExample1"
            }
        }
    ],
```

<a name="extension:genomic-study"></a>
<h4 class='additional-Guidance-Submenu'> extension:genomic-study </h4>
TBC. Only relevant for structured genomic reports (included in the [Genomic Report Profile in the Genomics Reporting IG](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-report.html)). Reference to Procedure resources indicating the analyses performed as part the genomic test order.

```json
"extension" : [
    {
      "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomic-study-reference",
      "valueReference" : {
        🔗 "reference" : "Procedure/PGXGenomicStudy"
      }
    }
  ]
```

<a name="extension:supporting-info"></a>
<h4 class='additional-Guidance-Submenu'> extension:supporting-info </h4>
TBC. Only relevant for structured genomic reports (included in the [Genomics Report IG Genomic Report Profile](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-report.html)). Reference to the genomic data files analysed as part of the test order, forming the report. Reference to DocumentReference resource which links to the binary data file.
```json
"extension" : [
        {
            "url" : "http://hl7.org/fhir/StructureDefinition/workflow-supportingInfo",
            "valueReference" : {
                "reference" : "DocumentReference/DocumentReference-PharmCAT-Example"
            }
        }
    ],
```

<a name="extension:workflow-relatedArtifact"></a>
<h4 class='additional-Guidance-Submenu'> extension:workflow-relatedArtifact </h4>
TBC. Only relevant for structured genomic reports (included in <a href='https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-report.html' target='_blank'> Genomic Report Profile in the Genomics Report IG) </a>. A reference to the guidelines or other knowledge artifacts which were used to guide interpretation or recommended actions included within this DiagnosticReport. 

If entries constitute published papers, they SHOULD be referenced using a known citation style, e.g. Vancouver/Harvard. Alternatively for online texts, these MAY be referenced via URL only.

A fixed value of 'citation' is expected for the type element, though this recommendation is pending further use cases.

```json
"extension" : [
        {
            "url" : "http://hl7.org/fhir/StructureDefinition/workflow-relatedArtifact",
            "valueRelatedArtifact" : {
                "type" : "citation",
                "url" : "https://cpicpgx.org/guidelines/guideline-for-clopidogrel-and-cyp2c19)"
            }
        }
    ],
```

<a name="basedOn"></a>
<h4 class='additional-Guidance-Submenu'> basedOn </h4>
SHOULD reference the originating ServiceRequest if this is an instance of a genomic diagnostic report resulting from a GMS test order.

```json
"basedOn":  [
        {
            "reference": "ServiceRequest-SavedTestOrder-Example"
        }
    ],
```

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
SHALL use base HL7 codes for DiagnosticReport.status. A DiagnosticReport SHOULD only be marked as final if the report is complete and verified by an authorised person.  

```json
 "status": "final",
```

<a name="code"></a>
<h4 class='additional-Guidance-Submenu'> code </h4>
SHOULD use a record artifact concept from SNOMED CT where an appropriate code exists, else text is preferred to indicate the document type.  

```json
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "4321000179101",
                "display": "Hematology report (record artifact)"
            }
        ]
    },
```

<a name="subject"></a>
<h4 class='additional-Guidance-Submenu'> subject </h4>
SHALL be present. Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS

```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="performer"></a>
<h4 class='additional-Guidance-Submenu'> performer </h4>
SHOULD reference the organization responsible for the testing, preferably by ODS code.

```json
"performer":  [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "REP"
            }
        }
    ],
```

<a name="resultsInterpreter"></a>
<h4 class='additional-Guidance-Submenu'> resultInterpreter </h4>
SHOULD reference the person responsible for interpreting the raw results, preferably by a recognised NHS identifier, such as SDS code.

```json
"resultsInterpreter":  [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/sds-user-id",
                "value": "999999999999"
            }
        }
    ],
```

<a name="specimen"></a>
<h4 class='additional-Guidance-Submenu'> specimen </h4>
SHOULD reference the specimen used during testing to generate the report, if the document is a Genomic report.

```json
"specimen":  [
        {
            "reference": "Specimen/Specimen-BloodEDTA-Example"
        }
    ],
```

<a name="conclusionCode"></a>
<h4 class='additional-Guidance-Submenu'> conclusionCode </h4>
If possible, unstructured reports wrapped within DiagnosticReports, SHOULD contain a conclusionCode element indicating the coded finding from the report, to aid analytics. 

```json
"conclusionCode":  [
        {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "738542003",
                    "display": "Dihydropyrimidine dehydrogenase poor metabolizer (finding)"
                }
            ]
        }
    ],
```

<a name="presentedForm"></a>
<h4 class='additional-Guidance-Submenu'> presentedForm </h4>
Genomic reports SHALL include a presentedForm element either referencing the location of the PDF report (located and accessible on either the source/client system or via NRL using appropriate authentication) or include the PDF report as a base64 encoded attachment within the message payload.

**Note: this guidance may change in the future as work on Structured Reporting matures**

```json
"presentedForm": [
        {
            "url": "https://example.com/GenomicReports/ExampleReport.pdf"
        }
    ]
```

<a name="result"></a>
<h4 class='additional-Guidance-Submenu'> result </h4>
Raw results included within the report, to aid interpretation. These SHOULD take the form of Observation references, if providing a structured report.

```json
"result" : [
        {
            "reference" : "Observation/TherapeuticImplicationExample1",
            "display" : "impact for high risk allele"
        },
        {
            "reference" : "Observation/GenotypeExample1"
        },
        {
            "reference" : "Observation/OverallInterpExample1"
        }
    ]
```

---