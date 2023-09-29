### NHSDigital-Task



| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task](https://simplifier.net/guide/DigitalMedicines/NHSDigital-Task) | 

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

- {{pagelink:TaskCancelDispenseNotification}}
- {{pagelink:TaskReturnPrescriptionOrder}} 
- {{pagelink:TaskEPSPrescriptionTracker1}}
- {{pagelink:TaskEPSPrescriptionTracker2}}
- {{pagelink: TaskPrescriptionCancel}} from a prescriber (or pharmacy?)
</div>
</div>

---

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
- <a href="#output">output</a>
- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>

<br>

A task resource describes an activity that can be performed and tracks the state of completion of that activity. It is a representation that an activity should be or has been initiated, and eventually, represents the successful or unsuccessful completion of that activity.

Note that there are a variety of processes associated with making and processing orders. Some orders may be handled immediately by automated systems but most require real world actions by one or more humans. Some orders can only be processed when other real world actions happen, such as a patient presenting themselves so that the action to be performed can actually be performed. Often these real world dependencies are only implicit in the order details.

**A Task resource often exists in parallel with clinical resources.** 

For example, a Task could request fulfillment of a ServiceRequest ordering a Procedure that would result in a Procedure, Observation, DiagnosticReport, ImagingStudy or similar resource. Another example would be a Task that requests fulfillment of a CommunicationRequest to be performed between various actors.

<br>

<a name="types"></a>
### Task Type

| Task Type | Description |
|--
| Request | Represents an order that needs to be fulfilled. The request will be contained in 'Task.input' |
| Event | Represents an order that has been or is being fulfilled. The events will be contained in 'Task.output'|

<br>

In simple workflow Requests and Events may be combined into one Task. For more complex workflow the use of sub-Tasks is allowed, in this case the use of 'basedOn' to reference the Request Task is recommended. See examples in {{pagelink:prescriptionmanagement}}

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

See {{pagelink:prescribingmodels}} for more details.

A single Code from {{pagelink: DM-MedicationRequest-Course-of-Therapy}} values.

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

Only `in-progress` and `rejected` are currently supported. 

`rejected` means I have taken no action on the order and I am returning the `prescription-order` to EPS. 

`in-progress` means I am still working on the `prescription-order` task and I am altering one the actions I have previously made (e.g. cancelling a previous `dispense-notification`) 

<a name="statusReason"></a>
### statusReason

A code from {{pagelink:DM-Task-Reason-Code}} 
Only codes from {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason}} can be used when the status is `in-progress`.
Only codes from {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-return-status-reason}} can be used when the status is `rejected`.

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
For Tasks with a status of `in-progress` this will be a `dispense-notification` message. 
For Tasks with a status of `rejected` this will be the `prescription-order` message from the Task/$release operation.

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

A code from {{pagelink:DM-Task-Reason-Code}} 
Only codes from {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason}} can be used when the status is `in-progress`.
Only codes from {{link:https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-return-status-reason}} can be used when the status is `rejected`.

```json
"reasonCode": {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/EPS-task-dispense-withdraw-reason",
                "code": "DA",
                "display": "Dosage Amendments"
            }
        ]
    }
```

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


<a name="output"></a>
### output

Information produced as part of task.

For `event` Tasks this will contain references to the key resources that are produced on completion of the Task. E.g. for dispense-notification this will be the MedicationDispense resources.

```json
"output":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "373784005",
                        "display": "Dispensing medication"
                    }
                ]
            },
            "valueReference": {
                "type": "MedicationDispense",
                "reference": "https://prescriptions.spineservices.nhs.uk/FHIR/R4/MedicationDispense/fd833d33-f128-4fa2-a807-1fc8a7db2658",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/prescription-dispense-item-number",
                    "value": "fd833d33-f128-4fa2-a807-1fc8a7db2658"
                },
                "display": "Paracetamol 500mg soluble tablets (Alliance Healthcare (Distribution) Ltd) 60 tablet"
            }
        },
```

 
<a name="search"></a>
## Search Parameters

<!--
@```
from CapabilityStatement
where url='https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance' 
for rest.resource(where type = 'Task').searchParam 
select name, type, documentation   
```
-->

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="15%">Name</th>
     <th data-no-sort width="15%">Type</th>
     <th data-no-sort width="35%">Description</th>
      <th data-no-sort width="15%">Conformance</th>
       <th data-no-sort width="20%">Path</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
authored-on 
    </td>
    <td>
  date
    </td>
     <td>
Search by creation date (of prescription)
    </td>
    <td>
SHOULD
    </td>
    <td>
Task.authoredOn
    </td>
   </tr>  
     <tr>
    <td>
identifier 
    </td>
    <td>
  token
    </td>
     <td>
Search for a task instance by its business identifier
    </td>
    <td>
MAY
    </td>
    <td>
Task.identifier
    </td>
   </tr> 
    <tr>
    <td>
focus:identifier 
    </td>
    <td>
  token
    </td>
     <td>
Search by prescription short form id
    </td>
    <td>
SHOULD
    </td>
    <td>
Task.focus.identifier
    </td>
   </tr>  
    <tr>
    <td>
owner:identifier 
    </td>
    <td>
  token
    </td>
     <td>
Search by task (Prescription) owner
    </td>
    <td>
SHALL
    </td>
    <td>
Task.owner
(Organization)
    </td>
   </tr>   
    <tr>
    <td>
 patient:identifier
    </td>
    <td>
token
    </td>
     <td>
The identity of a patient to list Tasks (prescription) for
    </td>
    <td>
SHALL
    </td>
    <td>
Task.for.where(resolve() is Patient)
(Patient)
    </td>
   </tr>  
    <tr>
    <td>
business-status
    </td>
    <td>
 token
    </td>
     <td>
Search by business status
    </td>
    <td>
SHOULD
    </td>
    <td>
Task.businessStatus
    </td>
   </tr> 
      <tr>
    <td>
status
    </td>
    <td>
 token
    </td>
     <td>
Search by task (/prescription) status
    </td>
    <td>
SHOULD
    </td>
    <td>
Task.status
    </td>
   </tr>  
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/task.html#search" target="_blank">Task - Search Parameters</a>

<br>


<a name="mandatorysearch"></a>
### Mandatory Search Parameters

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?patient:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Task?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9876543210`

Return all Task resources for Patients with a NHS Number of 9876543210

#### owner:identifier

**SHALL** support searching using the `owner:identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?owner:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Task?owner:identifier=https://fhir.nhs.uk/Id/ods-organization-code|FA666`

Return all Task resources for ODS Code of FA666

<br>

#### focus:identifier

**SHALL** support searching using the `focus:identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?focus:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Task?focus:identifier=https://fhir.nhs.uk/Id/prescription-order-number|2D35F7-ZA0448-11E88Z`

Return all Task resources for with prescription short form of 2D35F7-ZA0448-11E88Z

<br>

<a name="optionalsearch"></a>
### Optional Search Parameters

#### authored-on + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `authored-on` search parameters

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?patient:identifier={system|}[code]&authored-on=[date]
</div>

Example:

`GET [baseUrl]/MedicationRequest?patient:identifier=9876543210&authored-on=ge2010-01-01&authored-on=le2011-12-31`

Return all Task resources that have a authoredon greater than or equal to 1st Jan 2010, a date less than or equal to 31st Dec 2011 and Patient with an identifier code of 9876543210.

#### identifier

**SHOULD** support searching using the `identifier` search parameter.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/Task?identifier=https://fhir.nhs.uk/Id/prescription-order-number|DC2C66-A1B2C3-23407B`


#### business-status + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `business-status` search parameters

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?patient:identifier={system|}[code]&business-status=[code]
</div>

Example:

`GET [baseUrl]/Task?patient:identifier=9876543210&business-status=active`

Return all Task resources with a status of active and Patient with an identifier code of 9876543210.

#### business-status + owner:identifier

**SHOULD** support searching using the combination of the `owner:identifier` and `business-status` search parameters

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/Task?owner:identifier={system|}[code]&business-status=[code]
</div>

Example:

`GET [baseUrl]/Task?https://fhir.nhs.uk/Id/ods-organization-code|FA666&business-status=active`

Return all Task resources with a status of active and owner with an ODS code of FA666.


