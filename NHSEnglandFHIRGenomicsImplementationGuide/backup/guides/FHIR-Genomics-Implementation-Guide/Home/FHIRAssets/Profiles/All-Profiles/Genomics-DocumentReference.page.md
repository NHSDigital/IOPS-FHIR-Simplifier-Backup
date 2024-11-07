---
topic: Profile-Genomics-DocumentReference
issue: Genomics-DocumentReference
subject: http://hl7.org/fhir/StructureDefinition/DocumentReference
expand: yes
---

# {{variable:issue}}

The DocumentReference resource is used to reference data files generated as part of genomic testing and allow these files to be retrieved through the [DRS API standard](https://www.ga4gh.org/news_item/drs-api-enabling-cloud-based-data-access-and-retrieval/).

Primarily, the ServiceRequest SHALL be referenced via DiagnosticReport.basedOn. The DocumentReference then links back to the report via DocumentReference.context.related.

If following the Genomic Reporting IG, you could also reference the DocumentReference from the DiagnosticReport using the following chain:
```DiagnosticReport.extension:genomic-study -> Procedure (Genomic Study).extension:genomic-study-analysis -> Procedure (Genomic Study Analysis).extension:output.extension:file.valueReference -> DocumentReference (Genomic Data File)```

This requires use of the Genomic Study and Genomic Study Analysis profiles which have not yet been assessed for suitability in the UK. As such, this reference chain is only provided for reference.

The NHS England Genomics unit is also investigating backporting the R5 DiagnosticReport.media.link reference to DocumentReference to support referencing the data files from the DiagnosticReport directly. Until investigation is complete, DiagnosticReport resources MAY reference the DocumentReference for the data used by the report though the `DiagnosticReport.extension:supporting-info` element. In all cases the DocumentReference SHOULD reference the DNA Specimen from which the data originated and the ServiceRequest which triggered the capture of the data.

The Genomics-DocumentReference is currently based on the HL7 international version of the resource as the UKCore-DocumentReference profile is still in a draft status (and is pending use cases from the Unified Genomic Record project). Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The base DocumentReference resource is provided below for completeness.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/DocumentReference](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/DocumentReference&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
    <br>
    <ul>
        <li>{{pagelink:DocumentReference-PharmCAT-Example}}</li>
    </ul>
        </div>
        
<div id="Mappings" class="tabcontent">
       
            <!--
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>BodyStructure.morphology</td><td>Raw specimen/biopsy - Solid tumour morphology</td><td>Additional SPM-4/5 qualifiers</td></tr>
                    <tr><td>BodyStructure.location</td><td>Raw specimen/biopsy - Solid tumour histological type (topography)</td><td>SPM-8</td></tr>
                </table>
                -->
        </div>
 
<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#subject">subject</a>
- <a href="#author">author</a>
- <a href="#description">description</a>
- <a href="#content">content</a>
- <a href="#context">context</a>

<a name="subject"></a>
<h4 class='additional-Guidance-Submenu'> subject </h4>
SHOULD be present if related to a patient. Reference to the Patient this data file is pertaining to. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS

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
<h4 class='additional-Guidance-Submenu'> author </h4>
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
<h4 class='additional-Guidance-Submenu'> description </h4>
Human readable description for the data file. NOTE: this is being used in place of DocumentReference.type until suitable LOINC or SNOMED CT concepts are identified for the file types expected.  

```json
 "description": "Phenotype Report",
```

<a name="content"></a>
<h4 class='additional-Guidance-Submenu'> content </h4>
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
<h4 class='additional-Guidance-Submenu'> context </h4>
In all cases the DocumentReference SHOULD reference the DNA Specimen from which the data originated, where available, and the ServiceRequest which triggered the capture of the data.

The DiagnosticReport using the data file SHOULD reference the DocumentReference via the `DiagnosticReport.extension:supporting-info` element. **This guidance will be updated upon release of the R5 backport of DiagnosticReport.media, allowing references to DocumentReference. Once backported, the DiagnosticReport.media.link SHOULD be used to reference the DocumentReference resources for data files analysed for the report instead.**

```json
"context": {
    "related": [
      {
        "reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-NewFollowupTest-Example"
      },
      {
        "reference": "Specimen/Specimen-BloodEDTA-Example"
      }
    ]
  }
```
---