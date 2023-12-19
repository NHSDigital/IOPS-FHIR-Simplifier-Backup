## {{page-title}}

The  requirements of a specific Genomics DiagnosticReport is currently under review.

The draft profile is provided below for completeness.

Currently, only requirements for initial Pathology reports, provided with a test order, have been reviewed. DiagnosticReports containing the results of genomic testing are expected to be attached/provided as PDF documents during the alpha phase of the GMS development programme. 

It is expected structured DiagnosticReports will mimic the structure proposed within the [HL7 International Genomic Reporting IG](https://hl7.org/fhir/uv/genomics-reporting/index.html), though customizations for use within the UK still need to be investigated.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

<br>

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/DiagnosticReport}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:DiagnosticReport-MichaelJonesReport}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:DiagnosticReport-MichaelJonesReport-Minimal}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
    </div>
</div>


### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-DiagnosticReport' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

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
- <a href="#extension:recommended-action">extension:recommended-action</a>

<a name="basedOn"></a>
#### basedOn
SHOULD reference the originating ServiceRequest if this is an instance of a genomic diagnostic report resulting from a GMS test order.  
```json
"basedOn":  [
        {
            "reference": "ServiceRequest-SavedTestOrder-Example"
        }
    ],
```

<a name="status"></a>
#### status
SHOULD use base HL7 codes for DiagnosticReport.status. A DiagnosticReport SHOULD only be marked as final if the report is complete and verified by an authorised person.  
```json
 "status": "final",
```

<a name="code"></a>
#### code
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
#### subject
Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
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
#### performer
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
#### resultsInterpreter
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
#### specimen
SHOULD reference the specimen used during testing to generate the report, if the document is a Genomic report.
```json
"specimen":  [
        {
            "reference": "Specimen/Specimen-BloodEDTA-Example"
        }
    ],
```

<a name="conclusionCode"></a>
#### conclusionCode
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
#### presentedForm
Genomic reports SHALL include a presentedForm element either referencing the location of the PDF report (located and accessible on either the source/client system or via NRL using appropriate authentication) or include the PDF report as a base64 encoded attachment within the message payload.
```json
"presentedForm": [
        {
            "url": "https://example.com/GenomicReports/ExampleReport.pdf"
        }
    ]
```

<a name="result"></a>
#### result
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

<a name="extension:recommended-action"></a>
#### extension:recommended-action
TBC. Only relevant for structured genomic reports. Reference to Task resource indicating recommended action to take in response to the report's result/conclusion
```json
"extension" : [
        {
            "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/recommended-action",
            "valueReference" : {
                "reference" : "Task/MedicationRecommendationExample1"
            }
        },
        {
            "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomics-artifact",
            "valueRelatedArtifact" : {
                "type" : "citation",
                "url" : "https://cpicpgx.org/guidelines/guideline-for-clopidogrel-and-cyp2c19)"
            }
        }
    ],
```