### NHSDigital-MedicationRequest


| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest](https://simplifier.net/guide/DigitalMedicines/NHSDigital-MedicationRequest) | 

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
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}} <br>
            <br />
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
{{dict:  https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
{{pagelink: MedicationRequestControlledDrug}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink: MedicationRequestMultipleDrugCodes}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink: MedicationRequestRepeatDispensing}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest'
for differential.element.constraint
select key, human, severity, expression
```
        </div>
    </div>
</div>


---
<br>


Digital Medicine has the following extra rules in addition to UK Core MedicationRequest:

- <a href="#mustSupport">Must Support, Optional and Should Not Support</a>
- <a href="#repeatInformation">extension repeatInformation</a>
- <a href="#responsiblePractitioner">extension responsiblePractitioner</a>
- <a href="#prescriptionEndorsement">extension prescriptionEndorsement</a>
- <a href="#prescriptionTaskStatusReason">extension prescriptionTaskStatusReason</a>
- <a href="#NHSBSAprescriptionType">extension NHSBSAprescriptionType</a>
- <a href="#controlledDrug">extension controlledDrug</a>
- <a href="#dispensingInformation">extension dispensingInformation</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#statusReason">statusReason</a>
- <a href="#intent">intent</a>
- <a href="#category">category</a>
- <a href="#medication">medication</a>
- <a href="#subject">subject</a>
- <a href="#basedOn">basedOn</a>
- <a href="#groupIdentifier">groupIdentifier</a>
- <a href="#courseOfTherapyType">courseOfTherapyType</a>
- <a href="#requester">requester</a>
- <a href="#note">note</a>
- <a href="#dosageInstruction">dosageInstruction</a>
- <a href="#dispenseRequest">dispenseRequest</a>
  - <a href="#expectedSupplyDuration">expectedSupplyDuration</a>
  - <a href="#validityPeriod">validityPeriod</a>
  - <a href="#numberOfRepeatsAllowed">numberOfRepeatsAllowed</a>
  - <a href="#performer">performer</a>
- <a href="#substitution">substitution</a>
- <a href="#search">Search Parameters</a>
  - <a href="#mandatorysearch">Mandatory Search Parameters</a>
  - <a href="#optionalsearch">Optional Search Parameters</a>


<br>

<a name="mustSupport"></a>
### Must Support, Optional and Not Supported

Elements marked with a <span style="background-color:red;color:white;">S</span> **MUST** be supported by both producing and receiving systems. They should be populated if the data exists or the profile has made them mandatory. 

The following elements **SHOULD NOT** are not expected to be supported by consuming or receiving systems.

- `doNotPerform`
- `detectedIssue`

Elements that are neither marked as `Must Support` or listed as unsupported are optional. At present they will not be processed by EPS, however the intention is a future version of EPS will pass all elements to recipients. It is recommended these elements are populated from the guidance in [UKCore Medicines](https://simplifier.net/guide/ukcoreimplementationguideformedicines/Home)


<br>

<a name="repeatInformation"></a>
### Continous and Continuous Repeat Dispensing <a href="#repeatInformation" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The {{link:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation}} extension <b>MUST</b> be present for  `continuous` and `continuous-repeat-dispensing` therapy types. 


| Field | Description |
|--
| numberOfRepeatPrescriptionsIssued |  Running total of number of issues made against a repeat authorisation.   |
| numberOfRepeatPrescriptionsAllowed | Retired. See <a href="#numberOfRepeatsAllowed">numberOfRepeatsAllowed</a> | 
| authorisationExpiryDate | The date a repeat prescription authorisation will expire. | 

```json
"extension": [
  {
       "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation",
       "extension": [
           {
               "url": "numberOfRepeatPrescriptionsAllowed",
               "valueUnsignedInt": 4
           },
           {
               "url": "numberOfRepeatPrescriptionsIssued",
               "valueUnsignedInt": 1
           },
           {
               "url": "authorisationExpiryDate",
               "valueDateTime": "2020-08-07"
           }
       ]
   }
]
```

<br>

<a name="responsiblePractitioner"></a>
### Responsible Practitioner (extension responsiblePractitioner)  <a href="#responsiblePractitioner" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Must only be populated if the  <a href="#requester">requester</a> can not be responsible for the prescription, i.e. they would not be named as the prescriber on the FP10.

In that case, the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-ResponsiblePractitioner}} is mandatory.

```json
"extension": [
        
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-ResponsiblePractitioner",
        "valueReference": {
            "reference": "urn:uuid:a5acefc1-f8ca-4989-a5ac-34ae36741466",
            "display": "DR SAZ RAZ"
        }
    }
],
```

<br>

<a name="prescriptionEndorsement"></a>
### Endorsements (extension prescriptionEndorsement) <a href="#prescriptionEndorsement" title="link to here" class="self-link"><i class="bi-link"></i></a> 

NHS BSA Endorsements are carried in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement}}
The codes are contained in {{pagelink:DM-prescription-endorsement}} valueset

| Code	| Display |
|--
| CC	| 	Contraceptive |
| FS	| 	Sexual Health| 
| ACBS	| 	Advisory Committee on Borderline Substances. Part XV {{pagelink:DrugTariff}}| 
| SLS	| 	Selected List Scheme. Part XVIIIB {{pagelink:DrugTariff}}| 
| AF	| 	Food replacement/food supplement products| 

```json
"resourceType": "MedicationRequest",
    "extension":  [
      {
          "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement",
          "valueCodeableConcept": {
              "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-endorsement",
                    "code": "SLS",
                    "display": "Selected List Scheme"
                }
            ]
        }
    }
  ],
```

<br>



<a name="prescriptionTaskStatusReason"></a>
### Administrative Status (extension statusHistory) <a href="#prescriptionTaskStatusReason" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Should not be populated by prescribing systems. It is populated by EPS in 'prescription-order-response' messages. See {{pagelink:DM-MedicationRequest-Outcome}} for details.


<br>

<a name="NHSBSAprescriptionType"></a>
### NHS BSA Prescription Type (extension NHSBSAprescriptionType) <a href="#NHSBSAprescriptionType" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The vocabulary for the ‘PrescriptionType’ vocabulary is defined within the NHSBSA Overprint Specification.

The System must populate the ‘PrescriptionType’ attribute for the appropriate combination of prescriber and care setting. Retired codes within this vocabulary must not be used. See also {{pagelink:DM-Prescription-Type}}

```json
"extension":  [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionType",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/CodeSystem/prescription-type",
            "code": "1201",
            "display": "Outpatient Homecare Prescriber - Medical Prescriber"
        }
    }
    ]
```

<br>

<a name="controlledDrug"></a>
### Controlled Drugs (extension controlledDrug) <a href="#controlledDrug" title="link to here" class="self-link"><i class="fa-link"></i></a> 

Controlled drugs are recorded in the category section alongside the episode class (if applicable). The codes must belong to the {{pagelink:DM-MedicationRequest-Controlled-Drug}} valueset.


The table below summarises the EPS requirements for the CD schedules. The terms “Hand signature” and “Electronic signature” expressed in the table are shortened references to the legal definition of signature requirements within government legislation.

| Sch. | Code | Signing Legal Requirement | EPS Scope | Expiry Date | Quantity Representation | Repeat Dispensing Allowed | RD 1st Issue Expiry | RD Subsequent Expiry |
|--
| 1 | CD1 | Invalid to prescribe | Out of scope | N/A | N/A | N/A | N/A |
| 2 | CD2 | Hand signature or electronic signature | In scope | 28 days | Words and Figures | No | N/A | N/A |
| 3 | CD3 | Hand signature or electronic signature | In scope | 28 days | Words and Figures | No | N/A | N/A |
| 4 | CD4-1 CD4-2 | Hand signature or electronic signature | In scope | 28 days | Figures | Yes | 28 days | Up to 12 months
| 5 | CD5 | Hand signature or electronic signature | In scope | 6 Months | Figures | Yes | 6 months | Up to 12 months

It is a legal requirement to state the prescribed quantity as words in the `quantityWords` element of  {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-ControlledDrug}} 

```json
{
    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-ControlledDrug",
    "extension": [
        {
            "url": "quantityWords",
            "valueString": "twenty eight"
        },
        {
            "url": "schedule",
            "valueCoding": {
                "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-controlled-drug",
                "code": "CD2",
                "display": "Schedule 2"
            }
        }
    ]
}
```

<br>


<a name="dispensingInformation"></a>
### extension dispensingInformation

{{link:https://fhir.nhs.uk/StructureDefinition/Extension-EPS-DispensingInformation}} Should not be populated by prescribing systems. 

This extension is used in `continuous-repeat-dispensing` prescriptions sent by EPS to dispensing systems to convey information on prior dispensed medications.

```json
"extension":  [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-DispensingInformation",
                    "extension":  [
                        {
                            "url": "dispenseStatus",
                            "valueCoding": {
                                "system": "https://fhir.nhs.uk/CodeSystem/medicationdispense-type",
                                "code": "0001",
                                "display": "Item fully dispensed"
                            }
                        },
                        {
                            "url": "dateLastDispensed",
                            "valueDateTime": "2018-04-22T09:57:03+00:00"
                        }
                    ]
                }
            ],
```

<br>

<a name="identifier"></a>
### identifier <a href="#identifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Each MedicationRequest **MUST** be identified by an Universal Unique Identifiers (UUIDs) with a system of `https://fhir.nhs.uk/Id/prescription-order-item-number`

UUID example (for illustration purposes only);

**a54219b8-f741-4c47-b662-e4f8dfa49ab6**

This is contained in the extension {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-GroupIdentifier}}

```json
 "identifier":  [
    {
        "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
        "value": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
    }
]
```

<br>

<a name="status"></a>
### status <a href="#status" title="link to here" class="self-link"><i class="bi-link"></i></a> 

A code specifying the current state of the order. Generally, this will be active or completed state. 

| code | Definition |
|--
| active | The prescription is 'actionable', but not all actions that are implied by it have occurred yet. It has not been dispensed or filled. |
| cancelled | The prescription is to be cancelled or it has been cancelled been withdrawn before any administrations have occurred. Prescriptions in the process of being cancelled will be regarded as active until all actions are complete. |
| stopped | 

<br>

<a name="statusReason"></a>
### statusReason <a href="#statusReason" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This is generally only used for "exception" statuses such as "suspended" or "cancelled". It is the clinical status reason for the cancellation. It is a code from {{pagelink:DM-MedicationRequest-Status-Reason}}, the administrative status is captured in `extension(statusHistory)`

This is mandatory for 'prescription-order-update' messages.

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

<a name="intent"></a>
### intent

Indicates the type of order. A code specifying the current state of the order. Generally, this will be active or completed state. 

| code | display | courseOfTherapyType | Definition |
|--
| order | Order | acute | The request represents a request/demand and authorization for action |
| original-order | Original Order | continuous-repeat-dispensing instalment-dispensing | The request represents the original authorization for the medication request. |
| reflex-order |Reflex Order | continuous-repeat-dispensing | The request represents an automatically generated supplemental authorization (by EPS) for action based on a parent authorization together with initial results of the action taken against that parent authorization. |
| instance-order | Instance Order | instalment-dispensing | The request represents an instance for the particular order. |
 

<a name="category"></a>
### Category <a href="#category" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Category code from {{pagelink:DM-MedicationRequest-Category}} is required. In primary care the code of `community` should be used. In secondary care the category will often match the Episode/Spell type.

| Code | System |	Display |
|--
| leave | https://fhir.nhs.uk/CodeSystem/medicationrequest-category |	Leave
|outpatient	| http://terminology.hl7.org/CodeSystem/medicationrequest-category |Outpatient
| discharge	| http://terminology.hl7.org/CodeSystem/medicationrequest-category | Discharge
| community	|http://terminology.hl7.org/CodeSystem/medicationrequest-category | Community
| inpatient	 |http://terminology.hl7.org/CodeSystem/medicationrequest-category | Inpatient |

```json
"category": [
    {
        "coding": [
            {
                "system": "http://terminology.hl7.org/CodeSystem/medicationrequest-category",
                "code": "outpatient",
                "display": "Outpatient"
            }
        ]
    }
],
```


<a name="medication"></a>
### medication[x] <a href="#medication" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Only Virtual Medical Products (VMP) and Actual Medical Products (AMP) can be used. The ValueSet for medication is {{pagelink:DM-MedicationRequest-Code}}

See also {{pagelink:Prescribing}}

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
                "code": "9207411000001106",
                "display": "Salbutamol 100micrograms/dose dry powder inhaler"
            }
        ]
    },
```

<br>

<a name="subject"></a>
### subject <a href="#subject" title="link to here" class="self-link"><i class="bi-link"></i></a> 

A resource reference to a Patient with a traced NHS Number is required, an untraced NHS Number MUST NOT be used. 

```json
 "subject": {
                    "type": "Patient",
                    "reference": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
                    "display": "Miss Bernie Kanfeld"
                }
```

<br>

<a name="requester"></a>
### Requester <a href="#requester" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The requester must contain a resource reference to the Practitioner who has electronically signed the prescription.

If the `requester` can not take responsibility for the prescription, i.e. they would not be the prescriber on the FP10. Then the <a href="#responsiblePractitioner">extension responsiblePractitioner</a> must be populated.

```json
"requester": {
    "reference": "urn:uuid:56166769-c1c4-4d07-afa8-132b5dfca666"
},
```

<br/>

<a name="basedOn"></a>
### basedOn <a href="#basedOn" title="link to here" class="self-link"><i class="bi-link"></i></a>

This MUST be populated for `continuous-repeat-dispensing` issues where intent=`reflex-order`, i.e. the issues sent from EPS to pharmacists.
It is recommended this is populated for `continuous` issues and this should reference the original order.

Example for a `reflex-order` (continuous-repeat-dispensing): 

```json
 "basedOn": [
        {
            "extension": [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
                    "extension": [
                        {
                            "url": "numberOfRepeatsAllowed",
                            "valueUnsignedInt": 6
                        }
                    ]
                }
            ],
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "A7B86F8D-1D59-FC28-E050-D20AE3A215F0"
            }
        }
    ]
```

Example for a `instance-order` (continuous). Note this references an example MedicationRequest from GP Connect:

```json
 "basedOn": [
        {
            "extension": [
                {
                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation",
                    "extension": [
                        {
                            "url": "numberOfRepeatsAllowed",
                            "valueUnsignedInt": 5
                        }
                    ]
                }
            ],
            "identifier": {
                "system": "https://provider.nhs.uk/data-identifier",
                "value": "53426283749629"
            }
        }
    ]
```

<br/>

<a name="groupIdentifier"></a>
### groupIdentifier (Short Form Prescription ID) <a href="#groupIdentifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The purpose of the Short Form Prescription ID is to identify the prescription during its lifecycle within the Spine (i.e. prescribe, dispense & claim). The prescription UUID is retained to provide the link through to the Spine medication record within the PSIS and must be included as the first identifier within the prescription message.
The format of the Short Form Prescription ID is as follows;

`<RandomNumber>-<PracticeODSCode/ClinicODSCode>-<PracticeSequence/ClinicSequence><CheckDigit>`

Where;

`<RandomNumber>` is a locally generated random number each time a Prescription ID is generated of length 6 hexadecimal characters.

`<PracticeODSCode/ClinicODSCode>` is the unique ODS code for the practice or clinic code (aka cost centre) as defined within the Spine SDS of length 6 characters. Where the prescriber ODS code is shorter than 6 characters it must be zero-padded up to six characters from the start of the ODS code, e.g. “0A1B2C”.

`<PracticeSequence/ClinicSequence>` is an incremental sequence number starting from 00000 that is reset after FFFFF back to zero of length 5 hexadecimal characters. For systems that support multiple practices or clinics, a sequence number per practice/clinic is required. This is to ensure uniqueness of prescriptions within the Spine EPS component during the prescription lifecycle.

`<CheckDigit>` is calculated on the entire ID using the ISO/IEC 7064:2003 MOD 37-2 standard. The check digit algorithm is identical to that using for EPS Release 1.

Note. Hyphens are always included to separate the ID into 3 blocks of 6 characters.

Note. The implementation of the MOD 37-2 standard uses a “+” character for char 36 opposed to a “*” character.

Short Form Prescription ID example (for illustration purposes only);

**83C40E-A23856-00123W**

```json
"groupIdentifier": {
    ...
    "system": "https://fhir.nhs.uk/Id/prescription-order-number",
    "value": "DC2C66-A1B2C3-23407B"
},
```

<br>

### Universal Unique Identifiers (UUIDs) (groupIdentifier.extension (PrescriptionOrderUUID))

When UUIDs are used within HL7 messages they must be represented in an upper case human-readable hexadecimal format where hyphen separators are used as per the example below and as defined by the ‘datatype’ schema within the DMS.

UUID example (for illustration purposes only);

**34026084-A445-84AD-2D01-97D69ED25865**

This is contained in the extension {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-GroupIdentifier}}

```json
"groupIdentifier": {
    "extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionId",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription",
                "value": "ad945a29-85f8-439a-b590-6789719adc16"
            }
        }
    ],
    "system": "https://fhir.nhs.uk/Id/prescription-order-number",
    "value": "DC2C66-A1B2C3-23407B"
},
```

<br>

<a name="courseOfTherapyType"></a>
### courseOfTherapyType (Prescription Therapy Type) <a href="#courseOfTherapyType" title="link to here" class="self-link"><i class="bi-link"></i></a> 

See {{pagelink:prescribingmodels}} for more details.

A single Code from {{pagelink: DM-MedicationRequest-Course-of-Therapy}} valueset <br> In exceptional cases where for legacy data there is no prescriptionType recorded in the system then this MUST be populated with the text ‘No information available’. 
 
The  {{link:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-PrescriptionType}} **MUST NOT** be used with EPS (if used it will be ignored).  
A conversion table (ConceptMap) from the old CodeSystem is provided here {{pagelink:ukcore-prescriptiontypetor4prescriptiontherapytypemap}}

```json
"courseOfTherapyType": {
  "coding":  [
      {
          "system": "http://terminology.hl7.org/CodeSystem/medicationrequest-course-of-therapy",
          "code": "acute",
          "display": "Short course (acute) therapy"
      }
  ]
},
```

<a name="note"></a>
### Dispensing note (note)

Clinical information relating to a prescribed medication item that cannot be conveyed within dosage instructions is populated within `note` field.

Examples of dispensing notes are:

- To explain changes in dosage, for example, “Dosage has been increased on advice of the hospital”.
- "Tell patient to stop their statin whilst on this anitbiotic"
- "hospital consultant has confirmed dual treatment"

One scenario where `note` must be populated is when the current prescribed medication item is the last authorised repeat of that medication within a repeat prescribing cycle. Appropriate text, such as “Last authorised repeat” must be included within the `note` to inform the dispenser and to allow the dispenser to communicate to the patient or patient representative. Note that for repeat dispensing, the ‘numberOfRepeatPrescriptionsIssued’ element also conveys this information.

```json
"note": [
    {
      "text": "Tell patient to stop their statin whilst on this anitbiotic"
    }
  ],
```

<a name="dosageInstruction"></a>
### Dose Syntax (dosageInstruction) <a href="#dosageInstruction" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The content of the `dosageInstruction` should follow guidance in [Dosage Structure Overview](https://developer.nhs.uk/apis/dose-syntax-implementation/dosage-overview.html). (Note this is based on CareConnect STU3 but the guidance is still valid in UKCore R4)

`dosageInstruction.text` **MUST** be supplied and is a human readable version of the structured dose as would be printed on a paper prescription. The prescriber is required to enter a medication item dosage. The use of a generic default value, for example “Use as directed”, if a value is not entered, is not acceptable from a clinical perspective.

The prescriber is required to enter a medication item dosage. The use of a generic default value, for example “Use as directed”, if a value is not entered, is not acceptable from a clinical perspective. The user must be asked to select a dosage instruction from a pick list, type by hand or have the system populate with a valid and clinically safe dosage instruction relevant to the prescribed medication or clinical circumstances.

As per BNF guidelines, the dosage must be presented to the user without abbreviation although it may be entered and stored within the PMR in an abbreviated form. Within HL7 messaging, the dosage instruction must be represented without abbreviation.



```json
"dosageInstruction": [
   {
        "text": "10 milligram, Inject, Subcutaneous route, once weekly",
        "timing": {
            "repeat": {
                "boundsDuration": {
                    "value": 10,
                    "unit": "day",
                     "system": "http://unitsofmeasure.org",
                     "code": "d"
                },
                 "frequency": 5,
                 "period": 1,
                "periodUnit": "d"
             }
        },
        "route": {
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "34206005",
                    "display": "Subcutaneous route"
                }
            ]
        },
        "method": {
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "422145002",
                    "display": "Inject"
                }
            ]
        },
        "doseAndRate": [
            {
                "doseQuantity": {
                    "value": 10,
                    "unit": "milligram",
                    "system": "http://unitsofmeasure.org",
                    "code": "mg"
                }
            }
        ]
    }
]

```

#### patient infomation

These sections **MUST** be used only be used to pass notes regarding the prescription to the pharmacist or patient. Lists of repeat medications and general practice notifications to the patient **SHOULD** be recorded in [NHSDigital-CommunicationRequest](https://simplifier.net/guide/nhsdigital/NHSDigital-CommunicationRequest) resource.

Patient instructions for taking the drug are contained with in the `patientInstruction` and `additionalInstruction` as per the guidance in [Dosage Structure Overview](https://developer.nhs.uk/apis/dose-syntax-implementation/dosage-overview.html)

```json
"dosageInstruction": [
    {
        "text": "10 milligram, Inject, Subcutaneous route, once weekly",
        "additionalInstruction": [
            "coding": [
                {
                    "system": "http://snomed.info/sct",
                    "code": "421769005",
                    "display": "Follow directions"
                }
            ],
        ],
        "patientInstruction": "As directed"
    }
]
```

<br>

<a name="dispenseRequest"></a>
### dispenseRequest  <a href="#dispenseRequest" title="link to here" class="self-link"><i class="bi-link"></i></a> 

<br>

<a name="expectedSupplyDuration"></a>
<a name="validityPeriod"></a>
#### Days Supply (dispenseRequest.expectedSupplyDuration and dispenseRequest.validityPeriod) <a href="#validityPeriod" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The `expectedSupplyDuration` entity is required for repeat dispensing (repeatable) prescriptions only.

The `validityPeriod` attribute defines the validity period for the prescription authorisation. This period must start (the `validityPeriod.start`) at the date of prescribing and cannot exceed 12 months (the `validityPeriod.end`). Typically, most repeatable prescriptions will be authorised for a validity period of either 6 or 12 months.

```json
"dispenseRequest": {
          "validityPeriod": {
            "start": "2020-06-10",
            "end": "2020-12-07"
          },
          ...
      }
```


The `expectedSupplyDuration` element defines the expected duration, in days, of each issue of the prescription. A default value of 28 can be used which must be amendable by the prescriber when required. The value must be an integer value greater than zero. A sensible upper limit validation should be included within the System. If this value is omitted, the Spine will assume a value of 28.

```json
"dispenseRequest": {
          ...
          "expectedSupplyDuration": {
            "value": 28,
            "unit": "days",
            "system": "http://unitsofmeasure.org",
            "code": "d"
          }
      }
```

<br>

<a name="numberOfRepeatsAllowed"></a>
### dispenseRequest.numberOfRepeatsAllowed <a href="#numberOfRepeatsAllowed" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The number of repeat issues authorised if specified. <br> <b>MUST</b> be present where a `continuous` or `continuous-repeat-dispensing` is authorised for a defined number of issues. <br> <b>MUST</b> NOT be specified where the number of repeat issues has not been defined. Therefore, the numberOfRepeats allowed is the total number of allowed issues. See also <a href="#repeatInformation">extension repeatInformation</a>

For `continuous` orders and `continuous-repeat-dispensing` with intent=`reflex-order` (i.e., orders sent from EPS to pharmacists) this <b>MUST</b> be zero. The `numberOfRepeatsAllowed` in the extension to `basedOn` can be used to convey this information to inform patients that they need to re-order the medication. 

Example for a `continuous` issue:

```json

"dispenseRequest": {
        "numberOfRepeatsAllowed": 0
    }

```

Example for a `continuous-repeat-dispensing` issue with intent of `original-order`:

```json

"dispenseRequest": {
        "numberOfRepeatsAllowed": 6
    }

```

<br>

<a name="performer"></a>
#### Nominated Pharmacy and Dispensing Site Preference (dispenseRequest.performer) <a href="#performer" title="link to here" class="self-link"><i class="bi-link"></i></a> 

For non token based prescriptions the destination pharmacy **MUST** be recorded in the *dispenseRequest.performer.identifier* and a identifier reference (not a resource reference) with an ANANA/ODS Code **MUST** used. 

The extension {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType}} **MUST** be present 
and the code must be sourced from the {{pagelink:DM-Performer-Site-Type}}

Patients pharmacy preferences may be sourced from PDS {{pagelink: DispensingContractorsandNomination}}

Patients pharmacy preferences may be overriden by an 'one-off pharmacy nomination' by populating the *dispenseRequest.performer.identifier* with the ODS/ANANA code of the destination pharmacy.

```json
"dispenseRequest": {
        "extension":  [
            {
                "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType",
                "valueCoding": {
                    "system": "https://fhir.nhs.uk/CodeSystem/dispensing-site-preference",
                    "code": "0004"
                }
            },
        ],
        "performer": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "FX748"
            }
        },
```

<br>

<a name="substitution"></a>
#### substitution <a href="#substitution" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Within UK healthcare, substitution is not the norm and so this element will normally be set to a default of `false`.

Substitution being set to false is a mandatory requirement for EPS.

```json

"substitution": {
        "allowedBoolean": false
    }

```


<a name="search"></a>
## Search Parameters

<!--
@```
from CapabilityStatement
where url='https://fhir.nhs.uk/CapabilityStatement/apim-medicines-conformance' 
for rest.resource(where type = 'MedicationRequest').searchParam 
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
authoredon 
    </td>
    <td>
  date
    </td>
     <td>
Return prescriptions written on this date
    </td>
    <td>
SHOULD
    </td>
    <td>
MedicationRequest.authoredOn
    </td>
   </tr>  
    <tr>
    <td>
 code
    </td>
    <td>
 token
    </td>
     <td>
Return prescriptions of this medication code
    </td>
    <td>
SHOULD
    </td>
    <td>
(MedicationRequest.medication as CodeableConcept)
    </td>
   </tr> 
    <tr>
    <td>
group-identifier 
    </td>
    <td>
  token
    </td>
     <td>
Returns dispenses with this external group identifier (EPS prescription short form id)
    </td>
    <td>
MAY
    </td>
    <td>
MedicationRequest.groupdIdentifier
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
MedicationRequest.identifier
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
MedicationRequest.patient
(Patient)
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
Status of the prescription
    </td>
    <td>
SHOULD
    </td>
    <td>
MedicationRequest.status
    </td>
   </tr>  
   </tbody>
</table>

<br> 

Additional parameters can be on <a href="https://www.hl7.org/fhir/medicationrequest.html#search" target="_blank">MedicationRequest - Search Parameters</a>

<br>

<a name="mandatorysearch"></a>
### Mandatory Search Parameters

#### patient:identifier

**SHALL** support searching using the `patient:identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?patient:identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationRequest?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|9876543210`

Return all MedicationRequest resources for Patients with a NHS Number of 9876543210

#### status + patient:identifier

**SHALL** support searching using the combination of the `patient:identifier` and `status` search parameters:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?patient.identifier={system|}[code]&status=[code]
</div>

Example:

`GET [baseUrl]/MedicationRequest?patient:identifier=9876543210&status=active`

Return all MedicationRequest resources with a status of active and Patient with an identifier code of 9876543210.

<br>

<a name="optionalsearch"></a>
### Optional Search Parameters

#### authoredon + patient:identifier

**SHOULD** support searching using the combination of the `patient:identifier` and `authoredon` search parameters
- including support for these date comparators: gt,lt,ge,le
- including optional support for composite AND search on date (e.g.date=[date]&date=[date]]&...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?patient:identifier={system|}[code]&authoredon=[date]
</div>

Example:

`GET [baseUrl]/MedicationRequest?patient:identifier=9876543210&authoredon=ge2010-01-01&authoredon=le2011-12-31`

Return all MedicationRequest resources that have a authoredon greater than or equal to 1st Jan 2010, a date less than or equal to 31st Dec 2011 and Patient with an identifier code of 9876543210.

#### code + patient:identifier

**MAY** support searching using the combination of the `patient:identifier` and `code` search parameters:
- including optional support for composite OR search on code (e.g. code={system|}[code],{system|}[code],...)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?patient:identifier={system|}[code]&code={system|}|[code]
</div>

See reference for details on this parameter.

`GET [baseUrl]/MedicationRequest?patient:identifier=9876543210&code=9207411000001106`

Return all MedicationRequest resources that have a medication code (e.g. dm+d or SNOMED CT) with code of 9207411000001106 and Patient with an identifier code of 9876543210.

#### identifier

**MAY** support searching using the `identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationRequest?identifier=https://fhir.nhs.uk/Id/prescription-order-item-number|4509B70D-D8B8-EA03-1105-64557CB54A29`

#### group-identifier

**MAY** support searching using the `group-identifier` search parameter:

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
GET [baseUrl]/MedicationRequest?group-identifier={system|}[code]
</div>

Example:

`GET [baseUrl]/MedicationRequest?group-identifier=https://fhir.nhs.uk/Id/prescription-order-number|DC2C66-A1B2C3-23407B`



