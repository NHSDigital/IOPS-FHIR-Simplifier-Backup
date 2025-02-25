---
topic: Profile-UKCore-Specimen
issue: UKCore-Specimen
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen
expand: yes
---

## StructureDefinition {{variable:issue}}


Used to capture information on Samples which will undergo or have undergone processing for genomic testing. 

Within FHIR R4, there is no way to capture location against a sample to aid tracking, one of the key requirements of the Genomic Medicine Service. Investigation of a possible solution through backporting the container.location element within R5 is currently being investigated. Until this backport is adopted by UK Core, the location of samples, including interactions to manage and track samples, will be performed through changes to Task resources generated on submission of a ServiceRequest.

A diagram illustrating the links between resources is provided below (Duo Scenario)

**Note: links from ServiceRequest.supportingInfo to samples collected after submission are pending further investigation**

<plantuml>
@startuml
!pragma ratio 0.3
scale 1100 width
entity SR as "Test Request" <<ServiceRequest>>
entity P1 as "Proband" <<Patient>>
entity S1 as "New Sample from Proband" <<Specimen>>
entity SP1 as "Pre-existing Sample from Proband" <<Specimen>>
entity S2 as "New Sample from Consultand A" <<Specimen>>
together {
  entity RP as "Relationship of Consultand A to Proband" <<RelatedPerson>>
  entity P2 as "Consultand A" <<Patient>>
'  entity C2 as "RoD Consultand A" <<Consent>>
}
'together {
'  entity FMH as "Pedigree Person B" <<FamilyMemberHistory>> {
'    Not a participant in the test request
'  }
'  entity C1 as "RoD Proband" <<Consent>>
'}
SR -d-> P1 : ServiceRequest.subject
together {
'  SR -d-> C1 : ServiceRequest.supportingInfo
'  SR -d-> FMH : ServiceRequest.supportingInfo
  SR -d-> RP : ServiceRequest.supportingInfo
  SR -d-> P2 : ServiceRequest.supportingInfo
'  SR -d-> C2 : ServiceRequest.supportingInfo
}
'C1 -d-> P1 : Consent.patient
'FMH -d-> P1 : FamilyMemberHistory.patient
SP1 -d-> P1 : Specimen.subject
SR -d-> SP1 : ServiceRequest.specimen 
S1 -d-> P1 : Specimen.subject
S1 -u-> SR : Specimen.request
RP -r-> P1 : RelatedPerson.patient
P2 -r-> RP : Patient.link
S2 -d-> P2 : Specimen.subject
S2 -u-> SR : Specimen.request
'C2 -d-> P2 : Consent.patient
'S1 -l[hidden]-> C1
'S1 -l[hidden]-> FMH
'P2 -r[hidden]-> RP

@enduml
</plantuml>

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank">https://fhir.hl7.org.uk/StructureDefinition/UKCore-Specimen</a>| [UKCore]() | trial-use |

<br>
{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <br>
            <ul>
                    <li>
                    {{pagelink:Specimen-BloodEDTA-Example}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-BloodEDTA-WithCollectionDetails-Example}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-BoneMarrowAspiration-Example}}
                    </li>
               
                    <li>
                    {{pagelink:Specimen-JamesMetcalfeBloodEDTA-Example}}
                    </li>
               
                    <li>
                    {{pagelink:Specimen-PheobeSmitham-Example}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-PheobeSmithamFather-Example}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-PheobeSmithamMother-Example}}
                    </li>
               
                    <li>
                    {{pagelink:Specimen-RyanneBoulderPartnerSaliva-Example}}
                    </li>
               
                    <li>
                    {{pagelink:Specimen-RyanneBoulderSaliva-Example}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-CancerSolidTumor-Example}}
                    </li>
               
                    <li>
                    {{pagelink:Specimen-TissueResection-Example}}
                    </li>
           
                    <li>
                    {{pagelink:Home/Examples/Specimen/Specimen-MichealJonesBlood-Minimal.page.md}}
                    </li>
                
                    <li>
                    {{pagelink:Specimen-MichaelJonesBloodWithCollectionDetails-Example}}
                    </li>
                
            </ul>
        </div>

<div id="Mappings" class="tabcontent">
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
  
<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

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
<h4 class='additional-Guidance-Submenu'> extension:sampleCategory </h4>
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
<h4 class='additional-Guidance-Submenu'> identifier </h4>
Multiple identifiers MAY be assigned to a sample as it travels between labs. Each lab SHOULD append their local identifier to the identifier array if needed, ensuring either the system or assigner, is able to disambiguate any identifiers from possibly overlapping numbers from other organizations. Assigner is preferred in this case (see identifier example on the {{pagelink:UKcore-Patient}} page for further guidance)

Note: accessionIdentifier is unused by the Genomic Medicine Service to facilitate movement of samples across organizational boundaries.

```json
"identifier":  [
        {
            "system": "https://fhir.add.nhs.uk/Id/specimenId",
            "value": "RGT03135"
        }
    ],
```

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
If a Specimen has not been collected, the status SHOULD be marked as 'unavailable'. If the quality of the Specimen is such that it cannot be processed, the status SHOULD be 'unsatisfactory' (this is equivalent to a QC status of Failed). If the Specimen passes quality control, the status SHOULD be set as 'available

```json
"status": "unsatisfactory",
```

<a name="type"></a>
<h4 class='additional-Guidance-Submenu'> type </h4>
The sample type, SNOMED CT preferred. Used to differentiate between raw and extracted (DNA) samples.

**ConceptMaps for the allowed values for primary (raw) and final (extracted DNA) samples upon release of MDSv1.04, to aid identification of whether a sample is primary vs. final** 

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
<h4 class='additional-Guidance-Submenu'> subject </h4>
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
<h4 class='additional-Guidance-Submenu'> receivedTime </h4>
SHOULD be updated upon receipt at a destination lab

```json
"receivedTime": "2023-09-18T18:30:00Z"
```

<a name="parent"></a>
<h4 class='additional-Guidance-Submenu'> parent </h4>
If a sample has been split into multiple parts, such as DNA being extracted from a primary sample, each SHOULD be represented using an additional Specimen resource, referencing the parent sample through the parent element.

The central Order Management broker will only create Tasks for Specimen resources which do not have a parent element, i.e. primary samples. If required, clients can create Tasks for processing of derivative samples manually. 

```json
"parent": [
        {
            "reference": "Specimen/Specimen-BloodEDTA-Example"
        }
    ],
```

<a name="request"></a>
<h4 class='additional-Guidance-Submenu'> request </h4>
SHALL be provided. This SHOULD be a reference to the request which initiated collection of the sample. SHALL NOT be updated if the sample is used for another test e.g. for re-analysis. In the case that a Specimen needs to be processed as part of a new request, e.g. using a sample in storage, the ServiceRequest SHALL reference the pre-existing sample via ServiceRequest.specimen. 

```json
"request":  [
        {
            "reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-Example"
        }
    ]
```

<a name="collection"></a>
<h4 class='additional-Guidance-Submenu'> collection </h4>
Additional information which can be collected about the circumstances under which as sample was collected, if relevant. This include extensions for specialHandling of the sample, e.g. due to high risk of infection, as well as an extension to bodySite to extend the coding to a BodyStructure reference, for more detailed collection of structural information e.g. where tumour morphology and topography need to be collected.

Where the collector is an Organization, or where the individual is not known, ODS codes MAY be used as identifiers in place of SDS-User-IDs. However, if referencing a resource, the PractitionerRole resource SHOULD still be referenced. In this case the `PractitionerRole.identifier` and `PractitionerRole.practitioner` reference would not be filled, leaving only the reference to an Organization from `PractitionerRole.organization`.

**Note on quanitities**

The Specimen.collection.quantity is the amount of the sample collected at collection time. This quantity does not change as the sample is processed.

The Specimen.container.specimenQuantity is the amount of sample remaining in a container, this is equivalent to GEL 1001 banked volume. This value should be updated as the specimen is used.

If a specimen is split, additional specimen resources SHOULD be created (referencing the parent specimen), with individual container.specimenQuantity values.

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
<h4 class='additional-Guidance-Submenu'> processing </h4>
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
<h4 class='additional-Guidance-Submenu'> container </h4>
The UK Core STU3 version of Specimen backports the R5 changes to the container BackboneElement to support capturing of storage location for a sample (through `container.location`) and recursive capture of device identifiers (e.g. tube, well, rack, freezer through `container.device`). 

Additional examples/guidance will be provided within this IG once use of the fields has been appropriately tested.

Sample tracking information SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing, on either the output or input elements. This information MAY include consignment number, destination, date sent etc.

If known, the container type SHOULD be populated, using the example bound ValueSet, in SNOMED CT. If an appropraite code cannot be found, the specimen container type should be populated using free text, in `Specimen.container.type.text`. Additional container elements, such as capacity or specimenQuantity MAY be populated if known.
```json
"container":  [
        {
            "extension":  [
                {
                    "url": "http://hl7.org/fhir/5.0/StructureDefinition/extension-Specimen.container.location",
                    "valueReference": {
                            "reference": "Location/Location-NTGLHFridge-Example"
                    }
                }
            ],
            "type": {
                "coding": [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "702284002",
                        "display": "Non-evacuated blood collection tube, lithium heparin"
                    }
                ]
            }
        }
    ]
```

<a name="condition"></a>
<h4 class='additional-Guidance-Submenu'> condition </h4>
Used to record the condition of a specimen. Within Genomics, SHOULD be used to record the fixed/frozen state, using the UK Core bound ValueSet.

```json
"condition":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-PrimarySampleState",
                    "code": "fresh",
                    "display": "Fresh"
                }
            ]
        }
    ]
```

---