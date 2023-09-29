## {{page-title}}

### NHSDigital-Task

| Profile url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-DM-Task](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-DM-Task) |

<br>


<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
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
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
          <br><br>
          {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-DM-Task, hybrid}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-DM-Task, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-DM-Task'
for differential.element.constraint
select key, human, severity, expression
```

| key | human | severity | expression |
|--
| nhds-10 | groupIdentifier and reasonCode are mandatory for EPS interactions | error |	code.coding.where(system = 'http://hl7.org/fhir/CodeSystem/task-code').exists().not() or (code.coding.where(system = 'http://hl7.org/fhir/CodeSystem/task-code').exists() and groupIdentifier.exists() and reasonCode.exists()) |

</div>
<div id="Examples"  class="tab-pane">
<br/>

- {{pagelink:TaskCancelDispenseNotification-duplicate-2}}
- {{pagelink:TaskReturnPrescriptionOrder-duplicate-2}} 
- {{pagelink:TaskEPSPrescriptionTracker1-duplicate-2}}
- {{pagelink:TaskEPSPrescriptionTracker2-duplicate-2}}
- {{pagelink: TaskPrescriptionCancel-duplicate-2}} from a prescriber (or pharmacy?)
</div>
</div>

---



| | |
|----|----|
|Element Id|Task|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|

<br/>

 #### Definition

 FHIR Task usage and scope is defined as 

> A task resource describes an activity that can be performed and tracks the state of completion of that activity. It is a representation that an activity should be or has been initiated, and eventually, represents the successful or unsuccessful completion of that activity. Note that there are a variety of processes associated with making and processing orders. Some orders may be handled immediately by automated systems but most require real world actions by one or more humans. Some orders can only be processed when other real world actions happen, such as a patient presenting themselves so that the action to be performed can actually be performed. Often these real world dependencies are only implicit in the order details.

 #### Comment

Within NHS Digital this resource will often be associated with workflow management. 

Similar concepts exist outside of NHS Digital for example a GP system has the concept of Task and this includes:

- telephone patient
- form to complete
- prescription
- referral
- book appointment
- medication review

These are complemented with more detailed Task management around:

- pathology
- medicine management and also includes EPS
  - Rejected Prescriptions
  - Cancelled Prescriptions
  - Subsequent cancellation rejections 
- referrals

NHS App also includes the ability to order **repeat prescriptions** which relates to the GP systems **prescriptions**.

 #### Constraints 

- **inv-1** (*ERROR*) Last modified date must be greater than or equal to authored-on date.


- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#statusReason">statusReason</a>
- <a href="#statusReason.coding:withdrawReason">statusReason.coding:withdrawReason</a>
- <a href="#statusReason.coding:withdrawReason.system">statusReason.coding:withdrawReason.system</a>
- <a href="#statusReason.coding:dispenseReturn">statusReason.coding:dispenseReturn</a>
- <a href="#statusReason.coding:dispenseReturn.system">statusReason.coding:dispenseReturn.system</a>
- <a href="#statusReason.coding:medicationRequestStatusReason">statusReason.coding:medicationRequestStatusReason</a>
- <a href="#statusReason.coding:medicationRequestStatusReason.system">statusReason.coding:medicationRequestStatusReason.system</a>
- <a href="#intent">intent</a>
- <a href="#code">code</a>
- <a href="#focus">focus</a>
- <a href="#for">for</a>
- <a href="#requester">requester</a>
- <a href="#owner">owner</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#reasonCode.coding:SNOMED">reasonCode.coding:SNOMED</a>
- <a href="#reasonCode.coding:SNOMED.system">reasonCode.coding:SNOMED.system</a>
- <a href="#input">input</a>
- <a href="#output">output</a>

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Task.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 The business identifier for this task.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|Task.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[TaskStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/ValueSet/task-status&#124;4.0.1) (Required) <br/>The current status of the task. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 These workflow tasks have `status` which indicates the Task status. 

The following diagram reflects the "typical" state machine for Task. Note that not all states will be supported by all workflows and that some workflows may support additional transitions, including transitions from terminal states (e.g. back to "in-progress" from "failed" or "completed").

<img src="https://www.hl7.org/fhir/task-state-machine.svg"></img>

For example: 

A patient requesting a repeat prescription would ask for task with code `fulfil` used with `103742009 | Renewal of prescription` and a status of `requested`.  
Once reviewed (by a clinician), the task status would be changed to `accepted`. When the task is then picked up (`in-progress`) and the related *MedicationRequest* is sent, the status would change to `completed`.

 #### Requirements

 These states enable coordination of task status with off-the-shelf workflow solutions that support automation of tasks.

<a name="statusReason"></a>
 ## statusReason

| | |
|----|----|
|Element Id|Task.statusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 **For EPS only**

| reasonCode | focus | status | CodeSystem |
|--|--|--|--|
| 373784005 - Dispensing medication | `dispense-notification` | `cancelled` | {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason}} |
| 33633005 - Prescription of drug | `prescription-order` | `rejected` / `cancelled` / `failed` |  {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-return-status-reason}} |

```json
"statusReason": [{
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason",
                "code": "DA",
                "display": "Dosage Amendments"
            }
        ]
    }]
```

 #### Comment

 This applies to the current status.  Look at the history of the task to see reasons for past statuses.

<a name="statusReason.coding:withdrawReason"></a>
 ## statusReason.coding:withdrawReason

| | |
|----|----|
|Element Id|Task.statusReason.coding:withdrawReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|withdrawReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="statusReason.coding:withdrawReason.system"></a>
 ## statusReason.coding:withdrawReason.system

| | |
|----|----|
|Element Id|Task.statusReason.coding:withdrawReason.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="statusReason.coding:dispenseReturn"></a>
 ## statusReason.coding:dispenseReturn

| | |
|----|----|
|Element Id|Task.statusReason.coding:dispenseReturn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|dispenseReturn|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="statusReason.coding:dispenseReturn.system"></a>
 ## statusReason.coding:dispenseReturn.system

| | |
|----|----|
|Element Id|Task.statusReason.coding:dispenseReturn.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-return-status-reason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="statusReason.coding:medicationRequestStatusReason"></a>
 ## statusReason.coding:medicationRequestStatusReason

| | |
|----|----|
|Element Id|Task.statusReason.coding:medicationRequestStatusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|medicationRequestStatusReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="statusReason.coding:medicationRequestStatusReason.system"></a>
 ## statusReason.coding:medicationRequestStatusReason.system

| | |
|----|----|
|Element Id|Task.statusReason.coding:medicationRequestStatusReason.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/medicationrequest-status-reason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="intent"></a>
 ## intent

| | |
|----|----|
|Element Id|Task.intent|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[TaskIntent](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/ValueSet/task-intent&#124;4.0.1) (Required) <br/>Distinguishes whether the task is a proposal, plan or full order. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 Indicates the "level" of actionability associated with the Task, i.e. i+R[9]Cs this a proposed task, a planned task, an actionable task, etc.

 #### Comment

 Is not processed by EPS and is included for FHIR compliance reasons. The value should always be `order`.

<a name="code"></a>
 ## code

| | |
|----|----|
|Element Id|Task.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[EnglandTaskCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/ValueSet/England-task-code) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The reasonCode's are complemented with [task-code](https://www.hl7.org/fhir/valueset-task-code.html) which indicates the type of action to be performed. 

For example:

The code `fulfil` used with `182836005 | Review of medication` means a task to review medication.
The code `approve` used with `103742009 | Renewal of prescription` is a task for a clinician to approve the issue of a repeat medication.

```json
 "code": {
        "coding":  [
            {
                "system": "http://hl7.org/fhir/CodeSystem/task-code",
                "code": "fulfill",
                "display": "Fulfill the focal request"
            }
        ]
 ```

 #### Comment

 The title (eg "My Tasks", "Outstanding Tasks for Patient X") should go into the code.

<a name="focus"></a>
 ## focus

| | |
|----|----|
|Element Id|Task.focus|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalBundleFHIRMessage](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Bundle-FHIRMessage))|

<br/>

 #### Definition

 ** EPS Only**

This will be the `Bundle.identifier` of the message this Task is acting on. 
For Tasks with a reasonCode of `373784005 - Dispensing medication`  this will be a `dispense-notification` message. 
For Tasks with a reasonCode of `33633005 - Prescription of drug` this will be the `prescription-order` message from the Task/$release operation.

```json
"focus": {
        "type": "Bundle",
        "identifier": {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "334a3195-1f6c-497a-8efe-d272ca9c4e38"
        }
    },
```

 #### Requirements

 Used to identify the thing to be done.

 #### Comment

 Tasks are often generated as a consequence of other workflows or relate to FHIR Workflow resources. For example a repeat medication request will be related to a previous `MedicationRequest` or a medication reconciliation may relate to a hospital admissions `Encounter/EpisodeOfCare`. This is carried in the `focus` element.

`focus` can be omitted. For example if an ED generated a Medication Review as a result of COPD Emergency encounter they may chose to include a reference to the Encounter but they may decide instead to use a more specific reasonCode such as `394720003 | Asthma medication review`.

<a name="for"></a>
 ## for

| | |
|----|----|
|Element Id|Task.for|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Resource](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Resource))|

<br/>

 #### Definition

 A reference to the patient the Task is for. This will always be an identifier reference using the Patients NHSNumber.

```json
"for": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9446368138"
        }
    },
```

 #### Requirements

 Used to track tasks outstanding for a beneficiary.  Do not use to track the task owner or creator (see owner and creator respectively).  This can also affect access control.

 #### Constraints 

- **patient-reference** (*ERROR*) An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="requester"></a>
 ## requester

| | |
|----|----|
|Element Id|Task.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRoleMinimalPlusTelecom](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-MinimalPlusTelecom))|

<br/>

 #### Definition

 Who is created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.

```json
 "requester": {
        "reference": "#requester"
    },
```

This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry,

 #### Requirements

 Identifies who created this task.  May be used by access control mechanisms (e.g., to ensure that only the creator can cancel a task).

 #### Constraints 

- **usercode-reference** (*WARNING*) An identifier reference plus a display name or resource reference must be provided
- **usercode-nmc** (*ERROR*) NMC must be of the format NNANNNNA
- **usercode-gmp** (*ERROR*) GMP must be of the format GNNNNNNN and not be a spurious code (starts with G6 or G7)
- **usercode-gmc** (*ERROR*) GMC must be of the format CNNNNNNN
- **usercode-gphc** (*ERROR*) GPHC must be of the format NNNNNNN
- **usercode-hcpc** (*ERROR*) HCPC must be of the format AANNNNNN
- **usercode-din** (*ERROR*) DIN format must be NNNNNN

<a name="owner"></a>
 ## owner

| | |
|----|----|
|Element Id|Task.owner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 Who is responsible for actioning the request Task (e.g. for a prescription-order this will be the pharmacy). 

```json
"owner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FB444"
        },
        "display": "Freds Pharmacy"
    },
```

 #### Requirements

 Identifies who is expected to perform this task.

 #### Comment

 Tasks may be created with an owner not yet identified.

<a name="reasonCode"></a>
 ## reasonCode

| | |
|----|----|
|Element Id|Task.reasonCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 In FHIR Task these types of workflow would be represented via **reasonCode** and/or **reasonReference**

For medication this is probably SNOMED CT based using codes under the SNOMED CT 182832007 Medication management and includes codes such as:

| SNOMED CT | Display |
|--|--|
| 182836005 | Review of medication | 
| 430193006 | Medication Reconciliation |
| 103742009 | Renewal of prescription |
| 33633005 | Prescription of drug |
| 373784005 | Dispensing medication |

<br/>

For referral management

| SNOMED CT | Display |
|--|--|
| <a href="https://ontoserver.csiro.au/shrimp/?concept=3457005&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">3457005</a> | Patient Referral |
| <a href="https://ontoserver.csiro.au/shrimp/?concept=185499000&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">185499000</a>| Expedite appointment |

 #### Comment

 This should only be included if there is no focus or if it differs from the reason indicated on the focus.

<a name="reasonCode.coding:SNOMED"></a>
 ## reasonCode.coding:SNOMED

| | |
|----|----|
|Element Id|Task.reasonCode.coding:SNOMED|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|SNOMED|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="reasonCode.coding:SNOMED.system"></a>
 ## reasonCode.coding:SNOMED.system

| | |
|----|----|
|Element Id|Task.reasonCode.coding:SNOMED.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="input"></a>
 ## input

| | |
|----|----|
|Element Id|Task.input|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Additional information that may be needed in the execution of the task.

 #### Requirements

 Resources and data used to perform the task.  This data is used in the business logic of task execution, and is stored separately because it varies between workflows.

<a name="output"></a>
 ## output

| | |
|----|----|
|Element Id|Task.output|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Outputs produced by the Task.

 #### Requirements

 Resources and data produced during the execution the task.  This data is generated by the business logic of task execution, and is stored separately because it varies between workflows.