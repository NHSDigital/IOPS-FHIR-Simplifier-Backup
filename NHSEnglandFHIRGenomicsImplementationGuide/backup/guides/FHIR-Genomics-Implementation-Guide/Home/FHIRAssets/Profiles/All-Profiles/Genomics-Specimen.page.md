## {{page-title}}

Used to capture information on Samples which will undergo or have undergone processing for genomic testing. 

Within FHIR R4, there is no way to capture location against a sample to aid tracking, one of the key requirements of the Genomic Medicine Service. Investigation of a possible solution through backporting the container.location element within R5 is currently being investigated. Until this backport is adopted by UK Core, the location of samples, including interactions to manage and track samples, will be performed through changes to Task resources generated on submission of a ServiceRequest.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Specimen}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Specimen-BloodEDTA-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-BloodEDTA-WithCollectoinDetails-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-BoneMarrowAspiration-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-JamesMetcalfeBloodEDTA-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-PheobeSmitham-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-PheobeSmithamFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-PheobeSmithamMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-RyanneBoulderPartnerSaliva-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-RyanneBoulderSaliva-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-CancerSolidTumor-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-TissueResection-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Home/Examples/Specimen/Specimen-MichealJonesBlood-Minimal.page.md}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Specimen-MichaelJonesBloodWithCollectoinDetails-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Specimen</td><td>Sample/Biopsy inc germline, Extracted Specimen</td><td>SPM</td></tr>
                    <tr><td>Specimen.subject</td><td>Fetus - Is sample for fetal or unregistered neonate, Raw specimen/biopsy - Family member provided by</td><td>PID segment attached to SPM</td></tr>
                    <tr><td>Specimen.collection.quantity</td><td>PLCM activity - Sample volume, Raw specimen/biopsy - Volume</td><td>SPM-12</td></tr>
                    <tr><td>Specimen.type</td><td>PLCM activity - Sample category code</td><td>SPM-4</td></tr>
                    <tr><td>Specimen.identifier.assigner</td><td>Raw specimen/biopsy - Id assigning authority ODS code (many), Raw specimen/biopsy - Is assigning authority a histopathology laboratory (many), Extracted specimen - Id assigning authority ODS code (many)</td><td>SPM-2.1.2</td></tr>
                    <tr><td>Specimen.identifier.value</td><td>Raw specimen/biopsy - Id (many), Extracted specimen - Id (many)</td><td>SPM-2</td></tr>
                    <tr><td>Specimen.container.identifier</td><td>Raw specimen/biopsy - Sample well identifier</td><td>SAC-3</td></tr>
                    <tr><td>Specimen.note</td><td>Raw specimen/biopsy - Location details (will use backported R5 container.location once released), Extracted specimen - Location details, Raw specimen/biopsy - Sample to follow reason, Raw specimen/biopsy - Additional specimen/biopsy information, Extracted specimen - Additional specimen information</td><td>SAC-15, NTE segment attached to ORC, OBX segments attached to SPM</td></tr>
                    <tr><td>Specimen.extension:sampleCategory</td><td>Raw specimen/biopsy - WGS specimen type category</td><td>SPM-5</td></tr>
                    <tr><td>Specimen.type</td><td>Raw specimen/biopsy - Type, Raw specimen/biopsy - Blood component, Extracted specimen - Type</td><td>SPM-4</td></tr>
                    <tr><td>Specimen.condition</td><td>Raw specimen/biopsy - State</td><td>SPM-24</td></tr>
                    <tr><td>Specimen.processing</td><td>Raw specimen/biopsy - Sample preparation (submitted to GLH)</td><td>Combination of SPM-6/SPM-24 or NTE segments if other processing</td></tr>
                    <tr><td>Specimen.collection.collectedDateTime</td><td>Raw specimen/biopsy - Obtained date</td><td>SPM-17</td></tr>
                    <tr><td>Specimen.receivedTime</td><td>Raw specimen/biopsy - Received date</td><td>SPM-18</td></tr>
                    <tr><td>Specimen.collection.extension:specimen-specialHandling.valueCoding.code</td><td>Raw specimen/biopsy - High risk reason, Raw specimen/biopsy - Option for products of conception</td><td>SPM-16.2, SPM-15</td></tr>
                    <tr><td>Specimen.collection.bodySite</td><td>Raw specimen/biopsy - Biopsy site</td><td>SPM-8/SPM-9</td></tr>
                    <tr><td>Specimen.status</td><td>Raw specimen/biopsy - Sample to follow</td><td>N/A implied through absence of SPM segment in test order</td></tr>
                    <tr><td>Specimen.condition</td><td>Extracted specimen - State</td><td>SPM-24</td></tr>
                    <tr><td>Specimen.processing.timeDateTime</td><td>Extracted specimen - Extracted date</td><td>OBR-7 attached to processing procedure in SAC-30</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#extension:sampleCategory">extension:sampleCategory</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#type">type</a>
- <a href="#subject">subject</a>
- <a href="#receivedTime">receivedTime</a>
- <a href="#parent">parent</a>
- <a href="#request">request</a>
- <a href="#collection">collection</a>
- <a href="#processing">processing</a>
- <a href="#container">container</a>
- <a href="#condition">condition</a>

<a name="extension:sampleCategory"></a>
#### extension:sampleCategory
Allows the categorisation of a sample into either tumour or germline. Additional terms may be added upon review though the valueCodeableConcept.text field MAY be used as a free text representation if needed.
```json
"extension": [
        {
            "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-SampleCategory",
            "valueCodeableConcept": {
                "coding": [
                    {
                        "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-SampleCategory",
                        "code": "germline",
                        "display": "Germline"
                    }
                ]
            }
        }
    ]
```

<a name="identifier"></a>
#### identifier
Multiple identifiers MAY be assigned to a sample as it travels between labs. Each lab SHOULD append their local identifier to the identifier array if needed, ensuring either the system or assigner is able to disambiguate any identifiers from possibly overlapping numbers from other organizations
```json
"identifier":  [
        {
            "system": "https://fhir.add.nhs.uk/Id/specimenId",
            "value": "RGT03135"
        }
    ],
```

<a name="status"></a>
#### status
If a sample has not been collected or the quality is such that is cannot be processed, it SHALL be marked as 'unavailable' or 'unsatisfactory', respectively. Otherwise the sample SHOULD be marked as available.
```json
"status": "unavailable",
```

<a name="type"></a>
#### type
The sample type, SNOMED CT preferred.
```json
"type": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "445295009",
                "display": "Blood specimen with EDTA"
            }
        ]
    },
```

<a name="subject"></a>
#### subject
SHALL be provided. This SHOULD be a reference to the Patient resource or the identifier, NHS number, for the patient.

Samples collected from a Fetus SHOULD reference a Patient resource for the Fetus. This should then be linked to relevant maternal/paternal resources through the RelatedPerson resource. Further information can be found on the {{pagelink:Fetus-Management}} clinical scenario. It is not envisaged that samples would need to be linked to more than one person e.g. both fetus and mother, though this assumption will be tested within the Alpha phase of the Genomic Medicine Service.
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="receivedTime"></a>
#### receivedTime
SHOULD be updated upon receipt at a destination lab
```json
"receivedTime": "2023-09-18T18:30:00Z"
```

<a name="parent"></a>
#### parent
If a sample has been split into multiple parts, each SHOULD be represented using an additional Specimen resource, referencing the parent sample through the parent element.
```json
"parent": [
        {
            "reference": "Specimen/Specimen-BloodEDTA-Example"
        }
    ],
```

<a name="request"></a>
#### request
SHALL be provided. This SHOULD be a reference to the request which initiated collection of the sample. SHOULD be updated (added to) if used in further ServiceRequests, e.g. as part of reanalysis
```json
"request":  [
        {
            "reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-Example"
        }
    ]
```

<a name="collection"></a>
#### collection
Additional information which can be collected about the circumstances under which as sample was collected, if relevant. This include extensions for specialHandling of the sample, e.g. due to high risk of infection, as well as an extension to bodySite to extend the coding to a BodyStructure reference, for more detailed collection of structural information e.g. where tumour morphology and topography need to be collected.

Where the collector is an Organization, or where the individual is not known, ODS codes MAY be used as identifiers in place of SDS-User-IDs. However, if referencing a resource, the PractitionerRole resource SHOULD still be referenced. In this case the `PractitionerRole.identifier` and `PractitionerRole.practitioner` reference would not be filled, leaving only the reference to an Organization from `PractitionerRole.organization`.
```json
"collection": {
        "collector": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/sds-user-id",
                "value": "999999"
            }
        },
        "collectedDateTime": "2022-07-11T09:00:00Z",
        "quantity": {
            "system": "http://unitsofmeasure.org",
            "code": "mL",
            "value": 2.5
        },
        "method": {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "129300006",
                    "display": "Puncture - action"
                }
            ]
        },
        "bodySite": {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "14975008",
                    "display": "Forearm structure (body structure)"
                }
            ]
        }
    },
```

<a name="processing"></a>
#### processing
SHOULD be updated if processing occurs on the sample which affects later use, e.g. additives added
```json
"processing": [
    {
      "description": "Acidify to pH < 3.0 with 6 N HCl.",
      "procedure": {
        "coding": [
          {
            "system": "http://terminology.hl7.org/CodeSystem/v2-0373",
            "code": "ACID"
          }
        ]
      },
      "additive": [
        {
          "display": "6 N HCl"
        }
      ],
      "timeDateTime": "2015-08-18T08:10:00Z"
    }
  ],
```

<a name="container"></a>
#### container
In a future version of UK Core, R5 changes to the container BackboneElement will be backported to support capturing of storage location for a sample (through `container.location`) and recursive capture of device identifiers (e.g. tube, well, rack, freezer through `container.device`). 

Additional examples/guidance will be provided within this IG once the changes to the FHIR R4 UK Core package have been published.

Sample tracking information SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing, on either the output or input elements. This information MAY include consignment number, destination, date sent etc.

<a name="condition"></a>
#### condition
Used to record the condition of a specimen. Within Genomics, SHOULD be used to record the fixed/frozen state, using the UK Core bound ValueSet.
```json
"condition":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-BiopsyState",
                    "code": "fresh-frozen",
                    "display": "Fresh Frozen"
                }
            ]
        }
    ]
```
