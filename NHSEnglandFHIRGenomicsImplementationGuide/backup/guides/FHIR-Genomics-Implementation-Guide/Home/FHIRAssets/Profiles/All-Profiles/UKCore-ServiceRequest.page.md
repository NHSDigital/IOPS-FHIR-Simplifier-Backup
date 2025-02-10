---
topic: Profile-UKCore-ServiceRequest
issue: UKCore-ServiceRequest
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest
expand: yes
---

## StructureDefinition {{variable:issue}}

Focal resource for test order messages. All additional information or resources SHOULD be linked back to the ServiceRequest or be referenced from the ServiceRequest directly. 

ServiceRequests which have been updated post submission SHALL be accompanied by Provenance resources, referencing the ServiceRequest which detail when the resource was changed, who made the change and why.

An illustrative diagram of the links between ServiceRequests and other resources is provided below. 
**Note: not all resource links are represented, to increase legibility of the diagram.** 

<plantuml>
@startuml
!pragma ratio 0.3
left to right direction
scale 1100 width

entity SR as "Test Request" <<ServiceRequest>>
entity P1 as "Patient" <<Patient>>
entity S1 as "Raw Sample" <<Specimen>> {
  Collected after test submission
}
entity PR as "Requester" <<PractitionerRole>>
entity Prov as "Change History" <<Provenance>>
entity T1 as "Process Genomic Test Request" <<Task>>
entity SRP as "Parent Request" <<ServiceRequest>>
together {
  entity RP as "Consultand Relationship" <<RelatedPerson>>
  entity P2 as "Consultand" <<Patient>>
  entity C1 as "Record of Discussion" <<Consent>>
  entity O1 as "Clinical Information" <<Observation>>
}

T1 --> SR : Task.focus
T1 --> P1 : Task.for
T1 --> PR : Task.requester
SR --> P1 : ServiceRequest.subject
SR --> PR : ServiceRequest.requester
SR --> SRP : ServiceRequest.basedOn
SR --> O1 : ServiceRequest.supportingInfo
SR --> RP : ServiceRequest.supportingInfo
SR --> P2 : ServiceRequest.supportingInfo
SR --> Prov : ServiceRequest.relevantHistory
SR --> C1 : ServiceRequest.supportingInfo
Prov --> SR : Provenance.entity
S1 --> P1 : Specimen.subject
S1 --> SR : Specimen.request
RP --> P1 : RelatedPerson.patient
P2 --> RP : Patient.link
O1 --> P1 : Observation.subject
C1 --> SR : Consent.provision

@enduml
</plantuml>

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank">https://fhir.hl7.org.uk/StructureDefinition/UKCore-ServiceRequest</a> | [UKCore]() | trial-use |


{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <br>
            <ul>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrder-VariantReinterpretation-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-Cancellation-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-CancerSolidTumor-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-CascadeTesting-Example}}
                    </li>
              
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-DeceasedPatient-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-FetalScenario-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-FollowupTest-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-HaemOncology-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-HaemOncologyUpdated-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-NewFollowupTest-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-OutOfCountry-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderForm-UsingStoredSample-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-Cancellation-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-FetalScenario-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-SolidTumor-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-SavedTestOrder-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-SavedTestOrderUpdated-CascadeTesting-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-SavedTestOrderUpdated-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-SavedTestOrderWGS-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-TestOrderForm-StorageOfMaterial-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-WGSTestOrderForm-DirectToLab-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-WGSTestOrderForm-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-WGSTestOrderForm-TrioTestingProband-Example}}
                    </li>
   
                    <li>
                    {{pagelink:ServiceRequest-WGSTestOrderFormUpdated-DirectToLab-Example}}
                    </li>
                    <li>
                    {{pagelink:ServiceRequest-WGSTestOrderFormUpdated-TrioTesting-Example}}
                    </li>
                </li>
 </div>

<div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>ServiceRequest.requester</td><td>Requester (more details in PractitionerRole resource mappings), PLCM activity - Commissioned service category code, Previous genomic report - Original requester full name, Previous genomic report - Original requester organisation ODS code, Previous genomic report - Original requester reason for request, Previous non genomic report - Original requester full name, Previous non genomic report - Original requester organisation ODS code, Previous non genomic report - Original requester reason for request</td><td>Various ORC/STF segments</td></tr>
                    <tr><td>ServiceRequest.extension:additionalContact</td><td>Additional Contact (more details in PractitionerRole resource mappings)</td><td>Various STF segments</td></tr>
                    <tr><td>ServiceRequest.subject</td><td>Patient (more details in Patient resource mappings), Patient - Is relative</td><td>First PID segment in OML message, relatives referenced through NK1 segments</td></tr>
                    <tr><td>ServiceRequest.identifier</td><td>Test request - Test request id, PLCM activity - NGIS referral identifier, Previous genomic report - Report lab test number</td><td>ORC-2, ORC-3</td></tr>
                    <tr><td>ServiceRequest.extension:coverage</td><td>Test request - Payment status</td><td>IN1-15</td></tr>
                    <tr><td>ServiceRequest.authoredOn</td><td>Test request - Date and time request sent, PLCM activity - Financial month, PLCM activity - Financial year, PLCM activity - Turnaround time (calendar days)</td><td>ORC-9 (for TAT subtracted from OBR-7)</td></tr>
                    <tr><td>ServiceRequest.priority</td><td>Test request - Is urgent</td><td>TQ1-9</td></tr>
                    <tr><td>ServiceRequest.extension:priorityReason</td><td>Test request - Urgency reason</td><td>N/A could possibly use TQ1-10</td></tr>
                    <tr><td>ServiceRequest.code.coding.system</td><td>Test request - Test Directory version</td><td>OBR-4.3</td></tr>
                    <tr><td>ServiceRequest.code</td><td>Test request - CI code, Test request - CITT code, PLCM activity - Service code, PLCM activity - Point of delivery code, PLCM activity - Local point of delivery code, PLCM activity - Test method code</td><td>OBR-4</td></tr>
                    <tr><td>ServiceRequest.orderDetail</td><td>Test request - CI code for multipurpose CITT, Test request - Type of reanalysis, Test request - DNA storage information</td><td>NTE segment attached to OBR</td></tr>
                    <tr><td>ServiceRequest.category</td><td>Test request - Reason for testing, Test request - Reason for reanalysis</td><td>Likely ORC-29</td></tr>
                    <tr><td>ServiceRequest.supportingInfo</td><td>Test request - Detail of reason for reanalysis, Test request - Further information</td><td>NTE segments linked to OBR segment for reanalysis reason, Additional segments attached to ORC/OBR</td></tr>
                    <tr><td>ServiceRequest.occurrenceDateTime</td><td>Test request - Date report required by</td><td>OBR-8</td></tr>
                    <tr><td>ServiceRequest.performer</td><td>PLCM activity - ODS code of organisation commissioned to deliver requested test</td><td>PRD-7 where PRD-1=RT</td></tr>
                    <tr><td>ServiceRequest.note</td><td>Raw specimen/biopsy - Sample to follow reason</td><td>NTE segment attached to ORC</td></tr>
                </table>
</div>
 
<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#extension:additionalContact">extension:additionalContact</a>
- <a href="#extension:coverage">extension:coverage</a>
- <a href="#identifier">identifier</a>
- <a href="#basedOn">basedOn</a>
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
<!--- <a href="#reasonCode">reasonCode</a>-->
- <a href="#reasonReference">reasonReference</a>
- <a href="#supportingInfo">supportingInfo</a>
- <a href="#specimen">specimen</a>
- <a href="#note">note</a>

<a name="extension:additionalContact"></a>
<h4 class='additional-Guidance-Submenu'> extension:additionalContact </h4>

Extension used for recording additional personnel who should be contacted regarding questions related to a test order. This is separate from the requester or reporting address.

The additional contact SHOULD be a reference to a PractitionerRole resource wherever possible and SHALL contain contact details for the practitioner.

Additionally, where are there multiple practitioners involved in providing care who need to be listed as contacts, the contact details for each practitioner (or service) SHOULD be specified through additional additionalContact entries.
```json
{
    "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AdditionalContact",
    "valueReference": {
        "reference": "PractitionerRole/PractitionerRole-AdditionalContact-Example"
    }
},
```

<a name="extension:coverage"></a>
<h4 class='additional-Guidance-Submenu'> extension:coverage </h4>
SHALL be present for Genomic Order Management test orders. Extension for recording how work against the test order is being funded. The ValueSet bound to this extension is currently under review by the NHS England Genomics Informatics Working Advisory Group and subject to change.

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
<h4 class='additional-Guidance-Submenu'> identifier </h4>
Automatically assigned by the central service, though source systems MAY provide a local identifier for tracking within their own system, in which case the central order number is appended to the identifiers array.

```json
    "identifier":  [
        {
            "system": "https://fhir.nhs.uk/Id/GMSOrder",
            "value": "ROA43728"
        }
    ],
```

<a name="basedOn"></a>
<h4 class='additional-Guidance-Submenu'> basedOn </h4>
SHALL reference a parent request where this ServiceRequest is based on a previous request, e.g. in the case of reanalysis and cascade testing, or Germline Late tests in the Tumour First/Germline Late scenario.

```json
"basedOn":  [
        {
            "reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-FatherOfFayMutlow-Example"
        }
    ],
```

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
SHALL be provided. ServiceRequests SHOULD be marked as 'draft' until submitted, after which they will be marked as 'active' automatically by the central GMS system. 

A ServiceRequest may be marked as 'on-hold' if work against it cannot continue temporarily, e.g. due to certain prerequisite information not being provided. A ServiceRequest SHOULD be marked as 'revoked' if cancelled, either by the lab performing work against the order or at the request of the requesting clinician, though in each case a Provenance resource SHALL be provided to capture why the state change has occurred. The requesting clinician may also mark the ServiceRequest as entered-in-error, though implications for work already in progress needs to be investigated further.

A ServiceRequest SHOULD only be marked as completed by the requesting clinician upon receipt and review of the resulting DiagnosticReport.

For the full list of expected/supported ServiceRequest statuses, please see the table below: 

|Status|Description|Genomic workflow usage|
|--|--|--|
|Draft|The request has been created but is not yet complete or ready for action.|Saved but not submitted to central service (out of scope for Alpha).|
|Active|The request is in force and ready to be acted upon.|Submitted to central service.|
|On Hold|The request (and any implicit authorization to act) has been temporarily withdrawn but is expected to resume in the future.|Issue with the authorization for the test (potentially recoverable), not expected to be driven by on-hold statuses of Tasks.|
|Revoked|The request (and any implicit authorization to act) has been terminated prior to the known full completion of the intended actions. No further activity should occur.|Unrecoverable issue with order. Either used when the test is no longer needed or there is an is an unrecoverable failure with its fulfillment (driven by the requesting clinician). This status will propagate down to any Tasks which have not already moved into in-progress, Tasks not started will be marked with the status of cancelled.|
|Completed|The activity described by the request has been fully performed. No further activity will occur.|Completed order, marked by requestor once DiagnosticReport is received and accepted.|
|Entered in Error|This request should never have existed and should be considered 'void'. (It is possible that real-world decisions were based on it. If real-world activity has occurred, the status should be "revoked" rather than "entered-in-error".)|MAY be used for ServiceRequests created in error, can only be set if no Tasks have been started. If a Task has been moved out of its initial state, the status of Revoked SHOULD be used instead. This status will propagate down to Tasks, marking the tasks as entered-in-error.|
|Unknown|The authoring/source system does not know which of the status values currently applies for this request. Note: This concept is not to be used for "other" - one of the listed statuses is presumed to apply, but the authoring/source system does not know which.|Should not be used.|

```json
"status": "active",
```

<a name="intent"></a>
<h4 class='additional-Guidance-Submenu'> intent </h4>
SHALL be provided. ServiceRequests SHOULD be marked as 'order' unless they have been raised by a lab in response to an existing ServiceRequest, in which case they SHOULD be marked as 'reflex-order'. For reflex orders, the ServiceRequest.basedOn field SHALL be populated with the original ServiceRequest, for traceability.

```json
"intent": "order",
```

<a name="category"></a>
<h4 class='additional-Guidance-Submenu'> category </h4>
ServiceRequests SHOULD use the [Genomics Sequencing Category](https://simplifier.net/resolve?scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release&filepath=package/ValueSet-UKCore-GenomeSequencingCategory.json) ValueSet when categorising the test order in order to aid analytics (e.g. PLCM). This list is pending review from the Informatics Working Advisory Group, after which a full list of possible categorisations will be finalised.

category SHOULD additioanlly be populated with the type of request being ordered e.g. Diagnostic, Carrier, Predictive, Stored DNA etc. The final list of applicable codes which can be selected is still under review, the {{pagelink:Home/FHIRAssets/CodeSystems/Genomic-Reason-for-Testing.page.md}} CodeSystem SHOULD be used for this categorisation.
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
        },
        {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/reasonfortesting-genomics",
                    "code": "diagnostic",
                    "display": "Diagnostic"
                }
            ]
        }
    ],
```

<a name="priority"></a>
<h4 class='additional-Guidance-Submenu'> priority </h4>
ServiceRequests marked as urgent (i.e. not routine) SHOULD populate the extension:priorityReason with why an urgent test is being requested. This SHOULD ideally be coded using SNOMED CT concepts. Multiple priorityReason extensions are allowed within a single ServiceRequest in order to aid post-coordination.

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
<h4 class='additional-Guidance-Submenu'> doNotPerform </h4> 
For the purposes of Genomic Test Ordering, the doNotPerform field SHALL NOT be used. All ServiceRequests requests received by the system will be assumed to be orders for services/testing.

<a name="code"></a>
<h4 class='additional-Guidance-Submenu'> code </h4>
SHALL be provided. Code SHOULD contain the CI or CITT Test Directory code, currently available at https://www.england.nhs.uk/publication/national-genomic-test-directories/. There is currently no CodeSystem or queryable API for retrieving codes but work to address this is underway within the NHS England Genomics Unit.

Codes from the Genomic Test Directory SHOULD also specify the version number of the test directory at the time the test is being ordered, to ensure the test methods used are consistent with that version of the directory. 

```json
"code": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/England-GenomicTestDirectory",
                "code": "R67.2",
                "display": "Monogenic hearing loss",
                "version": "7"
            }
        ]
    },
```

<a name="orderDetail"></a>
<h4 class='additional-Guidance-Submenu'> orderDetail </h4>
If multiple codes are being requested within one Test Order, these SHOULD be represented using the 'orderDetail' field, with the main indication captured using the 'code' field above. If completely separate pathways/samples etc. are required for processing against the codes, it is expected these would be requested via multiple ServiceRequests instead of a single ServiceRequest with multiple orderDetail codes. The exact cut-off for when orderDetail vs. multiple ServiceRequest should be used is still being investigated. 
An appropriate code(Panel codes) SHOULD come from the following NamingSystem: {{pagelink:England-GenomicTestPanelCode}}

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
<h4 class='additional-Guidance-Submenu'> subject </h4>
SHALL be provided. Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS

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
<h4 class='additional-Guidance-Submenu'> occurrence[x] </h4>
If a result is required by a specific date, this MAY be indicated though occurrenceDateTime, though there is no guarantee from the GMS that the ServiceRequest will be processed in the time frame specified.

```json
"occurrenceDateTime": "2023-08-25",
```

<a name="authoredOn"></a>
<h4 class='additional-Guidance-Submenu'> autoredOn </h4> 
SHALL be populated by the client upon submission, either manually by the user or automatically by the system integrating with the central GMS.

```json
"authoredOn": "2023-08-05",
```

<a name="requester"></a>
<h4 class='additional-Guidance-Submenu'> requester </h4>
SHALL be populated on all ServiceRequests submitted to the central GMS. This SHALL reference a PractitionerRole resource also submitted to the system (either within a single transaction or previously POSTed).

```json
"requester": {
        "reference": "PractitionerRole/PractitionerRole-GeneSmithENT-Example"
    },
```

<a name="performer"></a>
<h4 class='additional-Guidance-Submenu'> performer </h4>
Allows a requester to assign processing of the ServiceRequest to a particular organization (e.g. a remote GLH). The performer field SHOULD be populated with the ODS code for the managing organization/GLH. 

In the future state, ServiceRequests may be kept open, by not specifying a performer, allowing them to be picked up by the local GLH or otherwise routed based on by test routing (TBC). 

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

<!--<a name="reasonCode"></a>
<h4 class='additional-Guidance-Submenu'> reasonCode </h4>
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
```-->
<a name="reasonReference"></a>
<h4 class='additional-Guidance-Submenu'> reasonReference </h4>
Reference SHOULD be associated to the primary condition being tested for.
i.e,

```json
"reasonReference": {
        "reference": "Condition/Condition-LungTumor-Example"
    },
```

<a name="supportingInfo"></a>
<h4 class='additional-Guidance-Submenu'> supportingInfo </h4>
Any clinical information provided about the patient for whom the testing is being requested SHALL be referenced though the supportingInfo field, to ensure all the information relevant to the ServiceRequest can be easily retrieved. This includes Observations, Conditions, Procedures, FamilyMemberHistories etc.

This also includes resources related to family members included as part of testing (consultands), e.g. in Duo/Trio scenarios. In this instance, RelatedPerson and Patient resource references for the consultands SHALL be added to the supportingInfo array, as well as any clinical resources related to these individuals. This is to ensure the number of participants for a given test can be calculated correctly, e.g. through counting the number of RelatedPerson resources referenced from ServiceRequest.supportingInfo plus the subject of the ServiceRequest itself (the proband).

For WGS testing, where Records of Discussion are required in order to process the test, Consent resources SHOULD also be added to the supportingInfo array once available.

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
        },
        {
            "reference": "RelatedPerson/RelatedPerson-AliceSmithamProbandMother-Example"
        },
        {
            "reference": "Patient/Patient-PheobeSmithamMother-Example"
        },
    ],
```

<a name="specimen"></a>
<h4 class='additional-Guidance-Submenu'> specimen </h4>
ServiceRequests where the required samples already exist, e.g. in the case where a specimen already in storage needs to be processed, SHOULD reference these samples through the ServiceRequest.specimen field. Where samples need to be collected to support testing, these SHOULD instead reference the ServiceRequest, through Specimen.request (i.e. the service request has prompted collection of the sample), and these Specimen resources do not need to be referenced from within ServiceRequest.supportingInfo. The referenced Specimen resources SHOULD either be contained within the test order transaction bundle or already exist on the central GMS.

In the case of Reanalysis or Reinterpretation tests, Specimens related to previous ServiceRequest are not required to be added to the new test request. The links from the previous ServiceRequest can be followed to identify the Specimens that resulted in the data being reanalysed, e.g. (reanalysis) ServiceRequest.basedOn -> (prior) ServiceRequest, (prior) ServiceRequest <- (original) Specimen.request

```json
"specimen": [
        {
            "reference": "Specimen/Specimen-BloodSerum-Example"
        }
    ],
```

<a name="note"></a>
<h4 class='additional-Guidance-Submenu'> note </h4>
Any information which cannot be readily be structured SHOULD be entered into the note field, though prolific use of the field to capture clinical information which better fits in level 3/4 FHIR resources is discouraged.

To support disambiguation of notes originating from different fields in a client system, the AnnotationType extension MAY be used, specifying the UI element name in text (coded elements for the full list of free text UI elements expected within Test Order forms is pending finalisation and addition to the Genomic Order Management MDS). The author element MAY also be used to reference a Practitioner, by identifier or name (string), indicating the person who created the note.
```json
"note":  [
        {
            "extension": [
                {
                    "url": "http://hl7.org/fhir/StructureDefinition/annotationType",
                    "valueCodeableConcept": {
                        "text": "Has any other members of the family previously had genomic testing (e.g. BRACA, NIPD testing etc)?"
                    }
                }
            ],
            "authorReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/sds-user-id",
                    "value": "9999999999"
                },
                "display": "Dr. Gene Smith"
            },
            "text": "No family history of genomic testing"
        }
    ]
```

---