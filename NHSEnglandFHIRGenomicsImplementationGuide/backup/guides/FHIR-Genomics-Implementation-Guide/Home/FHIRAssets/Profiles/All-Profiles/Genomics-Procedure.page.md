## {{page-title}}

Used for detailing information on procedures the patient has had performed, to aid interpretation of Genomic test results.

Assertion of an absence of a procedure being performed SHOULD be recorded using an Observation resource, as described in {{pagelink:Genomics-Observation}}

At a minimum, Procedure resources are expected to contain the status, code, subject and performedDateTime, though additional information conforming to the FHIR profile below MAY be included if relevant.

[Genomic Study](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study.html) and [Genomic Study Analysis](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study-analysis.html) profiles on Procedure may also be used as part of structured reporting. Mandated usage of these profiles is pending data standard discovery work to identify the items required within Genomic Test Reporting. As such, elements called out, and guidance suggested on this page, may be subject to change. 

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
        <li role="presentation">
            <a href="#Mappings" role="tab" data-toggle="tab">Mappings</a>
        </li>
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Procedure}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Procedure-MichaelJonesTransplant}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Procedure-InVitroFertilisation-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Procedure</td><td>Patient - Had transplant, Patient - Had transfusion, Is patient on TKI therapy, Insulin treated within 6 months of diagnosis, Is on Ig replacement</td><td>Presence of OBR segment with OBR-44 code for transplant/transfusion etc.</td></tr>
                    <tr><td>Procedure.performedDateTime</td><td>Patient - Fetal gestation (to determine termination date), Patient - Transplant date, Patient - Transfusion date</td><td>OBR-7</td></tr>
                    <tr><td>Procedure.code</td><td>Patient - Pregnancy type, Patient - Type of transplant, Patient - Type of transfusion, Neonatal hypoglycemia treatment details, Current exocrine pancreatic treatment</td><td>OBR segments with appropriate codes, OBR-44, OBR/RXA segments</td></tr>
                    <tr><td>Procedure.performedPeriod.start</td><td>Neonatal hypoglycemia treatment start date, Exocrine pancreatic treatment start date</td><td>OBR-7, RXA-3</td></tr>
                    <tr><td>Procedure.performedPeriod.end</td><td>Neonatal hypoglycemia treatment end date</td><td>OBR-8</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Procedure' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance
	
- <a href="#extension:genomic-study-analysis">extension:genomic-study-analysis</a>
- <a href="#genomic-study-analysis">Genomic Study Analysis extensions</a>
- <a href="#status">status</a>
- <a href="#code">code</a>
- <a href="#subject">subject</a>
- <a href="#performed">performed\[x\]</a>

<a name="extension:genomic-study-analysis"></a>
#### extension:genomic-study-analysis
TBC. From the Genomic Reporting IG [Genomic Study](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study.html) profile. Reference to the [Genomic Study Analysis](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study-analysis.html) resource, detailing the analyses performed as part of genomic test.
```json
"extension" : [
    {
      "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomic-study-analysis-ext",
      "valueReference" : {
        "reference" : "Procedure/PGXGenomicStudyAnalysis"
      }
    }
  ],
```

<a name="genomic-study-analysis"></a>
#### Genomic Study Analysis extensions
TBC. From the Genomic Reporting IG [Genomic Study Analysis](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study-analysis.html) profile. Various extensions covering the metadata related to a genomic test, e.g. regions studied, chage types tested for etc. For the full list of extensions, please see the linked profile page.

Use of the profile and its extensions is pending further discovery of the data standards required for Genomic Reporting in the UK.
```json
"extension" : [
    {
      "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomic-study-analysis-genome-build",
      "valueCodeableConcept" : {
        "coding" : [
          {
            "system" : "http://loinc.org",
            "code" : "LA26806-2",
            "display" : "GRCh38"
          }
        ]
      }
    },
    {
      "extension" : [
        {
          "url" : "sequencing-coverage",
          "valueQuantity" : {
            "value" : 100
          }
        }
      ],
      "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomic-study-analysis-metrics"
    },
    {
      "extension" : [
        {
          "url" : "description",
          "valueString" : "protein-coding and exon-splicing regions"
        },
        {
          "url" : "studied",
          "valueCodeableConcept" : {
            "coding" : [
              {
                "system" : "http://www.genenames.org",
                "code" : "HGNC:2621",
                "display" : "CYP2C19"
              }
            ]
          }
        },
        {
          "url" : "studied",
          "valueCodeableConcept" : {
            "coding" : [
              {
                "system" : "http://www.genenames.org",
                "code" : "HGNC:2623",
                "display" : "CYP2C9"
              }
            ]
          }
        },
        {
          "url" : "studied",
          "valueCodeableConcept" : {
            "coding" : [
              {
                "system" : "http://www.genenames.org",
                "code" : "HGNC:23663",
                "display" : "VKORC1"
              }
            ]
          }
        }
      ],
      "url" : "http://hl7.org/fhir/uv/genomics-reporting/StructureDefinition/genomic-study-analysis-regions"
    }
  ],
```

<a name="status"></a>
#### status
Status SHALL use the codes recommended in the base Procedure resource, appropriately tagging procedures as having been completed or in-progress etc. depending on the actual status of the procedure.
```json
"status": "completed",
```

<a name="code"></a>
#### code
SHALL be present. SNOMED CT coding is preferred, though alternative codings MAY be provided subject to review of the Coding system by the NHS England Genomics Unit.

For the [Genomic Study](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study.html) profile, expected to be from the [Genomic Study Type ValueSet](https://build.fhir.org/ig/HL7/genomics-reporting/ValueSet-genomic-study-type-vs.html)
```json
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "23719005",
                "display": "Transplantation of bone marrow"
            }
        ]
    },
```

<a name="subject"></a>
#### subject
SHALL be present. Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS.
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="performed"></a>
#### performed\[x\]
performed SHOULD be provided wherever possible, using the appropriate data type, to aid in interpretation of Genomic test results.
```json
"performedDateTime": "2020-01-19"
```