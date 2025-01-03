---
topic: Profile-Genomics-Task
issue: Task
subject: http://hl7.org/fhir/StructureDefinition/Task
expand: yes
---

## StructureDefinition {{variable:issue}}

The core workflow resource for managing processing of a ServiceRequest from order through to delivery of a DiagnosticReport and completion is Task. Task tracking is a core requirement of the central Genomic Medicine Service.

Each ServiceRequest submitted will instantiate a series of High Level Tasks, which MAY be assigned to different organizations for managing the test request e.g. Sample Processing, Interpretation, Reporting etc. The full list of possible Task types/codes, their associated business statuses, and status reasons is pending internal review.

Tasks will be automatically created by the central broker but updates to statuses and attachment of input/output resources is the responsibility of the assigned organizations.

An illustrative diagram of the links between ServiceRequests and Tasks are provided below (for the initial sample processing). **Note: not all resource links are represented, to increase legibility of the diagram**. In most cases, the full library of 10 tasks, as defined within {{pagelink:Genomic-Task-Code}}, will be 'spun-up', on submission of a Test order. Tasks related to Samples may be duplicated per Sample to allow tracking of work related to individual Samples as part of the same test request, or equally, may be omitted as in the case of Re-Analysis or Re-Interpretation where data from an existing sample is used, eliminating the need for additional wet-work. For the full cardinality breakdown see further guidance for the <a href="#code">Task.code</a> element.

<plantuml>
@startuml
!pragma ratio 0.3
left to right direction
scale 1100 width
entity SR as "Test Request" <<ServiceRequest>>
together {
'entity P1 as "Patient" <<Patient>>
entity S1 as "Raw Sample 1" <<Specimen>>
entity S2 as "Raw Sample 2" <<Specimen>>
'entity PR as "Requester" <<PractitionerRole>>
}
'entity S1a as "Extracted Sample 1" <<Specimen>>
'entity S2a as "Extracted Sample 2" <<Specimen>>
together {
entity T1 as "Process Genomic Test Request" <<Task>>
entity T2 as "Request & Sample Alignment" <<Task>>
entity T3 as "Sample Preparation 1" <<Task>>
entity T3a as "Sample Preparation 2" <<Task>>
}
'entity T4 as "Sample Processing 1" <<Task>>
'entity T4a as "Sample Processing 2" <<Task>>
'entity T5 as "Genetic/Genomic Data Processing 1" <<Task>>
'entity T5a as "Genetic/Genomic Data Processing 2" <<Task>>
'entity T6 as "Interpretation" <<Task>>
'entity T7 as "Produce Interim Report 1" <<Task>>
'entity T7a as "Produce Interim Report 2" <<Task>>
'entity T8 as "Genomic MDT" <<Task>>
'entity T9 as "Produce Final Report" <<Task>>
'entity T10 as "Distribute Report" <<Task>>
'entity DR1 as "Interim Report 1" <<DiagnosticReport>>
'entity DR2 as "Interim Report 2" <<DiagnosticReport>>
'entity DR3 as "Final Report" <<DiagnosticReport>>

'together {
'abstract O1 as "Managing Org" <<Organization>> {
'  e.g. Home GLH
'  Not an entity, referenced by identifier
'}
'abstract O2 as "Fulfilling Org 1" <<Organization>> {
'  e.g. Wet Lab/GEL
'  Not an entity, referenced by identifier
'}
'}
'abstract O3 as "Fulfilling Org 2" <<Organization>> {
'  e.g. Dry Lab/GEL
'  Not an entity, referenced by identifier
'}

T1 --> SR : Task.focus
T2 --> SR : Task.focus
T3 --> SR : Task.focus
T3a --> SR : Task.focus
'T4 --> SR : Task.focus
'T4a --> SR : Task.focus
'T5 --> SR : Task.focus
'T5a --> SR : Task.focus
'T6 --> SR : Task.focus
'T7 --> SR : Task.focus
'T7a --> SR : Task.focus
'T8 --> SR : Task.focus
'T9 --> SR : Task.focus
'T10 --> SR : Task.focus
'T1 --> P1 : Task.for
'T2 --> P1 : Task.for
'T3 --> P1 : Task.for
'T3a --> P1 : Task.for
'T4 --> P1 : Task.for
'T4a --> P1 : Task.for
'T5 --> P1 : Task.for
'T5a --> P1 : Task.for
'T6 --> P1 : Task.for
'T7 --> P1 : Task.for
'T7a --> P1 : Task.for
'T8 --> P1 : Task.for
'T9 --> P1 : Task.for
'T10 --> P1 : Task.for
T2 --> S1 : Task.output
T2 --> S2 : Task.output
T3 --> S1 : Task.input
T3a --> S2 : Task.input
'T4 --> S1 : Task.input
'T4a --> S2 : Task.input
'T4 --> S1a : Task.output
'T4a --> S2a : Task.output
'T5 --> S1a : Task.input
'T5a --> S2a : Task.input
'T7 --> DR1 : Task.output
'T7a --> DR2 : Task.output
'T8 --> DR1 : Task.input
'T8 --> DR2 : Task.input
'T9 --> DR3 : Task.output
'T10 --> DR3 : Task.input
'T1 --> O1 : Task.owner
'T2 --> O2 : Task.owner
'T3 --> O2 : Task.owner
'T3a --> O2 : Task.owner
'T4 --> O2 : Task.owner
'T4a --> O2 : Task.owner
'T5 --> O3 : Task.owner
'T5a --> O3 : Task.owner
'T6 --> O3 : Task.owner
'T7 --> O3 : Task.owner
'T7a --> O3 : Task.owner
'T8 --> O1 : Task.owner
'T9 --> O3 : Task.owner
'T10 --> O1 : Task.owner
'SR --> P1 : ServiceRequest.subject
'SR --> O1 : ServiceRequest.performer
'SR --> PR : ServiceRequest.requester
'S1 --> P1 : Specimen.subject
'S2 --> P1 : Specimen.subject
'S1 --> SR : Specimen.request
'S2 --> SR : Specimen.request
'S1a --> P1 : Specimen.subject
'S2a --> P1 : Specimen.subject
'S1a --> SR : Specimen.request
'S2a --> SR : Specimen.request
'DR1 --> SR : DiagnosticReport.basedOn
'DR1 --> P1 : DiagnosticReport.subject
'DR1 --> O3 : DiagnosticReport.performer
'DR1 --> S1 : DiagnosticReport.specimen
'DR2 --> SR : DiagnosticReport.basedOn
'DR2 --> P1 : DiagnosticReport.subject
'DR2 --> O3 : DiagnosticReport.performer
'DR2 --> S2 : DiagnosticReport.specimen
'DR3 --> SR : DiagnosticReport.basedOn
'DR3 --> P1 : DiagnosticReport.subject
'DR3 --> O1 : DiagnosticReport.performer
'DR3 --> S1 : DiagnosticReport.specimen
'DR3 --> S2 : DiagnosticReport.specimen


@enduml
</plantuml>

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Task](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Task&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}
 <br>       

<div id="Examples" class="tabcontent">
            <table>
                <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrder-Cancellation-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrder-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-FetalScenario-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-FollowupTest-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-HaemOncology-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Home/Examples/Task/Task-NonWGSRareDiseaseTestOrderAccepted-Reanalysis-Example.page.md}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-SufficientSample-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderCancelled-FollowupTest-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderCompleted-CascadeTesting-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderCompleted-FollowupTest-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderForwarded-OutOfCountry-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderForwarded-SolidTumor-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderHold-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-CancerSolidTumor-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-FetalScenario-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSRareDiseaseTestOrder-InsufficientSample-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSTestOrderAccepted-VariantReinterpretation-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Task-NonWGSTestOrderFormAccepted-UsingStoredSample-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-TestOrderFormAccepted-StorageOfMaterial-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-WGSRareDiseaseTestOrder-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-DirectToLab-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-TrioTestingProband-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderCompleted-DirectToLab-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderCompleted-TrioTestingProband-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderForwarded-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderHold-DirectToLab-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderHold-TrioTestingProband-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderRequested-DirectToLab-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-NonWGSTestOrderFormRequested-UsingStoredSample-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-TrioTestingFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-WGSRareDiseaseTestOrderAccepted-TrioTestingMother-Example}}
                    </td>
                </tr>
            </table>
        </div>
     
<div id="Mappings" class="tabcontent">
    <table class="assets">
        <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
        <tr><td>Task.executionPeriod.start</td><td>PLCM activity - Activity start date and time</td><td>Derived from TQ1-7 in the ORL response message for the activity based on the OML request</td></tr>
        <tr><td>Task.executionPeriod.end</td><td>PLCM activity - Activity end date and time</td><td>Derived from TQ1-8 in the ORL response message for the activity based on the OML request</td></tr>
                    <tr><td>Task.owner</td><td>PLCM activity - ODS code of organisation submitting to PLCM, PLCM activity - ODS code of organisation delivering requested test, PLCM activity - ODS code of the laboratory site delivering requested test</td><td>OBR-32.7 if sourced from principle results interpreter, OBX-32.10, AFF-2.10 associated with performing organization</td></tr>
                    <tr><td>Task.status</td><td>PLCM activity - Sample plating quality control</td><td>Implied through status recorded in ORC-25 indicating plating quality control had passed</td></tr>
                    <tr><td>Task.statusReason</td><td>PLCM activity - Sample plating quality control fail code</td><td>ORC-25</td></tr>
                    <tr><td>Task.output</td><td>Extracted specimen - Location details</td><td>SAC-15</td></tr>
    </table>
</div>
 



<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#basedOn">basedOn</a>
- <a href="#status">status</a>
- <a href="#statusReason">statusReason</a>
- <a href="#businessStatus">businessStatus</a>
- <a href="#code">code</a>
- <a href="#focus">focus</a>
- <a href="#for">for</a>
- <a href="#executionPeriod">executionPeriod</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#lastModified">lastModified</a>
- <a href="#requester">requester</a>
- <a href="#owner">owner</a>
- <a href="#note">note</a>
- <a href="#input">input</a>
- <a href="#output">output</a>

<a name="basedOn"></a>
<h4 class='additional-Guidance-Submenu'> basedOn </h4>
This element will not be used within the Genomic Medicine Service. The ServiceRequest a Task is seeking to fulfill SHALL be referenced through the `focus` element. Specimen resources being acted upon by tasks related to specimen prep/processing SHOULD be referenced through the `Task.input` element. 

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
Initially, automatically populated by the central service upon instantiation. Tasks will be first marked as 'draft' until their prerequisites have been satisfied, after which they will be marked as 'requested' until accepted/claimed by an organization. Upon acceptance, the owning organization is responsible for updating the status up until completion (or if the owning organization is not integrated into the GMS, the organization who has referred the task to the unintegrated org).

If a ServiceRequest is cancelled, any Tasks which have not already moved into in-progress SHALL be moved into the cancelled state, any in-progress Tasks will require lab processes to manage closure of the Task and appropriate reimbursement.

For the full list of expected Task statuses in use by the GMS, please refer to the table below. For the allowed Task status transitions, please see the [FHIR R4 Task state machine model](https://www.hl7.org/fhir/R4/task.html#statemachine). 

|Status|Description|Genomic workflow usage|
|--|--|--|
|Draft|The task is not yet ready to be acted upon.|Initial state for Tasks. Used for tasks which require prerequisite tasks to be completed first.|
|Requested|The task is ready to be acted upon and action is sought.|Status indicating a task can be worked on/claimed, all prerequisites have been satisfied.|
|Received|A potential performer has claimed ownership of the task and is evaluating whether to perform it.|NOT USED within Genomics as Tasks will be polled for rather than being sent out to assigned organizations. Most likely not used unless tasks are automatically assigned and organizations are notified by the central service, e.g. to GLH.|
|Accepted|The potential performer has agreed to execute the task but has not yet started work.|Used when an assigned owner has accepted the task after being assigned.|
|Rejected|The potential performer who claimed ownership of the task has decided not to execute it prior to performing any action.|Used if an organization was assigned to a task but is unable to perform work against it. It is expected if an alternative organization can be assigned, this is done as an owner update rather than marking the task as rejected. If subsequent work does occur, a duplicate task will need to be created as the 'rejected' state is a terminal one.|
|Ready|The task is ready to be performed, but no action has yet been taken. Used in place of requested/received/accepted/rejected when request assignment and acceptance is a given.|NOT USED within Genomics as it is not assumed that Tasks will be automatically accepted when prerequisites are satisfied.|
|Cancelled|The task was not completed.|Used when a task has been created but later identified as unneeded, e.g. due to modifications to test order such as the ServiceRequest being cancelled. Automatically set by the central broker.|
|In Progress|The task has been started but is not yet complete.|When work has commenced.|
|On Hold|The task has been started but work has been paused.|A holding state where work is expected to continue but is being blocked through some external issue. Suppliers will need to state reason why work is on hold through the statusReason field e.g. Awaiting Sample.|
|Failed|The task was attempted but could not be completed due to some error.|Indicates the task cannot continue and is unrcoverable without external intervention. If modifications to the test order allow the task to be resumed, a new task should be created e.g. a new sample is provided to replace a previous sample which has failed quality control. If the Task results in an unrecoverable error, the ServiceRequest may need to be revoked.|
|Completed|The task has been completed.|Marked once all actions against a task are complete, and follow on Tasks can commence.|
|Entered in Error|The task should never have existed and is retained only because of the possibility it may have used.|May be used if user created Tasks are created in error, e.g. duplicate Tasks, or Tasks have been created by the central broker and the ServiceRequest has subsequently been marked as entered-in-error.|

```json
"status": "rejected",
```

<a name="statusReason"></a>
<h4 class='additional-Guidance-Submenu'> statusReason </h4>
Reasons why a Task has been marked as on-hold, cancelled etc. SHOULD use the {{pagelink:Genomic-Task-StatusReason}} CodeSystem. NOTE: The list of appropriate statusReasons is pending finalization.

```json
"statusReason": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/task-status-reason-genomics",
                "code": "further-information-needed",
                "display": "Further Information Needed"
            }
        ]
    },
```

<a name="businessStatus"></a>
<h4 class='additional-Guidance-Submenu'> businessStatus </h4>
Genomic specific business statuses for capturing more granular information as part of processing the task. SHOULD use the {{pagelink:Genomic-Business-Status}} CodeSystem. NOTE: The list of appropriate buinessStatuses is pending finalization. Mapping business statuses to the high level container Tasks and statuses is still ongoing.

```json
"businessStatus": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/business-status-genomics",
                "code": "sample-sent",
                "display": "Sample Sent"
            }
        ]
    },
```

<a name="code"></a>
<h4 class='additional-Guidance-Submenu'> code </h4>
High level coding for the Task, matches the NGTP stages for genomic test processing. Clients SHOULD use the {{pagelink:Genomic-Task-Code}} CodeSystem. NOTE: The list of appropriate codes is pending finalization.

The currently allowed code list and their definition is provided in the table below. The table also provides the cardinality of each Task per ServiceRequest or Sample attached to the request as generated by the central broker on submission of a test request. **Note: the cardinalities listed reflect the number of concurrent active tasks per service request at any one time, there may be cases where additional Tasks need to be spun up manually, e.g. on failure such as when a new sample needs to be processed after a previous sample fails Quality Control, or when further preparation is required**. This cardinality supports the use cases for both requests with multiple participants, e.g. Duo/Trio, and multiple samples per participant e.g. Cancer testing. 

|Task.code display|Definition of work within Task|Cardinality (general case)|Cardinality (Reanalysis/Reinterpretation)|Cardinality (DNA Storage)|
|--|--|
|Process Genomic Test Request|Test code requested is ratified by the lab against provided patient information (checking eligibility)|1..1 (per ServiceRequest)|1..1|1..1|
|Request & Sample Alignment|The lab confirms/validates the data and sample(s) required for given test type are present|1..\* (1 per Specimen referenced from or referencing the ServiceRequest)|1..1 (At least 1 will always be required, e.g. for validation of data in the No Sample scenario)|1..\* (per Sample)|
|Sample Preparation|Sample is prepared, as appropriate for the selected test type, and DNA extracted. May have multiples if further preparation is required|1..\* (1 per Sample)|0..0 (Not required for Reanalysis/Reinterpretation requests where a sample does not need to be prepared)|1..\* (1 per Sample)|
|Sample Processing|DNA sample(s) are sequenced, generating read/sequence data to feed into analysis|1..* (1 per Sample or extracted DNA sample)|0..0 (Not required for Reanalysis/Reinterpretation requests where a sample does not need to be sequenced)|0..0 (Not required for DNA storage where a sample does not need to be sequenced)|
|Genetic/Genomic Data Processing|Sequence data is passed through a bio-pipeline, generates variant priorities lists for analysis|1..\* (1 per Sample or read data)|0..\* (For Reanalysis, should match the number of Samples for the parent request. Not required for Reinterpretation requests)|0..0 (Not required for DNA storage requests)|
|Interpretation|Results analysis is organised and interpreted by a Clincial Scientist|1..\* (1 per Sample or variant priorities list)|1..\* (For Reanalysis/Reinterpretation, should match the number of Samples for the parent request|0..0 (Not required for DNA storage requests)|
|Produce Interim Report|A report is created and deemed interim pending MDT, if necessary|1..\* (1 per Sample. **TBC whether one interim report would be generated per sample/set of genetic data or 1 per request**)|1..\* (For Reanalysis/Reinterpretation, should match the number of Samples for the parent request|0..0 (Not required for DNA storage requests)|
|Genomic MDT|Multi-Diciplinary-Team consults on the interim report|1..1 (max 1 per ServiceRequest, for the purposes of the Alpha an MDT task will always be created, even if not needed)|1..1|0..0 (Not required for DNA storage requests)|
|Produce Final Report|Interim report is deemed final or is updated following MDT|1..1 (per ServiceRequest)|1..1|1..1|
|Distribute Report|Final report is distributed or marked as distributable/available|1..1 (per ServiceRequest or Final Report)|1..1|1..1|

Rendered within a diagram, the Task cardinalities and their inputs are illustrated in the diagram below:

{{render:diagrams-genomicordermanagementtaskmodel}}

```json
"code": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/task-code-genomics",
                "code": "sample-processing",
                "display": "Sample Processing"
            }
        ]
    },
```

<a name="focus"></a>
<h4 class='additional-Guidance-Submenu'> focus </h4>
The ServiceRequest the Task is fulfilling. Autopopulated by the central service.

```json
"focus": {
        "reference": "ServiceRequest/ServiceRequest-SavedTestOrder-Example"
    },
```

<a name="for"></a>
<h4 class='additional-Guidance-Submenu'> for </h4>
A reference to the Patient resource or the identifier, NHS number, for the patient for whom the Task is for. Autopopulated by the central service if the Task is automatically generated. 

If a Task is created by client system or user interaction, `for` SHALL be populated with a reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS.

```json
"for": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="executionPeriod"></a>
<h4 class='additional-Guidance-Submenu'> executionPeriod </h4>
MAY be used to capture start and end DateTimes associated with execution of a Task. It is expected the start time will be populated as a Task is moved to in-progress and the end time will be populated as a Task is marked as completed. Usage of this field will be investigated during the Alpha phase of the Genomic Order Management project as timelines for task execution can also be derived from the AuditEvents recorded as Tasks are updated.

```json
"executionPeriod": {
        "start": "2023-10-31T10:25:05+00:00",
        "end": "2023-11-15T16:45:05+00:00"
    },
```

<a name="authoredOn"></a>
<h4 class='additional-Guidance-Submenu'> authoredOn </h4>
Autopopulated by the central service on creation of the Task.

```json
"authoredOn": "2023-09-18T18:30:00Z"
```

<a name="lastModified"></a>
<h4 class='additional-Guidance-Submenu'> lastModidified </h4>
Time at which a change to the task was made, e.g. status updated. SHALL be updated on change.

```json
"lastModified": "2023-09-18T19:11:00Z"
```

<a name="requester"></a>
<h4 class='additional-Guidance-Submenu'> requester </h4>
The original requester of the ServiceRequest the Task is fulfilling. Autopopulated by the central service.

```json
"requester": {
        "reference": "PractitionerRole/PractitionerRole-GeneSmithENT-Example"
    },
```

<a name="owner"></a>
<h4 class='additional-Guidance-Submenu'> owner </h4>
Autopopulated by the central service if a performer is assigned at Test submission. By default, this will the Home GLH for the submitting organization, unless an alternative is specified. The Home GLH/original performer (managing entity) SHOULD remain the owner for the Process Genomic Test Task, throughout the test order-fulfillment process.

This field can be updated by the organization claiming the task (though this could also be autopopulated if automated per test routing tables are integrated into the central service functionality). Owner SHOULD be populated using organization ODS code references. 

**The responsibility for routing/reassigning ownership of Tasks lies with the current owner following the transfers of responsibility as per the National Genomic Testing Process (NGTP). The different scenarios for how follow-on routing may be achieved is summarised in the points below:**

* In most cases, by default the test will be routed to the home GLH (or other lab/GLH as dictated by the initial routing table). 
* This would mean all Tasks by default would have this organization, e.g. home GLH, as the initial owner, it would then be the responsibility of the GLH to reassign tasks to other organizations, where they 'send away' or commission work. 
* Once that work is complete, the send-away organization can choose to reassign the current Task (where another organization needs to conduct work against the same Task before it can be marked as complete)/or assign the follow-on Task (where the current task can be marked as complete) to the next organization, if this is known. 
* If the next organization to send work to is unknown, responsibility should lie with the original/previous owner e.g. Home GLH to reassign the task to the next organization that needs to complete work. This should be captured by having the current owner reassign the task back to the GLH (or organization which assigned the task to them) if further work needs to occur within the current task; or the next task in the NGTP moves from the draft state into the requested state (indicating all its prerequisites have been satisfied). The owner of that task, e.g home GLH, then either starts work or assigns this to the relevant organization. 
* In further phases, a routing advice service may be provided by NHS England to aid organizations in identifying which organization should be assigned, after completing their work.

Tasks assigned to a particular organization SHOULD be searched for using the `owner` search parameter with the `:identifier` modifier i.e. `[base]/Task?owner:identifier=8J834` or `[base]/Task?owner:identifier=https://fhir.nhs.uk/Id/ods-organization-code|8J834`

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "69010"
        },
        "display": "Pathology Lab - ADDENBROOKE'S HOSPITAL LABORATORY"
    },
```

<a name="note"></a>
<h4 class='additional-Guidance-Submenu'> note </h4>
Used for messaging between owner and other orgnizations e.g. during handover of task or requesting information from requesting clinician.

```json
"note":  [
        {
            "text": "Sample has not been received within 4 week window. Task will be closed unless further communication is received"
        }
    ]
```

<a name="input"></a>
<h4 class='additional-Guidance-Submenu'> input </h4>
Used to attach inputs to a Task, if relevant. e.g. references to Specimen's which a Sample Processing task is acting on. No CodeSystem exists for this field as of publication but this will be investigated as future work.

Specimen references SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing. This is to clearly disambiguate which specimen a task is acting on, where multiple specimens are necessary for processing the test request. 

The table below provides possible inputs that could be provided for certain Tasks as part of fulfillment of a test order. A finalised list is pending business analysis work to identify the operational data generated as fulfilment against a test order progresses and the need for this data to pass between organizations.

|Task.code display|Possible Task.input|
|--|--|
|Process Genomic Test Request|N/A, all information required should be part of or refernced from the ServiceRequest|
|Request & Sample Alignment|Specimen resource to be aligned and potentially Consent resources where these are captured post submission of a test request|
|Sample Preparation|Specimen resource to be prepared as part of this Task|
|Sample Processing|DNA Specimen resource to be sequenced as part of this Task as well as Consignment, Rack and Well identifiers to allow for specimen tracking|
|Genetic/Genomic Data Processing|Sequence data generated from the previous Task, potentially referenced using DocumentReference resources, these SHOULD reference the Specimen from which the data originated|
|Interpretation|Variant Priorities lists generated from the previous Task, **the representation of these lists is still under investigation**|
|Produce Interim Report|Guidance/Recommendations generated though data interpretation, **the representation of these items is still under investigation**|
|Genomic MDT|Interim reports, references to Diagnostic report resources containing either structured Genomic reports or binary representations of the reports|
|Produce Final Report|Interim reports and potentially recommendations from the MDT, **whether these are represented within the DiagnosticReport itself or contained as other resource types is still under investigation**|
|Distribute Report|The final report to be distributed|

```json
"input":  [
    {
            "type": {
                "coding":  [
                    {
                        "system": "https://fhir.nhs.uk/CodeSystem/AdditionalInfoTypeGenomics",
                        "code": "Specimen",
                        "display": "Specimen"
                    }
                ]
            },
            "valueReference": {
                "reference": "Specimen/Specimen-CancerSolidTumor-Example"
            }
        }
    ]
```

<a name="output"></a>
<h4 class='additional-Guidance-Submenu'> output </h4>
Used to attach outputs from a Task, if relevant. e.g. VUS files during processing or a DiagnosticReport upon completion of reporting stage. No CodeSystem exists for this field as of publication but this will be investigated as future work.

Sample tracking information SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing, on either the output or input elements. This information MAY include consignment number, destination, date sent etc. Further modelling of the types/format expected are pending clinical scenarios.

The table below provides possible outputs that could be generated by certain Tasks as part of fulfillment of a test order. A finalised list is pending business analysis work to identify the operational data generated as fulfilment against a test order progresses and the need for this data to pass between organizations.

|Task.code display|Possible Task.output|
|--|--|
|Process Genomic Test Request|N/A, may result in updates to the ServiceRequest if codes or supporting information needs to change|
|Request & Sample Alignment|Aligned Specimen resource for request (except for Reanalysis/Reinterpretation)|
|Sample Preparation|DNA Specimen resource as well as Consignment, Rack and Well identifiers to allow for specimen tracking|
|Sample Processing|Sequence/Read data|
|Genetic/Genomic Data Processing|Variant information|
|Interpretation|Potentially structured guidance/recommendations|
|Produce Interim Report|Interim reports|
|Genomic MDT|Potentially ammended Interim/combined report or recommendations from MDT|
|Produce Final Report|Final Report|
|Distribute Report|N/A, final report will be included as input to Task|

```json
"output":  [
       {
          "type": {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/CodeSystem/AdditionalInfoTypeGenomics",
                "code": "DiagnosticReport",
                "display": "DiagnosticReport"
              }
            ]
          },
          "valueReference": {
            "reference": "DiagnosticReport/DiagnosticReport-PhoebeSmithGeneticReport-Example"
          }
        }
    ]
```
---