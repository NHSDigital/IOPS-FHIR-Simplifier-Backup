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
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}} 
    </div>
    <div role="tabpanel" class="tab-pane" id="example-1">
{{json:b269d1d7-1acf-47bb-8b3c-e38b583d9a07}}
    </div>
  </div>
</div>

### Definition
An order or request for both supply of the medication and the instructions for administration of the medication to a patient. The resource is called "MedicationRequest" rather than "MedicationPrescription" or "MedicationOrder" to generalize the use across inpatient and outpatient settings, including care plans and so on, and to harmonize with workflow patterns.

### Minimum Viable Content
The minimum viable content that all provider and consumer systems should support contains the following elements:


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
            <td>extension[medicationRepeatInformation]</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Conditional"></td>
        </tr>        
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>status</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>statusReason</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>intent</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>category</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>priority</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
        <tr>
            <td>doNotPerform</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>reported</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>medicationCodeableConcept</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>subject</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>encounter</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>supportingInformation</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>authoredOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>requester</td>
            <td><span class="fas fa-check-circle text-sucess fa-lg"></td>
        </tr>
        <tr>
            <td>performer</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>performerType</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>recorder</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>instantiatesCanonical</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>instantiatesUri</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td><span class="fas fa-exclamation-circle text-warning fa-lg" title="Conditional"></td>
        </tr>
        <tr>
            <td>groupIdentifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>courseOfTherapyType</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>insurance</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>note</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>dispenseRequest</td>
            <td><span class="fas fa-times-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>substitution</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></td>
        </tr>
        <tr>
            <td>priorPrescription</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>detectedIssue</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>eventHistory</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
    </tbody>
</table>

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

The logical `identifier` of the `MedicationRequest` resource.

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

The `MedicationRequest` profile URL.

Fixed value: `https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest`

#### Example
```json
  "meta": {
    "profile": [
      "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest"
    ]
```


### extension:medicationRepeatInformation

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
      <td>Extension</td>
      <td>conditional</td>
      <td>0:1</td>
      </tr>
    </tbody>
</table>

Extension elements to hold details of repeat authorisation.

Only populate for a `MedicationRequest` with an intent = plan. For a `MedicationRequest` with an intent = order none of the repeatInformation fields are populated.

This extension must be present for `continuous` and `continuous-repeat-dispensing` therapy types.

##### medicationRepeatInformation.authorisationExpiryDate
Only populate for a `MedicationRequest` with an intent = plan. For a `MedicationRequest` with an intent = order this is not populated.

##### medicationRepeatInformation.numberOfPrescriptionsIssued
Running total of number of issues made against a repeat authorisation.

**MUST** be zero, if not yet issued.

#### Example
```json
"extension": [
    {
        "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation",
        "extension": [
            {
                "url": "numberOfPrescriptionsIssued",
                "valueUnsignedInt": 2
            },
            {
                "url": "authorisationExpiryDate",
                "valueDateTime": "2022-10-11T19:00:00.000Z"
            }
        ]
    }
],
```
### identifier

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

This **MUST** be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). This **MUST** be scoped by a provider specific namespace for the identifier.

Where consuming systems are integrating data from this resource to their local system, they **MUST** also persist this identifier at the same time.

If the EPS identifier is present (will only be with an `intent` of order) then the identifier.value is where the EPS Id SHOULD also be added. The codeSystem for this identifier is `https://fhir.nhs.uk/Id/prescription-order-item-number`

#### Example of intent order with EPS Id
```json
    "identifier" : [
        {
            "system" : "https://fhir.nhs.uk/Id/prescription-order-item-number",
            "value" : "4857b9d3-b714-44b9-9e67-3df67275b785"
        },
    ]
```

#### Example of intent plan with uuid
```json
"identifier": [
    {
        "system": "https://tools.ietf.org/html/rfc4122",
        "value": "42b4a841-9d69-4d13-bf91-ee5882e85765"
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

A code specifying the current state of the order. Generally, this will be active or completed state.

<table data-responsive>
    <thead>
        <tr>
            <th>code</th>
            <th>Definition</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>active</td>
        <td>Represents an active authorisation - used for active medications/medical devices.</td>
      </tr>
      <tr>
        <td>stopped</td>
        <td>Represents an authorisation which has been discontinued, cancelled or stopped.</td>
      </tr>
      <tr>
        <td>completed</td>
        <td>Represents an authorisation which has run its course.</td>
      </tr>
    </tbody>
</table>

For MedicationRequest instances where intent is set to plan:
*   For repeats and repeat dispensed the status refers to the status of the plan (the entire cycle of prescriptions).
*   For acutes the status refers to the status of the prescription issue.

For MedicationRequest instances where intent is set to order:

*  The status refers to the status of the prescription issue.

#### Example
``` json
  "status" : "active",
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
        <td>code</td>
        <td>optional</td>
        <td>0:1</td>
      </tr>
    </tbody>
</table>

Where a medication/medical device has been stopped (status == ‘stopped’), the reason is provided in the statusReason extension.

Mandatory for authorisations with stopped status.

Only populate for a MedicationRequest with an intent = plan. Do not populate for a MedicationRequest with an intent = order.

#### Example
```json
"statusReason": {
    "coding": [
        {
            "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-status-reason",
            "code": "0001",
            "display": "Prescribing Error"
        }
    ]
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

Whether the request is a `plan` or `order`. 

 * `plan` represents an authorisation of a medication or medical device

 * `order` represents a prescription or issue of a medication/medical device

#### Example

```json
 "intent" : "order",
```

### category
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

Required as part of the resource. Must be set to "community" as this includes requests for medications to be administered or consumed by the patient in their home (this would include long term care or nursing homes, hospices, etc.) 

```json
    "category": [
      {
        "coding": [
          {
            "system": "http://terminology.hl7.or/CodeSystem/medicationrequest-category",
            "code": "community",
            "display": "Community"
          }
        ]
      }
    ],
```

### medicationCodeableConcept
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

* The medicationCodeableConcept.text should be the description for the medication.

* The medicationCodeableConcept.coding.code should be the code for the medication.
    * Supported codesystems: [DM+D](https://services.nhsbsa.nhs.uk/dmd-browser/)

* The medicationCodeableConcept.coding.display should be the description for the medication, i.e. the same value as medicationCodeableConcept.text.

#### Example
```json
    "medicationCodeableConcept": [
      {
        "coding": [
          {
            "system": "https://dmd.nhs.uk",
            "code": 329526003,
            "display": "Apirin 300mg dispersible tablets"
          }
        ]
      }
    ],

```

### subject
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

Reference to the patient that the medication is for.

#### Example
```json
  "subject" : {
    "reference" : "Patient/9000000009",
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/nhs-number",
      "value" : "9000000009"
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

Authorisation date, when the medication/medical device was authorised.

#### Example
```json
"authoredOn" : "2022-10-13T16:20:27+07:00",
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
        <td>Reference</td>
        <td>optional</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

A business-required element identifying the clinically qualified human prescriber referenced by a PractitionerRole resource. 

They may be other possible references depending on the use case the full list is below. The resource being referenced should conform to one of the following:

* [Profile UKCore-Organization](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Organization?version=0.5.0)

* [Profile UKCore-Patient](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Patient?version=1.0.0)

* [Profile UKCore-Practitioner](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/Profile-UKCore-Practitioner?version=1.0.0)

* [Profile UKCore-PrasctitionerRole](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-PractitionerRole?version=1.0.0)

* [Profile UKCore-RelatedPerson](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-RelatedPerson?version=0.5.0)
 
* [UKCore-Device Profile](https://simplifier.net/hl7fhirukcorer4/ukcoredevice)

* [UKCore-CareTeam Profile](https://simplifier.net/hl7fhirukcorer4/ukcorecareteam)

#### Example
```json
 "requester" : {
    "reference" : "PractitionerRole/ed313d93-f470-420f-ae4e-2b7eb91d3f45",
    "display" : "Dr Jane Smith"
  },
```
### basedOn
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
        <td>Conditional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

This field is used to create the links between `MedicationRequest` profiles to represent the medication ordering process as described here. This MUST be used when a profile has an `intent` element that is set to `order` and is `basedOn` a `MedicationRequest` profile that has an `intent` set to `plan`.

DO NOT USE for authorisations - that is, for a `MedicationRequest` with `intent` of `plan`.

#### Example

```json
"basedOn": [
    {
    "reference": "MedicationRequest/06c7d0e2-1022-4e47-ac55-f6463d701a4f"
    }
],
```

### groupIdentifier
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

The EPS prescriptionID if this medication or medical device has been prescribed via the Electronic Prescriptions Service. The element in the Identifier data type that MUST be populated when a groupIdentifier is populated is identifier.value.

All EPS prescribed drugs *MUST* have the prescriptionID present in this field and have system element set to https://fhir.nhs.uk/Id/prescription-order-number.

#### Example

```json
 "groupIdentifier" : {
    "system" : "https://fhir.nhs.uk/Id/prescription-order-number",
    "value" : "PDI12E-Y765908-4FF3LQ"
  },
```

### courseOfTherapyType

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
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

Necessary in order to denote the type of therapy, such as an acute/one-off medication compared to a repeat/on-going medication.

Will be used in order to denote whether a prescription is acute or repeat.

<table data-responsive>
    <thead>
        <tr>
            <th>Code</th>
            <th>System</th>
            <th>Display</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>continuous</td> <td>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy</td>
        <td>Continuous long term therapy</td>
      </tr>
            <tr>
        <td>acute</td>   <td>http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy	</td>
        <td>Short course (acute) therapy</td>
      </tr>
    </tbody>
</table>

#### Example
```json
  "courseOfTherapyType" : {
    "coding" : [ {
      "system" : "https://fhir.hl7.org.uk/CodeSystem/UKCore-MedicationRequestCourseOfTherapy",
      "code" : "continuous",
      "display" : "Continuous long term therapy"
    } ]
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
        <td>0:*</td>
      </tr>
    </tbody>
</table>

Use when the prescriber wishes to provide supporting textual information to the dispenser.

#### Example

```json
      "note" : [ {
        "authorString" : "Patient",
        "text" : "Ran out of previous prescription"
      } ]
```

### dosageInstruction
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
        <td>Dosage</td>
        <td>required</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

Preferable as a structured dosage aligned to the [FHIR Dose Syntax Guidance](https://simplifier.net/guide/ukcoreimplementationguideformedicines/elementdosage?version=current) but as a minimum, dosage.text.

#### Example
```json
  "dosageInstruction" : [ {
        "text" : "One to two puffs to be inhaled as needed",
        "method" : {
          "coding" : [ {
            "system" : "http://snomed.info/sct",
            "code" : 420652005,
            "display" : "Until Gone"
          } ]
        }
    } ]
```

### dispenseRequest
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
        <td>BackboneElement</td>
        <td>required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

##### dispenseRequest.numberOfRepeatsAllowed
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
        <td>unsignedInt</td>
        <td>optional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

An integer indicating the number of times, in addition to the original dispense, (aka refills or repeats) that the patient can receive the prescribed medication. Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus "3 repeats", then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.

The number of repeat issues authorised if specified.
MUST be present where a `continuous` is authorised for a defined number of issues.

MUST NOT be specified where the number of repeat issues has not been defined. Therefore, the `numberOfRepeats` allowed is the total number of allowed issues. See also extension `repeatInformation`

##### Example
``` json
"numberOfRepeatsAllowed": 6,
```

#### dispenseRequest.quantity
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
    <td>simpleQuantity</td>
        <td>required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The amount that is to be dispensed for one fill.

```json
"quantity": {
    "value": 1,
    "unit": "inhaler",
    "system": "http://snomed.info/sct",
    "code": "334980009"
},
```

#### dispenseRequest.expectedSupplyDuration
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
        <td>Duration</td>
        <td>required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Number of days’ supply per dispense.

```json
"expectedSupplyDuration": {
    "value": 28,
    "unit": "days",
    "system": "http://unitsofmeasure.org",
    "code": "d"
},
```

#### dispenseRequest.performer
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
        <td>Duration</td>
        <td>required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Patients pharmacy preferences may be sourced from PDS.

Patients pharmacy preferences may be overriden by an 'one-off pharmacy nomination' by populating the dispenseRequest.performer.identifier with the ODS code of the destination pharmacy. The one off ODS code can be obtained from input element of the corresponding Task resource.

```json
    "performer": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FX748"
        }
    }
```

### substitution
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
        <td>BabckboneElement</td>
        <td>required</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

UK Core has profiled this element as mandatory and must have a default boolean value of `false` to denote substitution is not allowed.

#### Example
```json
    "substitution": {
        "allowedBoolean": false
    }
```