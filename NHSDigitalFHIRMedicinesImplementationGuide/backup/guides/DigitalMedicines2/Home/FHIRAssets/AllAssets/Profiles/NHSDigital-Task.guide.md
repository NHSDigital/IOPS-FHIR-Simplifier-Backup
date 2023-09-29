### NHSDigital-Task

| Profile url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task) | [Workflow]() | trial-use |

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
          {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task, hybrid}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task, diff}}
        </div>
        <div id="Constraints"  class="tab-pane">
<br/>
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task'
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

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> The guidance below is EPS specfic supplementary information. This will be incorporated into the main NHSDigital-Task profile in a future version. </div>

- <a href="#types">Task Types</a>
- <a href="#mustSupport">Must Support, Optional and Should Not Support</a>
- <a href="#courseOfTherapyType">courseOfTherapyType</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#statusReason">statusReason</a>
- <a href="#intent">intent</a>
- <a href="#groupIdentifier">groupIdentifier</a>
- <a href="#code">code</a>
- <a href="#focus">focus</a>
- <a href="#for">for</a>
- <a href="#requester">requester</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#owner">owner</a>
- <a href="#reasonCode">reasonCode</a>
- <a href="#input">input</a>


<br>

A task resource describes an activity that can be performed and tracks the state of completion of that activity. It is a representation that an activity should be or has been initiated, and eventually, represents the successful or unsuccessful completion of that activity.

Note that there are a variety of processes associated with making and processing orders. Some orders may be handled immediately by automated systems but most require real world actions by one or more humans. Some orders can only be processed when other real world actions happen, such as a patient presenting themselves so that the action to be performed can actually be performed. Often these real world dependencies are only implicit in the order details.

**A Task resource often exists in parallel with clinical resources.** 

For example, a Task could request fulfillment of a ServiceRequest ordering a Procedure that would result in a Procedure, Observation, DiagnosticReport, ImagingStudy or similar resource. Another example would be a Task that requests fulfillment of a CommunicationRequest to be performed between various actors.

<br>

<a name="mustSupport"></a>
### Must Support, Optional and Not Supported

Elements marked with a <span style="background-color:red;color:white;">S</span> **MUST** be supported by both producing and receiving systems. They should be populated if the data exists or the profile has made them mandatory. 

The following elements **SHOULD NOT** are not expected to be supported by consuming or receiving systems.

- `doNotPerform`
- `detectedIssue`

Elements that are neither marked as `Must Support` or listed as unsupported are optional. 

<br>

<a name="courseOfTherapyType"></a>
### extension courseOfTherapyType (Prescription Therapy Type) <a href="#courseOfTherapyType" title="link to here" class="self-link"><i class="bi-link"></i></a> 

See prescribingmodels ({{pagelink:index-duplicate-47}}) for more details.

A single Code from {{pagelink: DM-MedicationRequest-Course-of-Therapy-duplicate-2}} values.

```json
"extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-Prescription",
            "extension":  [
                {
                    "url": "courseOfTherapyType",
                    "valueCoding": {
                        "system": "http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy",
                        "code": "acute",
                        "display": "Acute"
                    }
                }
            ]
        }
    ],
```

<br>

<a name="identifier"></a>
### identifier

A single identifier **MUST** be present and the value must be a UUID.

```json
"identifier":  [
        {
            "system": "https://tools.ietf.org/html/rfc4122",
            "value": "5AC84C11-DB8B-44DA-8FCF-8980B3D13596"
        }
    ],
```

<br>

<a name="status"></a>
### status

Only `in-progress` is currently supported for reasonCode = 373784005 (Dispensing medication) and focus is a `dispense-notification`. 

`rejected` / `cancelled` / `failed` are supported for reasonCode = 33633005 (Prescription of drug) and focus is a `prescription-order`. See also {{pagelink:fulfilmentstates-duplicate-2}}


<a name="statusReason"></a>
### statusReason


A code from {{pagelink:DM-Task-Reason-Code-duplicate-2}} 

| reasonCode | focus | status | CodeSystem |
|--
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

<a name="intent"></a>
### intent 

Is not processed by EPS and is included for FHIR compliance reasons. The value should always be `order`.

<a name="groupIdentifier"></a>
### groupIdentifier

An identifier to the original `prescription-order` **MUST** be present. Only the short form identifier needs to be supplied.

```json
"groupIdentifier": {
        "system": "https://fhir.nhs.uk/Id/prescription-order-number",
        "value": "88AF6C-C81007-00001C"
    },
```
<a name="code"></a>
### code

The code indicates the action to perform on the `focus` resource. A code from {{link:http://hl7.org/fhir/ValueSet/task-code}}

```json
 "code": {
        "coding":  [
            {
                "system": "http://hl7.org/fhir/CodeSystem/task-code",
                "code": "fulfill",
                "display": "Fulfill the focal request"
            }
        ]
    }
```

<a name="focus"></a>
### focus 

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

<a name="for"></a>
### for

A reference to the patient the Task is for. This will always be an identifier reference using the Patients NHSNumber.

```json
"for": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9446368138"
        }
    },
```

<a name="requester"></a>
### requester

Who is created the Request or the Event. 

```json
"requester": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "C81007"
        },
        "display": "VERNON STREET MEDICAL CTR"
    },
```

<a name="authoredOn"></a>
### authoredOn

Date and time the task was created.

```json
"authoredOn": "2020-12-21T17:03:20-00:00",
```

<a name="owner"></a>
### owner

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

<a name="reasonCode"></a>
### reasonCode

This is a SNOMED CT :

| SNOMED CT | Display |  | 
|--
| 33633005 | Prescription of drug |
| 373784005 | Dispensing medication |

<a name="input"></a>
### input

Information used to perform task. 

For `request` Tasks this will contain references to the key resources that are used to process the Task. E.g. for prescription-order this will be the MedicationRequest resources.

For `event` Tasks this may also be used to hold the key resources, however if the event has a corresponding `request` Task i.e. this is a sub-Task, the `basedOn` element can be used instead.

```json
"input":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "16076005",
                        "display": "Prescription"
                    }
                ]
            },
            "valueReference": {
                "type": "MedicationRequest",
                "reference": "https://prescriptions.spineservices.nhs.uk/FHIR/R4/MedicationRequest/30b7e9cf-6f42-40a8-84c1-e61ef638eee2",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                    "value": "30b7e9cf-6f42-40a8-84c1-e61ef638eee2"
                },
                "display" : "Perindopril erbumine 2mg tablets"
            }
        },
```

 
