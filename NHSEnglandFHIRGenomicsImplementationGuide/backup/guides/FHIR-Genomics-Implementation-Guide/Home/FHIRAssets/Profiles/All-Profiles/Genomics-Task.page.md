## {{page-title}}

The core workflow resource for managing processing of a ServiceRequest from order through to delivery of a DiagnosticReport and completion. Task tracking is a core requirement of the central Genomic Medicine Service.

Each ServiceRequest submitted will instantiate a series of High Level Tasks, which MAY be assigned to different organizations for managing the test request e.g. Sample Processing, Interpretation, Reporting etc. The full list of possible Task types/codes, their associated business statuses, and status reasons is pending internal review.

Tasks will be automatically created by the central service but updates to statuses and attachment of input/output resources is the responsibility of the assigned organizations.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Task](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Task&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

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
            {{tree:http://hl7.org/fhir/StructureDefinition/Task, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Task}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/Task, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/Task, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
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
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='http://hl7.org/fhir/StructureDefinition/Task'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
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
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='http://hl7.org/fhir/StructureDefinition/Task' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

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
#### basedOn
This element will not be used within the Genomic Medicine Service. The ServiceRequest a Task is seeking to fulfill SHALL be referenced through the `focus` element. Specimen resources being acted upon by tasks related to specimen prep/processing SHOULD be referenced through the `Task.input` element. 

<a name="status"></a>
#### status
Initially, automatically populated by the central service upon instantiation. Tasks will be first marked as 'draft' until their prerequisites have been satisfied, after which they will be marked as 'requested' until accepted/claimed by an organization. Upon acceptance, the owning organization is responsible for updating the status up until completion (or if the owning organization is not integrated into the GMS, the organization who has referred the task to the unintegrated org).

For the full list of expected Task statuses in use by the GMS, please refer to the table below. For the allowed Task status transitions, please see the [FHIR R4 Task state machine model](https://www.hl7.org/fhir/R4/task.html#statemachine). 

|Status|Description|Genomic workflow usage|
|--|--|--|
|Draft|The task is not yet ready to be acted upon.|Initial state for Tasks. Used for tasks which require prerequisite tasks to be completed first.|
|Requested|The task is ready to be acted upon and action is sought.|Status indicating a task can be worked on/claimed, all prerequisites have been satisfied.|
|Received|A potential performer has claimed ownership of the task and is evaluating whether to perform it.|NOT USED within Genomics as Tasks will be polled for rather than being sent out to assigned organizations. Most likely not used unless tasks are automatically assigned and organizations are notified by the central service, e.g. to GLH.|
|Accepted|The potential performer has agreed to execute the task but has not yet started work.|Used when an assigned owner has accepted the task after being assigned.|
|Rejected|The potential performer who claimed ownership of the task has decided not to execute it prior to performing any action.|Used if an organization was assigned to a task but is unable to perform work against it. It is expected if an alternative organization can be assigned, this is done as an owner update rather than marking the task as rejected. If subsequent work does occur, a duplicate task will need to be created as the 'rejected' state is a terminal one.|
|Ready|The task is ready to be performed, but no action has yet been taken. Used in place of requested/received/accepted/rejected when request assignment and acceptance is a given.|NOT USED within Genomics as it is not assumed that Tasks will be automatically accepted when prerequisites are satisfied.|
|Cancelled|The task was not completed.|Used when a task has been created but later identified as unneeded, e.g. due to modifications to test order such as the ServiceRequest being cancelled.|
|In Progress|The task has been started but is not yet complete.|When work has commenced.|
|On Hold|The task has been started but work has been paused.|A holding state where work is expected to continue but is being blocked through some external issue. Suppliers will need to state reason why work is on hold through the statusReason field e.g. Awaiting Sample.|
|Failed|The task was attempted but could not be completed due to some error.|Indicates the task cannot continue and is unrcoverable without external intervention. If modifications to the test order allow the task to be resumed, a new task should be created e.g. a new sample is provided to replace a previous sample which has failed quality control.|
|Completed|The task has been completed.|Marked once all actions against a task are complete, and follow on Tasks can commence.|
|Entered in Error|The task should never have existed and is retained only because of the possibility it may have used.|May be used if user created Tasks are created in error, e.g. duplicate Tasks|

```json
"status": "rejected",
```

<a name="statusReason"></a>
#### statusReason
Reasons why a Task has been marked as on-hold, cancelled etc. SHOULD use the {{pagelink:Genomic-Task-StatusReason}} CodeSystem. NOTE: The list of appropriate statusReasons is pending finalization.
```json
"statusReason": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/task-status-reason-genomics",
                "code": "Inappropriate",
                "display": "Inappropriate for patient"
            }
        ]
    },
```

<a name="businessStatus"></a>
#### businessStatus
Genomic specific business statuses for capturing more granular information as part of processing the task. SHOULD use the {{pagelink:Genomic-Business-Status}} CodeSystem. NOTE: The list of appropriate buinessStatuses is pending finalization. Mapping business statuses to the high level container Tasks and statuses is still ongoing.
```json
"businessStatus": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/business-status-genomics",
                "code": "InvalidRequest",
                "display": "Invalid Request"
            }
        ]
    },
```

<a name="code"></a>
#### code
High level coding for the Task, matches the NGTP stages for genomic test processing. SHOULD use the {{pagelink:Genomic-Task-Code}} CodeSystem. NOTE: The list of appropriate codes is pending finalization.
```json
"code": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/task-code-genomics",
                "code": "SampleProcessing",
                "display": "Sample Processing"
            }
        ]
    },
```

<a name="focus"></a>
#### focus
The ServiceRequest the Task is fulfilling. Autopopulated by the central service.
```json
"focus": {
        "reference": "ServiceRequest/ServiceRequest-SavedTestOrder-Example"
    },
```

<a name="for"></a>
#### for
A reference to the Patient resource or the identifier, NHS number, for the patient for whom the Task is for. Autopopulated by the central service.
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
#### executionPeriod
MAY be used to capture start and end DateTimes associated with execution of a Task. It is expected the start time will be populated as a Task is moved to in-progress and the end time will be populated as a Task is marked as completed. Usage of this field will be investigated during the Alpha phase of the Genomic Order Management project as timelines for task execution can also be derived from the AuditEvents recorded as Tasks are updated.
```json
"executionPeriod": {
        "start": "2023-10-31T10:25:05+00:00",
        "end": "2023-11-15T16:45:05+00:00"
    },
```

<a name="authoredOn"></a>
#### authoredOn
Autopopulated by the central service on creation of the Task.
```json
"authoredOn": "2023-09-18T18:30:00Z"
```

<a name="lastModified"></a>
#### lastModified
Time at which a change to the task was made, e.g. status updated. SHALL be updated on change.
```json
"lastModified": "2023-09-18T19:11:00Z"
```

<a name="requester"></a>
#### requester
The original requester of the ServiceRequest the Task is fulfilling. Autopopulated by the central service.
```json
"requester": {
        "reference": "PractitionerRole/PractitionerRole-GeneSmithENT-Example"
    },
```

<a name="owner"></a>
#### owner
Autopopulated by the central service if a performer is assigned at Test submission. By default, this will the Home GLH for the submitting organization, unless an alternative is specified. The Home GLH/original performer (managing entity) SHOULD remain the owner for the Process Genomic Test Task, throughout the test order-fulfillment process.

This field can be updated by the organization claiming the task (though this could also be autopopulated if automated per test routing tables are integrated into the central service functionality). Owner SHOULD be populated using organization ODS code references.

Tasks assigned to a particular organization SHOULD then be searched for using the `owner` search parameter with the `:identifier` modifier i.e. `[base]/Task?owner:identifier=8J834` or `[base]/Task?owner:identifier=https://fhir.nhs.uk/Id/ods-organization-code|8J834`
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
#### note
Used for messaging between owner and other orgnizations e.g. during handover of task or requesting information from requesting clinician
```json
"note":  [
        {
            "text": "Sample has not been received within 4 week window. Task will be closed unless further communication is received"
        }
    ]
```

<a name="input"></a>
#### input
Used to attach inputs to a Task, if relevant. e.g. references to Specimen's which a Sample Processing task is acting on. No CodeSystem exists for this field as of publication but this will be investigated as future work.

Specimen references SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing. This is to clearly disambiguate which specimen a task is acting on, where multiple specimens are necessary for processing the test request. 
```json
"input":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "123038009",
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
#### output
Used to attach outputs from a Task, if relevant. e.g. VUS files during processing or a DiagnosticReport upon completion of reporting stage. No CodeSystem exists for this field as of publication but this will be investigated as future work.

Sample tracking information SHOULD be added to Tasks acting on Specimen resources, e.g. Tasks marked SamplePreparation or SampleProcessing, on either the output or input elements. This information MAY include consignment number, destination, date sent etc. Further modelling of the types/format expected are pending clinical scenarios.
```json
"output":  [
        {
            "type": {
                "text": "DiagnosticReport"
            },
            "valueReference": {
                "reference": "DiagnosticReport/DiagnosticReport-GenomicTesting-Example"
            }
        }
    ]
```