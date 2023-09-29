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
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement}} 
    </div>
    <div role="tabpanel" class="tab-pane" id="example-1">
{{json:44f85d15-8744-47c2-a790-4f5e38aacdb0}}
    </div>
  </div>
</div>

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
            <td>extension[pharmacistVerifiedIndicator]</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>extension[medicationPrescribingOrganization]</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>extension[medicationStatementLastIssued]</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>partOf</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
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
            <td>category</td>
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
            <td>context</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>effectivePeriod</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>dateAsserted</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>informationSource</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>derivedFrom</td>
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
            <td>note</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>dosage</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
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

The logical identifier of the `MedicationStatement` resource.

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

The `MedicationStatement` profile URL.

Fixed value: `https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement`

#### Example
```json
  "meta": {
    "profile": [
      "https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationStatement"
    ]
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

This must be populated with a globally unique and persistent identifier (that is, it doesn’t change between requests and therefore stored with the source data). 

Where consuming systems are integrating data from this resource to their local system, they must also persist this identifier at the same time.

#### Example

```json
    "identifier": {
      "system": "https://tools.ietf.org/html/rfc4122",
      "value": "123jkwndf-1234-dgdg-134dd-4f5e38aacdb0"
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
      <td>Reference</td>
      <td>required</td>
      <td>1:1</td>
      </tr>
    </tbody>
</table>

Must reference a `MedicationRequest` within the `basedOn` attribute: `MedicationRequests` provide details of specific prescriptions. The referenced `MedicationRequest` must have intent of `plan`.

The display within `basedOn` should quote the `courseOfTherapyType` from the referenced `MedicationRequest`, showing the prescription treatment type.

#### Example

```json
      "basedOn" : {
        "reference" : "MedicationRequest/0f450c33-67b2-4ca3-b0f9-fea75ccdcd44",
        "display" : "Acute prescription request for Amoxicillin 250mg capsules."
      },
```

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

The status of the authorisation.

Use one of `active`, `completed` or `stopped`:

* `active` represents an active authorisation - used for active repeat medications/medical devices

* `stopped` represents an authorisation which has been discontinued, cancelled or stopped

* `complete` represents an authorisation which has run its course

For repeat and repeat dispensed the status refers to the status of the plan (the entire cycle of prescriptions).

For acute, the status refers to the status of the prescription issue.

#### Example
```json
 "status": active
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

Where the requested medication is contained within the [NHS dm+d](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) then it must be recorded using the dm+d standard.

* The `medicationCodeableConcept.coding.code` should be the code for the medication.

* The `medicationCodeableConcept.coding.display` should be the description for the medication, i.e. the same value as medicationCodeableConcept.text.


#### Example 
``` json
    "medicationCodeableConcept": [
      {
        "coding": [
          {
            "system": "http://snomed.info/ct",
            "code": 3113111000001106,
            "display": "Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
          }
        ]
      }
    ]
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


Who the medication/medical device is for - that is, to whom it will be administered.

Reference to Patient.

#### Example
``` json
"subject": {
    "reference": "Patient/9000000009",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9000000009"
    },
    "display": "Jane Smith"
},
```

### effectivePeriod
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
        <td>Period</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The period the medication or medical device is authorised under this medication/medical device plan. For items that are repeats and repeat dispensed this refers to the entire cycle of prescriptions made under the authorisation. For acutes, this refers to the period of the prescription issue.

`effectivePeriod.start` is **mandatory**

The date from which the medication or medical device is authorised under this plan.

Use one of the following dates in order of descending preference:

* the authorised date as recorded in the patient record

    * for authorisation that were performed during a consultation this will be the date when the consultation took place

* the date of the first issue under the medication/medical device plan
* the date the medication/medical device plan was recorded onto the system (the audit date)

`effectivePeriod.end` is **required**

The date when the authorisation under this plan ends.

Where the medication/medical device plan is still active, set to **null**.

Where the medication/medical device plan has ended use one of the following dates in order of descending preference:

* the end date recorded in the patient record

* the end date of the final issue under the medication/medical device plan. This is the start date of the final issue plus the expected supply duration.

* the date the plan was updated to ended

* the Period.start date

* this option should only occur where data has been lost (for example, during the record transfer between two systems) and is used to ensure that an ended plan will always have an end date

#### Example
```json
    "effectivePeriod": {
      "start": "2022-10-23T13:50:00+00:00",
      "end": "2023-01-10T13:50:00+00:00"
    },
```

### dateAsserted

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

When this medication statement was believed true.

Unless there is a distinct user-modifiable availability date/time for the authorisation, this is the audit trail date/time for when the authorisation was entered.

``` json
    "dateAsserted": "2022-11-23T13:50:00+00:00",
```

### dosage

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
        <td>0:*</td>
      </tr>
    </tbody>
</table>

Preferable as a structured dosage aligned to the [FHIR Dose Syntax Guidance](https://simplifier.net/guide/ukcoreimplementationguideformedicines/elementdosage?version=current) but as a minimum, dosage.text must be used.