## {{page-title}}

Focal resource for test order messages. All additional information or resources should be linked back to the ServiceRequest or be referenced from the ServiceRequest directly. 

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/ServiceRequest}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-MichaelJonesDYPDRequest}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-SavedTestOrder-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-SavedTestOrderUpdated-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-SavedTestOrderWGS-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:ServiceRequest-WGSTestOrderForm-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-ServiceRequest-Genomics'
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
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#extension:additionalContact">extension:additionalContact</a>
- <a href="#extension:coverage">extension:coverage</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#intent">intent</a>
- <a href="#category">category</a>
- <a href="#priority">priority</a>
- <a href="#doNotPerform">doNotPerform</a>
- <a href="#code">code</a>
- <a href="#orderDetail">orderDetail</a>
- <a href="#subject">subject</a>
- <a href="#occurrence">occurrence\[x\]</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#requester">requester</a>
- <a href="#performer">performer</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#supportingInfo">supportingInfo</a>
- <a href="#specimen">specimen</a>
- <a href="#note">note</a>
- <a href="#relevantHistory">relevantHistory</a>

<a name="extension:additionalContact"></a>
#### extension:additionalContact
Extension used for recording additional personnel who should be contacted regarding questions related to a test order. This is separate from the requester or reporting address.

The additional contact SHOULD be a reference to a PractitionerRole resource wherever possible.
```json
{
    "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact",
    "valueReference": {
        "reference": "PractitionerRole/PractitionerRole-AdditionalContact-Example"
    }
},
```

<a name="extension:coverage"></a>
#### extension:coverage
Extension for recording how work against the test order is being funded. The ValueSet bound to this extension is currently under review by the NHS England Genomics Informatics Working Advisory Group and subject to change.
```json
{
    "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage",
    "valueCoding": {
        "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-FundingCategory",
        "code": "nhs",
        "display": "NHS"
    }
}
```

<a name="identifier"></a>
#### identifier
Automatically assigned by the central service, though source systems can provide a local identifier for tracking within their own system, in which case the central order number is appended to the identifiers array.
```json
    "identifier":  [
        {
            "system": "https://fhir.nhs.uk/Id/GMSOrder",
            "value": "ROA43728"
        }
    ],
```

<a name="status"></a>
#### status
ServiceRequests should be marked as 'draft' until submitted, after which they will be marked as 'active' automatically by the central GMS system. 

A ServiceRequest may be marked as 'on-hold' if work against it cannot continue temporarily, e.g. due to certain prerequisite information not being provided. A ServiceRequest should be marked as 'revoked' if cancelled, either by the lab performing work against the order or at the request of the requesting clinician, though in each case a Provenance resource MUST be provided to capture why the state change has occurred. The requesting clinician may also mark the ServiceRequest as entered-in-error, though implications for work already in progress needs to be investigated further.

A ServiceRequest should only be marked as completed by the requesting clinician upon receipt and review of the resulting DiagnosticReport.
```json
"status": "active",
```

<a name="intent"></a>
#### intent
ServiceRequests SHOULD be marked as 'order' unless they have been raised by a lab in response to an existing ServiceRequest, in which case they should be marked as 'reflex-order'. For reflex orders, the ServiceRequest.basedOn field MUST be populated with the original ServiceRequest, for traceability.
```json
"intent": "order",
```

<a name="category"></a>
#### category
ServiceRequests SHOULD use the [Genomics Sequencing Category](https://simplifier.net/resolve?scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release&filepath=package/ValueSet-UKCore-GenomeSequencingCategory.json) ValueSet when categorising the test order in order to aid analytics (e.g. PLCM). This list is pending review from the Informatics Working Advisory Group, after which a full list of possible categorisations will be finalised.
```json
"category":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-GenomeSequencingCategory",
                    "code": "rare-disease-non-wgs",
                    "display": "Rare Disease - Non-WGS"
                }
            ]
        }
    ],
```

<a name="priority"></a>
#### priority
ServiceRequests marked as urgent (i.e. not routine) SHOULD populate the extension:priorityReason with why an urgent test is being requested. This should ideally be coded using SNOMED CT concepts. Multiple priorityReason extensions are allowed within a single ServiceRequest in order to aid post-coordination.
```json
"priority": "urgent",
"_priority": {
        "extension" : [ 
            {
                "url" : "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PriorityReason",
                "valueCodeableConcept" : {
                    "coding": [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "722480002",
                            "display": "Chemotherapy started"
                        }
                    ]
                }
            }
        ]
    }
```

<a name="doNotPerform"></a>
#### doNotPerform
For the purposes of Genomic Test Ordering, the doNotPerform field MUST not be used. All ServiceRequests requests received by the system will be assumed to be orders for services/testing.

<a name="code"></a>
#### code
Code SHOULD contain the CI or CITT Test Directory code, currently available at https://www.england.nhs.uk/publication/national-genomic-test-directories/. There is currently no CodeSystem or queryable API for retrieving codes but work to address this is underway within the NHS England Genomics Unit.
```json
"code": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/England-GenomicTestDirectory",
                "code": "R67.2",
                "display": "Monogenic hearing loss"
            }
        ]
    },
```

<a name="orderDetail"></a>
#### intent
If multiple codes are being requested within one Test Order, these SHOULD be represented using the 'orderDetail' field, with the main indication captured using the 'code' field above. If completely separate pathways/samples etc. are required for processing against the codes, it is expected these would be requested via multiple ServiceRequests instead of a single ServiceRequest with multiple orderDetail codes. The exact cut-off for when orderDetail vs. multiple ServiceRequest should be used is still being investigated.
```json
"orderDetail": [
    {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/England-GenomicTestDirectory",
                "code": "R67.1",
                "display": "Monogenic hearing loss"
            }
        ]
    }
],
```

<a name="subject"></a>
#### subject
Reference to the associated Patient. This can be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="occurrence"></a>
#### occurrence\[x\]
If a result is required by a specific date, this can be indicated though occurrenceDateTime, though there is no guarantee from the GMS that the ServiceRequest will be processed in the time frame specified.
```json
"occurrenceDateTime": "2023-08-25",
```

<a name="authoredOn"></a>
#### authoredOn
MUST be populated by the client upon submission, either manually by the user or automatically by the system integrating with the central GMS.
```json
"authoredOn": "2023-08-05",
```

<a name="requester"></a>
#### requester
MUST be populated on all ServiceRequests submitted to the central GMS. This MUST reference a PractitionerRole resource also submitted to the system (either within a single transaction or previously POSTed).
```json
"requester": {
        "reference": "PractitionerRole/PractitionerRole-GeneSmithENT-Example"
    },
```

<a name="performer"></a>
#### performer
If a requester wants to assign processing of the ServiceRequest to a particular organization (e.g. a remote GLH) as opposed to leaving the ServiceRequest open, to be picked up by the local GLH or otherwise routed based on by test routing (TBC), then the performer field should be populated with the ODS code for the organization.
```json
"performer": [
        {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "RGT01"
            }
        }
    ]
```

<a name="reasonCode"></a>
#### reasonCode
reasonCode SHOULD be populated with the type of request being ordered e.g. Diagnostic, Carrier, Predictive, Stored DNA etc. The final list of applicable codes which can be selected is still under review. It is expected that a fixed list of SNOMED CT codes will be permissible, to allow appropriate categorisation by the central service.

This mapping is currently under review as the CI/CITT code is also technically the reason/indication for testing.
```json
"reasonCode":  [
        {
            "coding":  [
                {
                    "system": "http://snomed.info/sct",
                    "code": "103693007",
                    "display": "Diagnostic procedure"
                }
            ]
        }
    ],
```

<a name="supportingInfo"></a>
#### supportingInfo
Any clinical information provided about the patient for whom the testing is being requested MUST be referenced though the supportingInfo field, to ensure all the information relevant to the ServiceRequest can be easily retrieved. This includes Observations, Conditions, Procedures, FamilyMemberHistories etc.
```json
"supportingInfo":  [
        {
            "reference": "Observation/Observation-DiseaseStatus-Example"
        },
        {
            "reference": "Observation/Observation-GenomicEthnicity-Example"
        },
        {
            "reference": "Observation/Observation-NoPregnancy-Example"
        },
        {
            "reference": "FamilyMemberHistory/FamilyMemberHistory-NonConsanguinousUnion-Example"
        },
        {
            "reference": "Observation/Observation-NoTransplant-Example"
        },
        {
            "reference": "Observation/Observation-NoTransfusion-Example"
        },
        {
            "reference": "Condition/Condition-HearingLoss-Example"
        }
    ],
```

<a name="specimen"></a>
#### specimen
ServiceRequests for reanalysis, where the required samples already exist, SHOULD reference these samples through the specimen field. Where samples need to be collected to support testing, these should instead reference the ServiceRequest, through Specimen.request (i.e. the service request has prompted collection of the sample). The referenced Specimen resources should either be contained within the test order transaction bundle or already exist on the central GMS.
```json
"specimen": [
        {
            "reference": "Specimen/Specimen-BloodSerum-Example"
        }
    ],
```

<a name="note"></a>
#### note
Any information which cannot be readily be structured should be entered into the note field, though prolific use of the field to capture clinical information which better fits in level 3/4 FHIR resources is discouraged.
```json
"note":  [
        {
            "text": "No family history of genomic testing"
        }
    ]
```

<a name="relevantHistory"></a>
#### relevantHistory
ServiceRequests which have been updated post submission should reference Provenance resources which detail when the resource was changed, who made the change and why.
```json
"relevantHistory":  [
        {
            "reference": "Provenance/Provenance-ServiceRequestUpdate-Example"
        }
    ]
```