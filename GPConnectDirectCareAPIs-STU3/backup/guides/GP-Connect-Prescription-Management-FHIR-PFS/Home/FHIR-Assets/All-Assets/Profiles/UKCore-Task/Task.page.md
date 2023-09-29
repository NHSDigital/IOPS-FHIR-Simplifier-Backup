## {{page-title}}

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#profile-1" role="tab" data-toggle="tab">Profile</a>
      </li>
      <li role="presentation">
        <a href="#dictionary-1" role="tab" data-toggle="tab">Dictionary</a>
      </li>
        <li role="presentation">
        <a href="#example-1" role="tab" data-toggle="tab">Example</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet nhsd-!t-margin-bottom-6">
    <div role="tabpanel" class="tab-pane active" id="profile-1">
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task}} 
    </div>
        <div role="tabpanel" class="tab-pane" id="example-1">
        {{json:7c747c6e-15c8-4b2f-8aa0-441f2ef703d6-duplicate-2}} 
    </div>
  </div>
</div>

### Definition

A `Task` resource describes an activity that can be performed and tracks the state of completion of that activity. It is a representation that an activity should be or has been initiated, and eventually, represents the successful or unsuccessful completion of that activity.

A `Task` resource often exists in parallel with clinical resources.

In this instance, the task will exist have a focus reference of a `MedicationRequest`. 

### Minimum Viable Content
A minimum viable content that all provider and consumer systems should support is the following elements.

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Required?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>instantiatesCanonical</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>instantiatesUri</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>groupIdentifier</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>partOf</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        <tr>
            <td>status</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>statusReason</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Conditional"></td>
        </tr>
        <tr>
            <td>businessStatus</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>intent</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>priority</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>        
        <tr>
            <td>description</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>focus</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>for</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>encounter</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>executionPeriod</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>authoredOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>lastModified</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>requester</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>performerType</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>owner</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>insurance</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Optional"></td>
        </tr>
        <tr>
            <td>relevantHistory</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>restriction</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>input</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Conditional"></td>
        </tr>
        <tr>
            <td>output</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Conditional"></td>
        </tr>
    </tbody>
</table>

---

### id

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>identifier</td>
      <td>required</td>
      <td>1:1</td>
      </tr>
    </tbody>
</table>

The logical identifier of the Task resource.

#### Example
```json
 "id":"44f85d15-8744-47c2-a790-4f5e38aacdb0" 
```


### meta.profile

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>uri</td>
      <td>required</td>
      <td>1:1</td>
      </tr>
    </tbody>
</table>

The `Task` profile URL.

Fixed value: `https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task`

#### Example
```json
"meta": {
    "profile": [
      "https://fhir.hl7.org.uk/StructureDefinition/UKCore-Task"
    ]
}
```


### identifier

`identifier` must be present within the task resource and the value must be a UUID.

```json
"identifier":  [
    {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "5AC84C11-DB8B-44DA-8FCF-8980B3D13596"      
    }
],
```
#### Comment
This is a business identifier, not a resource identifier.

### status

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>code</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>


The status of the Task must be provided and updated as the Task passes through the GP system workflow.

<table data-responsive>
    <thead>
        <tr>
            <th>Status</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>requested</td>
            <td>Repeat request has been submitted to the GP practice but processing has not started.</td>
        </tr>
        <tr>
            <td>accepted</td>
            <td>The request has passed auto-system checks, e.g. valid patient, practice, etc. and is now pending user processing.
</td>
        </tr>
        <tr>
            <td>rejected</td>
            <td>The request will not be actioned. The business reason will be conveyed in ‘statusReason’, e.g. patient not known at the practice.</td>
        </tr>
        <tr>
            <td>cancelled</td>
            <td>The patient cancelled the request before it was actioned.</td>
        </tr>
        <tr>
            <td>in-progress</td>
            <td>The request has been processed by a prescription clerk and is awaiting confirmation/authorisation (signing) by a prescriber.</td>
        </tr>
        <tr>
            <td>completed</td>
            <td>The prescription has been authorised/signed. Refer to the EPS state model for the dispensing status.</td>
        </tr>
        <tr>
            <td>failed</td>
            <td>A prescription has not been authorised. The business reason will be conveyed in ‘statusReason’, e.g. on clinical grounds.</td>
        </tr>
      </tbody>
</table>

#### Example
```json
 "status": completed
```

### statusReason

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>string</td>
        <td>optional, only used to notify the patient of rejection reasons</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

This will be free text containing the rejection reason to be shown back to the patient. 

```json
"statusReason": {
    "text": "No longer suitable, please contact GP to organise an appointment"
},
```

### intent

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>code</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

Is needed for FHIR compliance reasons. The value must always be `order` in this use case.

```json
    "intent": "order",
```

### code

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>code</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The code indicates the action to perform on the focus resource. 

It is a [Snomed CT](http://snomed.info/sct) and must always be set `Renewal of prescription`.


<table data-responsive>
    <thead>
        <tr>
            <th>Snomed CT</th>
            <th>Display</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>103742009</td>
        <td>Renewal of prescription</td>
      </tr>
    </tbody>
</table>


```json
"code" : {
    "coding" : [ {
      "system" : "http://snomed.info/sct",
      "code" : 103742009,
      "display" : "Renewal of prescription"
    } ]
  },
```

### focus

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Reference(MedicationRequest)</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The focus must point to a previous [`MedicationRequest`](https://simplifier.net/guide/GP-Connect-Prescription-Management-FHIR-PFS/Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationRequest?version=current) when requesting an instance of a prescription. The `MedicationRequest` must have an intent of `plan`. 

In returning the Task resource the provider must return a short summary of the referenced medication resource under the `display` element with the corresponding reference.

This display must contain the type of prescription, i.e. repeat, acute etc. and the title of the medication. See the example below.

#### Example
```json
  "focus": {
    "reference": "MedicationRequest/b269d1d7-1acf-47bb-8b3c-e38b583d9a07"
    "display": "Repeat prescription for Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
  },
```

### for 
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Reference(Patient)</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

This must reference the patient that the request is for, using NHS number as the ID.

#### Example
```json
  "for" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : 9000000009
    },
    "display" : "Jane Smith"
  },
```

### authoredOn
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>dateTime</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The `dateTime` of the request being made.

#### Example
```json
  "authoredOn" : "2022-10-13T09:20:27.000Z",
```

### lastModified
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>dateTime</td>
        <td>optional</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>
The `dateTime` that the Task object was last modified.

#### Example
``` json
  "lastModified" : "2022-10-13T09:20:27.000Z",
```

### requester
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Reference(Patient)</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

In this use case, since it is Patient Facing the requester must always be the Patient. Beyond MVP this could be updated to facilitate proxy ordering.

#### Example
```json
"requester" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : 9000000009
    },
    "display" : "Jane Smith"
},
```

### note
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Annotation</td>
        <td>optional</td>
        <td>0:1</td>
      </tr>
    </tbody>
</table>

Note to be supplied by the patient when completing the request.

#### Example
```json
  "note": [
    {
      "authorString": "Patient",
      "text": "ran out of previous prescription"
    }
  ]
```

### input
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Code</td>
        <td>optional</td>
        <td>0:1</td>
      </tr>
    </tbody>
</table>

Information used to perform the task.

In this case it will be supplied when the patient wishes for their prescription to be dispensed by a different pharmacy to their nominated pharmacy on PDS.

When applicable it must contain the organization ODS code and reference the code `preferred-performer`. 

The set of prescription ordering parameters can be found [here.](https://simplifier.net/gpconnect2/gpconnect-prescriptionorderingparameters)

#### Example
``` json
"input": [
    {
        "type": {
            "coding": [
                {
                    "system": "https://fhir.hl7.org.uk/GPConnect-PrescriptionOrderingParameters",
                    "code": "preferred-performer",
                    "display": "Preferred performer"
                }
            ]
        },
        "valueIdentifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FLM49"
        }
    }
]
```

### output
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Code</td>
        <td>Conditional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Information produced as part of the task.

This can be used to identify the prescription outside of the scope of the patient facing API. 

In this specific case, once the prescription is created and been sent to EPS to be dispensed. This allows full end to end tracking of the request.

When applicable it must contain the EPS prescription ID and reference the code `sent-to-eps`.

The set of prescription ordering parameters can be found [here.](https://simplifier.net/gpconnect2/gpconnect-prescriptionorderingparameters)

#### Example
``` json
"output": [
    {
        "type": {
            "coding": [
                {
                    "system": "https://fhir.hl7.org.uk/GPConnect-PrescriptionOrderingParameters",
                    "code": "sent-to-eps",
                    "display": "Sent to EPS"
                }
            ]
        },
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "4857b9d3-b714-44b9-9e67-3df67275b785"
            }
    }
]
```