## {{page-title}}

The core workflow resource for managing processing of a ServiceRequest from order through to delivery of a DiagnosticReport and completion. Task tracking is a core requirement of the central Genomic Medicine Service.

Each ServiceRequest submitted will instantiate a series of High Level Tasks, which MAY be assigned to different organizations for managing the test request e.g. Sample Processing, Interpretation, Reporting etc. The full list of possible Task types/codes, their associated business statuses, and status reasons is pending internal review.

Tasks will be automatically created by the central service but updates to statuses and attachment of input/output resources is the responsibility of the assigned organizations.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Task}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Task-DYPDSequencingTask}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-Filler}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-FillerUpdate}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Task-SendAway}}
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
                        {{pagelink:Task-NonWGSRareDiseaseTestOrderHold-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-Example}}
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
                        {{pagelink:Task-WGSRareDiseaseTestOrderForwarded-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task'
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
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task' 
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
- <a href="#authoredOn">authoredOn</a>
- <a href="#lastModified">lastModified</a>
- <a href="#requester">requester</a>
- <a href="#owner">owner</a>
- <a href="#note">note</a>
- <a href="#output">output</a>

<a name="basedOn"></a>
#### basedOn
This element will not be used within the Genomic Medicine Service. The ServiceRequest a Task is seeking to fulfill SHALL be referenced through the `focus` element. Specimen resources being acted upon by tasks related to specimen prep/processing SHOULD be referenced through the `Task.input` element. 

<a name="status"></a>
#### status
Initially, automatically populated by the central service upon instantiation. Tasks will be first marked as 'requested' until accepted/claimed by an organization, or marked as 'draft' if their prerequisities have not been satisfied. Upon acceptance, the owning organization is responsible for updating the status up until completion (or if the owning organization is not integration into the GMS, the organization who has referred the task to the unintegrated org).

For the full list of expected Task statuses in use by the GMS, please refer to the table below: 

|Status|Description|Genomic workflow usage|
|--|--|--|
|Draft|The task is not yet ready to be acted upon.|May be used for tasks which require prerequisite tasks to be completed first|
|Requested|The task is ready to be acted upon and action is sought.|Initial state of tasks when created|
|Received|A potential performer has claimed ownership of the task and is evaluating whether to perform it.|Most likely not used unless tasks are automatically assigned by the central service, e.g. to GLH|
|Accepted|The potential performer has agreed to execute the task but has not yet started work.|When assigned|
|Rejected|The potential performer who claimed ownership of the task has decided not to execute it prior to performing any action.|Most likely used if an organization was assigned to a task but is unable to perform work against it|
|Ready|The task is ready to be performed, but no action has yet been taken. Used in place of requested/received/accepted/rejected when request assignment and acceptance is a given.|Tasks ready to be picked up when prerequisites are satisfied|
|Cancelled|The task was not completed.|Most likely used when a task has been created but later identified as unneeded, e.g. due to modifications to test order|
|In Progress|The task has been started but is not yet complete.|When work has commenced|
|On Hold|The task has been started but work has been paused.|May need to state reason why work is on hold e.g. awaiting sample|
|Failed|The task was attempted but could not be completed due to some error.|Indicates the task cannot continue, if modifications to the test order allow the task to be resumed, a new task should be created|
|Completed|The task has been completed.|Once complete|
|Entered in Error|The task should never have existed and is retained only because of the possibility it may have used.|Unused|

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
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
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
Autopopulated by the central service if a performer is assigned at Test submission. Otherwise updated by the organization claiming the task (though this could also be autopopulated if automated per test routing tables are integrated into the central service functionality). Owner SHOULD be populated using organization ODS code references.

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