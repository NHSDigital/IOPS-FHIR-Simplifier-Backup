## {{page-title}}

The DocumentReference resource is used to reference data files generated as part of genomic testing and allow these files to be retrieved through the [DRS API standard](https://www.ga4gh.org/news_item/drs-api-enabling-cloud-based-data-access-and-retrieval/).

Primarily, the ServiceRequest SHALL be referenced via DiagnosticReport.basedOn. The DocumentReference then links back to the report via DocumentReference.context.related.

If following the Genomic Reporting IG, you could also reference the DocumentReference from the DiagnosticReport using the following chain:
```DiagnosticReport.extension:genomic-study -> Procedure (Genomic Study).extension:genomic-study-analysis -> Procedure (Genomic Study Analysis).extension:output.extension:file.valueReference -> DocumentReference (Genomic Data File)```

This requires use of the Genomic Study and Genomic Study Analysis profiles which have not yet been assessed for suitability in the UK. As such, this reference chain is only provided for reference.

The NHS England Genomics unit is also investigating backporting the R5 DiagnosticReport.media.link reference to DocumentReference to support referencing the data files from the DiagnosticReport directly.

The Genomics-DocumentReference is currently based on the HL7 international version of the resource as the UKCore-DocumentReference profile is still in a draft status (and is pending use cases from the Unified Genomic Record project). Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The base DocumentReference resource is provided below for completeness.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/DocumentReference](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/DocumentReference&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |


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
            {{tree: http://hl7.org/fhir/StructureDefinition/DocumentReference, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/DocumentReference}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/DocumentReference, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/DocumentReference, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:DocumentReference-PharmCAT-Example}}
                    </td>
                </tr>
            </table>
        </div>
        
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':http://hl7.org/fhir/StructureDefinition/DocumentReference'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <!--
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>BodyStructure.morphology</td><td>Raw specimen/biopsy - Solid tumour morphology</td><td>Additional SPM-4/5 qualifiers</td></tr>
                    <tr><td>BodyStructure.location</td><td>Raw specimen/biopsy - Solid tumour histological type (topography)</td><td>SPM-8</td></tr>
                </table>
                -->
        </div>
    </div>
</div>

<br>

### Additional Guidance

- <a href="#subject">subject</a>
- <a href="#author">author</a>
- <a href="#description">description</a>
- <a href="#content">content</a>
- <a href="#context">context</a>

<a name="subject"></a>
#### subject
Reference to the Patient this data file is pertaining to. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="author"></a>
#### author
SHOULD reference the organization responsible for creating the data file, preferably by ODS code.
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

<a name="description"></a>
#### description
Human readable description for the data file. NOTE: this is being used in place of DocumentReference.type until suitable LOINC or SNOMED CT concepts are identified for the file types expected.  
```json
 "description": "Phenotype Report",
```

<a name="content"></a>
#### content
SHOULD be a DRS compatible reference to the data file.   
```json
"content": [
    {
      "attachment": {
        "contentType": "application/json",
        "url": "drs://drs.genomicsengland.nhs.uk/ga4gh/drs/v1/objects/42375e7d-071c-4eb3-b1c8-cec11e245cf0",
        "title": "PharmCAT JSON report"
      }
    }
  ],
```

<a name="context"></a>
#### context
SHOULD reference the DiagnosticReport related to the data file, where this exists.
```json
"context": {
    "related": [
      {
        "reference": "DiagnosticReport/DiagnosticReport-AnitaLamberts-Example"
      }
    ]
  }
```