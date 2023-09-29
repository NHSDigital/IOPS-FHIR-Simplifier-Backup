## NHSDigital-MedicationDispense

| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense](https://simplifier.net/guide/DigitalMedicines/NHSDigital-MedicationDispense) | 


<br />

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
            Combined with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationDispense}} <br><br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br>
            {{dict: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense, hybrid}}
        </div>
         <div id="Constraints"  class="tab-pane">

<br />

@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense'
for differential.element.constraint
select key, human, severity, expression
```

</div>
        <div id="Examples"  class="tab-pane">
<br />
See examples in {{pagelink:dispense-notification}}
        </div>
    </div>
</div>



---


<br>

- <a href="#mustSupport">Must Support, Optional and Not Supported</a>
- <a href="#prescriptionStatus">extension prescriptionStatus</a>
- <a href="#repeatInformation">extension repeatInformation</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#medication">medication</a>
- <a href="#subject">subject (patient)</a>
- <a href="#performer">performer (Pharmacist and Pharmacy)</a>
- <a href="#authorizingPrescription">authorizingPrescription (orginal prescription)</a>
- <a href="#type">type</a>
- <a href="#quantity">quantity</a>
- <a href="#daysSupply">daysSupply</a>
- <a href="#whenPrepared">whenPrepared</a>
- <a href="#whenHandedOver">whenHandedOver</a>
- <a href="#dosageInstruction">dosageInstruction</a>
- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>


<br>

<a name="mustSupport"></a>
### Must Support, Optional and Not Supported

Elements marked with a <span style="background-color:red;color:white;">S</span> **MUST** be supported by both producing and receiving systems. They should be populated if the data exists or the profile has made them mandatory. 

The following elements **SHOULD NOT** are not expected to be supported by consuming or receiving systems.

- `detectedIssue`

Elements that are neither marked as `Must Support` or listed as unsupported are optional. At present they will not be processed by EPS, however the intention is a future version of EPS will pass all elements to recipients. It is recommended these elements are populated from the guidance in [UKCore Medicines](https://simplifier.net/guide/ukcoreimplementationguideformedicines/Home)



<br>

<a name="prescriptionStatus"></a>
### prescriptionStatus (extension) <a href="#prescriptionStatus" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This is the overall status of the `prescription-order`, it is not the status of the individual prescription item. This is a code from {{pagelink:DM-Task-Status-Reason.md}}, all prescription status reasons in a `dispense-notification` FHIR Message Bundle must be the same.

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/CodeSystem/EPS-task-business-status",
            "code": "0003",
            "display": "With Dispenser - Active"
        }
    }
]
```
<br>

<a name="repeatInformation"></a>
### repeatInformation (extension)

The extension {{link:https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation}} is mandatory for `continuous` and `continuous-repeat-dispensing`. The following elements **MUST** be populated 

- numberofRepeatsAllowed 
- numberOfRepeatsIssued 

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
        "extension": [
            {
                "url" : "numberOfRepeatsAllowed",
                "valueInteger" : 3
            },
            {
                "url" : "numberOfRepeatsIssued",
                "valueInteger" : 2
            }
        ]
    }
]
```

<br>

<a name="identifier"></a>
### identifier <a href="#identifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Each MedicationDispense **MUST** be identified by an Universal Unique Identifiers (UUIDs) with a system of `https://fhir.nhs.uk/Id/prescription-dispense-item-number`

UUID example (for illustration purposes only);

**4509B70D-D8B8-EA03-1105-64557CB54A29**


```json
 "identifier":  [
    {
        "system": "https://fhir.nhs.uk/Id/prescription-dispense-item-number",
        "value": "4509B70D-D8B8-EA03-1105-64557CB54A29"
    }
]
```

<br>

<a name="status"></a>
### status (Dispense status) <a href="#status" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The status of the individual medication item, this will normally indicate whether the medication has been picked up or not. The full set of statuses is {{link:http://hl7.org/fhir/ValueSet/medicationdispense-status}}

| Code | Display | Definition |
|--
| completed | Completed | The dispensed product has been picked up. |
| in-progress | In Progress | The dispensed product is ready for pickup. |

Example:

```json
"status": "completed"
```
<br>

<a name="medication"></a>
### medication[x] <a href="#medication" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Actual Medical Product Packs (AMPP) SHOULD be used. The ValueSet for medication is {{pagelink:DM-MedicationDispense-Code}}
It is valid to include a FHIR Medication resource within the FHIR Message, this practice is discouraged to simplify handling of the event messages.

See also {{pagelink:Dispensing}}

<table>
<thead>
<th data-no-sort width="25%">
dm+d Category
</th>
<th data-no-sort width="50%">
dm+d Description
</th>
<th data-no-sort width="25%">
UK SNOMED Members Of
</th>

</thead>
<tr>
<td>
VMPP
</td>
<td>
Virtual Medical Product Pack
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000571000001104" target="_blank">999000571000001104</a>
</td>

</tr>
<tr>
<td>
AMPP
</td>
<td>
Actual Medical Product Pack
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000551000001106" target="_blank">999000551000001106</a>
</td>
</tr>
<tr>
<td>
VMP
</td>
<td>
Virtual Medical Product
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000561000001109" target="_blank">999000561000001109</a>
</td>
</tr>
<tr>
<td>
AMP
</td>
<td>
Actual Medical Product
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000541000001108" target="_blank">999000541000001108</a>
</td>
</tr>
</table>

<br>

```json
"medicationCodeableConcept": {
        "coding":  [
        {
            "system": "http://snomed.info/sct",
            "code": "10460811000001109",
            "display": "Amoxil 500mg capsules (Dowelhurst Ltd) 12 capsule"
        }
    ]
}
```
<br>

<a name="subject"></a>
### subject (patient) <a href="#subject" title="link to here" class="self-link"><i class="bi-link"></i></a> 

A reference to the patient via a traced NHS Number is required, an untraced NHS Number MUST NOT be used. This can be sent in two ways, first option is via a `identifier reference`. Only the NHS Number. Full example: {{pagelink: 1stdispenseevent-partial.md}}

```json
"subject": {
    "type": "Patient",
    "identifier": {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "2300992742"
    }
}
```

Second option uses a FHIR Patient resource to convey the NHS Number.  
Full example: {{pagelink: 1stdispenseevent-partialwithPatientResource.md}}
The reference in the MedicationDispesnse is now a `resource reference`. 

```json
 "subject": {
                    "type": "Patient",
                    "reference": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
                    "display": "Miss Bernie Kanfeld"
                }
```

The NHS Number has moved to the Patient resource alongside other patient identifiers such as MRN. E.g. 

```json
"fullUrl": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
"resource": {
                "resourceType": "Patient",
                "identifier": [
                    {
                        "extension": [
                            {
                                "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberVerificationStatus",
                                "valueCodeableConcept": {
                                    "coding": [
                                        {
                                            "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-NHSNumberVerificationStatus",
                                            "code": "01",
                                            "display": "Number present and verified"
                                        }
                                    ]
                                }
                            }
                        ],
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9876543210"
                    },
                    {
                        "system": "https://fhir.leedsth.nhs.uk/Id/pas-number",
                        "value": "ABC8650149"
                    },
                    {
                        "system": "https://fhir.leedsth.nhs.uk/Id/PPMIdentifier",
                        "value": "1"
                    }
                ],
               ... other elements removed from example.
            }
```

It is anticipated that hospital pharmacies will prefer the later option for compatibility with other systems. Community pharmacies are anticipated to prefer the former option.

<br>

<a name="performer"></a>
### performer (Pharmacist and Pharmacy) <a href="#performer" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The pharmacist and pharmacy MUST be present and MUST use `identifier references`. This means FHIR Practitioner, Organization and PractitionerRole resource are not included in the FHIR Message. Professional codes and ODS codes should be used instead. `sds-user-role-id` is permitted to identify a Practitioner(& Role) but professional codes are preferred to support wider NHS interoperability.

```json
 "performer": [
                    {
                        "actor": {
                            "type" : "Practitioner",
                            "identifier":  {
                                "system": "https://fhir.hl7.org.uk/Id/gphc-number",
                                "value": "7654321"
                            },
                            "display": "Mr Peter Potion"
                        }
                    },
                    {
                        "actor": {
                            "type": "Organization",
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                                "value": "AB123"
                            },
                            "display": "The Simple Pharmacy"
                        }
                    }
                ],
```


<br>

<a name="authorizingPrescription"></a>
### authorizingPrescription (Original Prescription) <a href="#authorizingPrescription" title="link to here" class="self-link"><i class="bi-link"></i></a> 


```json
"authorizingPrescription": [
    {
        "extension": [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-GroupIdentifier",
                "extension": [
                    {
                        "url": "shortForm",
                        "valueIdentifier": {
                            "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                            "value": "3C2366-B81001-0A409U"
                        }
                    },
                    {
                        "url": "UUID",
                        "valueIdentifier": {
                            "system": "https://fhir.nhs.uk/Id/prescription",
                            "value": "66317E0C-CE13-59AD-9979-9B568E080160"
                        }
                    }
                ]
            }
        ],
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
            "value": "E76622AE-E2DB-5683-2045-D1C229EDA3A2"
        }
    }
]
```
<br>

<a name="type"></a>
### type <a href="#type" title="link to here" class="self-link"><i class="bi-link"></i></a> 

```json
"type": {
    "coding": [
        {
            "system": "https://fhir.nhs.uk/CodeSystem/medicationdispense-type",
            "code": "0001",
            "display": "Item fully dispensed"
        }
    ]
}
```

<br>

<a name="quantity"></a>
### quantity <a href="#quantity" title="link to here" class="self-link"><i class="bi-link"></i></a> 

```json
"quantity": {
    "value": 28,
    "unit": "capsule",
    "system": "http://snomed.info/sct",
    "code": "3316911000001105"
}
```
<br>

<a name="daysSupply"></a>
### daysSupply <a href="#daysSupply" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The amount of medication expressed as a timing amount.

```json
"daysSupply": {
    "value": 7,
    "unit": "Day",
    "system": "http://unitsofmeasure.org",
    "code": "d"
}
```
<br>

<a name="whenPrepared"></a>
### whenPrepared <a href="#whenPrepared" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The time when the dispensed product was packaged and reviewed.

```json
"whenPrepared": "2004-09-16T16:30:00+00:00"
```
<br>

<a name="whenHandedOver"></a>
### whenHandedOver <a href="#whenHandedOver" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The time the dispensed product was provided to the patient or their representative.
In HL7 v3 this is: *The date and local time that the medication is issued by the dispenser*.

```json
"whenHandedOver": "2004-09-16T16:30:00+00:00"
```
<br>

<a name="dosageInstruction"></a>
### dosageInstruction <a href="#dosageInstruction" title="link to here" class="self-link"><i class="bi-link"></i></a> 

At present only the `text` element **MUST** be provided. It is recommended the guidance in [FHIR Dose Syntax Implementation Guidance](https://developer.nhs.uk/apis/dose-syntax-implementation-1-3-2-alpha/dosage-overview.html) is followed. 

Note the structure of this section is similar as the {{pagelink:NHSDigital-MedicationRequest.md}} from the `prescription-order`.

```json
"dosageInstruction": [
    {
        "text": "4 times a day for 7 days",
        "timing": {
            "repeat": {
                "boundsDuration": {
                    "value": 7,
                    "unit": "d"
                },
                "frequency": 4,
                "period": 1,
                "periodUnit": "d"
            }
        },
        "doseAndRate": [
            {
                "doseQuantity": {
                    "value": 1,
                    "unit": "capsule",
                    "system": "http://snomed.info/sct",
                    "code": "3316911000001105"
                }
            }
        ]
    }
]
```

<br>

<a name="search"></a>
## Search Parameters

<!--
@```
from CapabilityStatement
where url='https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance' 
for rest.resource where type = 'MedicationDispense' 
select searchParam.name, searchParam.type, searchParam.documentation
      
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
 code
    </td>
    <td>
 token
    </td>
     <td>
Returns dispenses of this medicine code
    </td>
    <td>
MAY
    </td>
    <td>
(MedicationDispense.medication as CodeableConcept)
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
Returns dispenses with this external identifier
    </td>
    <td>
MAY
    </td>
    <td>
MedicationDispense.identifier
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
The identity of a patient to list orders for
    </td>
    <td>
SHALL
    </td>
    <td>
MedicationDispense.patient
(Patient)
    </td>
   </tr>  
    <tr>
    <td>
 prescription:identifier
    </td>
    <td>
 token
    </td>
     <td>
The identity of a prescription to list dispenses from
    </td>
    <td>
MAY
    </td>
    <td>
MedicationDispense.authorizingPrescription
(MedicationRequest)
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
Returns dispenses with a specified dispense status
    </td>
    <td>
SHOULD
    </td>
    <td>
MedicationDispense.status
    </td>
   </tr>  
     <tr>
    <td>
 whenhandedover
    </td>
    <td>
 date
    </td>
     <td>
Returns dispenses handed over on this date
    </td>
    <td>
SHALL
    </td>
    <td>
MedicationDispense.whenHandedOver
    </td>
   </tr>  
   </tbody>
</table>

<br> 

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/medicationdispense.html#search" target="_blank">MedicationDispense - Search Parameters</a>

<a name="mandatorysearch"></a>
### Mandatory Search Parameters

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?patient:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9876543210`

Return all MedicationDispense resources for Patients with a NHS Number of 9876543210

<br>

#### whenhandedover + patient:identifier

**SHALL** support searching using the combination of the `patient:identifier` and `whenhandedover` search parameters
- including support for these date comparators: gt,lt,ge,le
- including optional support for composite AND search on date (e.g.date=[date]&date=[date]]&...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?patient:identifier={system|}[code]&whenhandedover=[date]
</div>

Example:

`GET [baseUrl]/MedicationDispense?patient:identifier=9876543210&whenhandedover=ge2010-01-01&authoredon=le2011-12-31`

Return all MedicationDispense resources that have a whenhandedover greater than or equal to 1st Jan 2010, a date less than or equal to 31st Dec 2011 and Patient with an identifier code of 9876543210. 

<br>

<a name="optionalsearch"></a>
### Optional Search Parameters

#### code + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `code` search parameters
- including optional support for composite OR search on code (e.g. code={system|}[code],{system|}[code],...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?patient:identifier={system|}[code]&code={system|}|[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?patient:identifier=9876543210&code=10460811000001109`

Return all MedicationDispense resources that have a medication code (e.g. dm+d or SNOMED CT) with code of 10460811000001109. 

#### group-identifier

**MAY** support searching using `group-identifier` search parameters: 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?group-identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?group-identifier=https://fhir.nhs.uk/Id/prescription-order-number|DC2C66-A1B2C3-23407B`

#### identifier

**MAY** support searching using `identifier` search parameters: 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?identifier=https://fhir.nhs.uk/Id/prescription-dispense-item-number|4509B70D-D8B8-EA03-1105-64557CB54A29`


#### prescription:identifier

**MAY** support searching using `prescription:identifier` search parameters: 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?prescription:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?prescription:identifier=https://fhir.nhs.uk/Id/prescription-order-item-number|E76622AE-E2DB-5683-2045-D1C229EDA3A2`


#### status + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `status` search parameters

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationDispense?patient:identifier={system|}[code]&status=[code]
</div>

Example:

`GET [baseUrl]/MedicationDispense?patient:identifier=9876543210&status=in-progress`

Return all MedicationRequest resources with a status of `in-progress` and Patient with an identifier code of 9876543210.


---
