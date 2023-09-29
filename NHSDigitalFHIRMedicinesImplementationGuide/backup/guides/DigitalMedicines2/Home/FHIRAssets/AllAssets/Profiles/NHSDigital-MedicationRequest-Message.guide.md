## {{page-title}}

| Profile url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message) |

This is a EPS NextGen constraint to enforce referenced resources are present in a FHIR Bundle.

See {{pagelink:NHSDigital-MedicationRequest-duplicate-3}} for full details on the resource profile.

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation" class="active">
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
        <div id="Profile" role="tabpanel" class="tab-pane">
            <br />
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane active">
         <br />
         Differential from {{link:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest}} <br>
            <br />
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
{{dict:  https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Message, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
         
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



| | |
|----|----|
|Element Id|MedicationRequest|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|

<br/>

 #### Definition

 An order or request for both supply of the medication and the instructions for administration of the medication to a patient. The resource is called "MedicationRequest" rather than "MedicationPrescription" or "MedicationOrder" to generalize the use across inpatient and outpatient settings, including care plans, etc., and to harmonize with workflow patterns.

 #### Constraints 

- **eps-1** (*ERROR*) medication[x] - Only one of medicationReference or medicationCodeableConcept should be provided
- **eps-cd1** (*ERROR*) Extension(controlledDrug) - For schedule 2 or 3 Controlled Drugs, the quantity must be expressed in words
- **eps-5** (*ERROR*) Extension(responsiblePractitioner) - An identifier or resource reference must be provided
- **eps-6** (*ERROR*) Extension repeatInformation is required for continuous, continuous-repeat-dispensing and instalment-dispensing MedicationRequests. It is not required for actue MedicationRequests
- **eps-7** (*WARNING*) For continuous-repeat-dispensing intent must be reflex-order or original-order
- **eps-8** (*ERROR*) For instalment-dispensing intent must be instance-order or original-order
- **eps-9** (*WARNING*) dispenseRequest.numberOfRepeatsAllowed should be populated for continuous, continuous-repeat-dispensing and instalment-dispensing MedicationRequests.
- **eps-10** (*ERROR*) For continuous-repeat-dispensing (intent=reflex-order) basedOn must be populated
- **eps-11** (*ERROR*) For continuous-repeat-dispensing (intent=reflex-order) or continous orders, numberOfRepeatsAllowed must be empty or equal to 0
- **eps-12** (*WARNING*) For continuous issues basedOn should be populated
- **eps-13** (*ERROR*) Extension repeatInformation.numberOfPrescriptionsIssued should not be present for continuous-repeat-dispensing that are not intent=reflex-order
- **eps-14** (*ERROR*) Extension repeatInformation.numberOfPrescriptionsIssued should be present for continuous-repeat-dispensing that have intent=reflex-order
- **eps-15** (*WARNING*) Extension repeatInformation.numberOfPrescriptionsIssued is recommend to be present for continuous issues
- **eps-16** (*ERROR*) Extension repeatInformation.numberOfPrescriptionsIssued should not be present for acute issues


- <a href="#extension:medicationRepeatInformation">extension:medicationRepeatInformation</a>
- <a href="#extension:responsiblePractitioner">extension:responsiblePractitioner</a>
- <a href="#extension:prescriptionEndorsement">extension:prescriptionEndorsement</a>
- <a href="#extension:prescriptionTaskStatusReason">extension:prescriptionTaskStatusReason</a>
- <a href="#extension:NHSBSAprescriptionType">extension:NHSBSAprescriptionType</a>
- <a href="#extension:controlledDrug">extension:controlledDrug</a>
- <a href="#extension:dispensingInformation">extension:dispensingInformation</a>
- <a href="#identifier">identifier</a>
- <a href="#identifier:prescriptionOrderItem">identifier:prescriptionOrderItem</a>
- <a href="#identifier:prescriptionOrderItem.system">identifier:prescriptionOrderItem.system</a>
- <a href="#status">status</a>
- <a href="#statusReason">statusReason</a>
- <a href="#category">category</a>
- <a href="#category.coding:patientClassFHIR">category.coding:patientClassFHIR</a>
- <a href="#category.coding:patientClassFHIR.system">category.coding:patientClassFHIR.system</a>
- <a href="#category.coding:patientClassUK">category.coding:patientClassUK</a>
- <a href="#category.coding:patientClassUK.system">category.coding:patientClassUK.system</a>
- <a href="#medication[x]">medication[x]</a>
- <a href="#subject">subject</a>
- <a href="#subject.identifier.system">subject.identifier.system</a>
- <a href="#authoredOn">authoredOn</a>
- <a href="#requester">requester</a>
- <a href="#basedOn">basedOn</a>
- <a href="#groupIdentifier">groupIdentifier</a>
- <a href="#groupIdentifier.extension:PrescriptionOrderUUID.url">groupIdentifier.extension:PrescriptionOrderUUID.url</a>
- <a href="#groupIdentifier.extension:PrescriptionOrderUUID.value[x].system">groupIdentifier.extension:PrescriptionOrderUUID.value[x].system</a>
- <a href="#groupIdentifier.system">groupIdentifier.system</a>
- <a href="#courseOfTherapyType">courseOfTherapyType</a>
- <a href="#note">note</a>
- <a href="#dosageInstruction">dosageInstruction</a>
- <a href="#dosageInstruction.additionalInstruction">dosageInstruction.additionalInstruction</a>
- <a href="#dosageInstruction.patientInstruction">dosageInstruction.patientInstruction</a>
- <a href="#dispenseRequest">dispenseRequest</a>
- <a href="#dispenseRequest.extension:performerSiteType">dispenseRequest.extension:performerSiteType</a>
- <a href="#dispenseRequest.validityPeriod">dispenseRequest.validityPeriod</a>
- <a href="#dispenseRequest.numberOfRepeatsAllowed">dispenseRequest.numberOfRepeatsAllowed</a>
- <a href="#dispenseRequest.quantity">dispenseRequest.quantity</a>
- <a href="#dispenseRequest.expectedSupplyDuration">dispenseRequest.expectedSupplyDuration</a>
- <a href="#dispenseRequest.expectedSupplyDuration.code">dispenseRequest.expectedSupplyDuration.code</a>
- <a href="#dispenseRequest.performer">dispenseRequest.performer</a>
- <a href="#dispenseRequest.performer.identifier.system">dispenseRequest.performer.identifier.system</a>
- <a href="#substitution">substitution</a>

<a name="extension:medicationRepeatInformation"></a>
 ## extension:medicationRepeatInformation

| | |
|----|----|
|Element Id|MedicationRequest.extension:medicationRepeatInformation|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|medicationRepeatInformation|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionUKCoreMedicationRepeatInformation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation))|

<br/>

 #### Definition

 This extension <b>MUST</b> be present for  `continuous` and `continuous-repeat-dispensing` therapy types. 

| Field | Description |
|---|---|
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

<a name="extension:responsiblePractitioner"></a>
 ## extension:responsiblePractitioner

| | |
|----|----|
|Element Id|MedicationRequest.extension:responsiblePractitioner|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|responsiblePractitioner|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionDMResponsiblePractitioner](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-ResponsiblePractitioner))|

<br/>

 #### Definition

 Must only be populated if the  `requester` can not be responsible for the prescription, i.e. they would not be named as the prescriber on the FP10.

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

<a name="extension:prescriptionEndorsement"></a>
 ## extension:prescriptionEndorsement

| | |
|----|----|
|Element Id|MedicationRequest.extension:prescriptionEndorsement|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionEndorsement|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionPrescriptionEndorsement](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement))|

<br/>

 #### Definition

 The codes are contained in the valueset

| Code | Display |
|---|---|
| CC |  Contraceptive |
| FS |  Sexual Health| 
| ACBS |  Advisory Committee on Borderline Substances. Part XV Drug Tariff | 
| SLS |  Selected List Scheme. Part XVIIIB Drug Tariff | 
| AF |  Food replacement/food supplement products|

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

<a name="extension:prescriptionTaskStatusReason"></a>
 ## extension:prescriptionTaskStatusReason

| | |
|----|----|
|Element Id|MedicationRequest.extension:prescriptionTaskStatusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionTaskStatusReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionDMPrescriptionStatusHistory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionStatusHistory))|

<br/>

 #### Definition

 The status history within EPS is primarily a technical Status and the statusReason will reflect current clinical status of the order.

<a name="extension:NHSBSAprescriptionType"></a>
 ## extension:NHSBSAprescriptionType

| | |
|----|----|
|Element Id|MedicationRequest.extension:NHSBSAprescriptionType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|NHSBSAprescriptionType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([Extension NHS BSA prescriptionType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionType))|

<br/>

 #### Definition

 The vocabulary for the ‘PrescriptionType’ vocabulary is defined within the NHSBSA Overprint Specification. 

The System must populate the ‘PrescriptionType’ attribute for the appropriate combination of prescriber and care setting. Retired codes within this vocabulary must not be used

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

<a name="extension:controlledDrug"></a>
 ## extension:controlledDrug

| | |
|----|----|
|Element Id|MedicationRequest.extension:controlledDrug|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|controlledDrug|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionDMControlledDrug](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-ControlledDrug))|

<br/>

 #### Definition

 The table below summarises the EPS requirements for the CD schedules. The terms “Hand signature” and “Electronic signature” expressed in the table are shortened references to the legal definition of signature requirements within government legislation.

| Sch. | Code | Signing Legal Requirement | EPS Scope | Expiry Date | Quantity Representation | Repeat Dispensing Allowed | RD 1st Issue Expiry | RD Subsequent Expiry |
|---|---|---|---|---|---|---|---|---|
| 1 | CD1 | Invalid to prescribe | Out of scope | N/A | N/A | N/A | N/A ||
| 2 | CD2 | Hand signature or electronic signature | In scope | 28 days | Words and Figures | No | N/A | N/A ||
| 3 | CD3 | Hand signature or electronic signature | In scope | 28 days | Words and Figures | No | N/A | N/A ||
| 4 | CD4-1 CD4-2 | Hand signature or electronic signature | In scope | 28 days | Figures | Yes | 28 days | Up to 12 months |
| 5 | CD5 | Hand signature or electronic signature | In scope | 6 Months | Figures | Yes | 6 months | Up to 12 months |

It is a legal requirement to state the prescribed quantity as words in the `quantityWords`

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

<a name="extension:dispensingInformation"></a>
 ## extension:dispensingInformation

| | |
|----|----|
|Element Id|MedicationRequest.extension:dispensingInformation|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|dispensingInformation|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSDispensingInformation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-DispensingInformation))|

<br/>

 #### Definition

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

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|MedicationRequest.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 UUID example (for illustration purposes only);

a54219b8-f741-4c47-b662-e4f8dfa49ab6

```json
 "identifier":  [
    {
        "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
        "value": "a54219b8-f741-4c47-b662-e4f8dfa49ab6"
    }
]
```

 #### Comment

 This is a business identifier, not a resource identifier.

<a name="identifier:prescriptionOrderItem"></a>
 ## identifier:prescriptionOrderItem

| | |
|----|----|
|Element Id|MedicationRequest.identifier:prescriptionOrderItem|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionOrderItem|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 Unique Id of the MedicationRequest within EPS

 #### Comment

 This is a business identifier, not a resource identifier.

<a name="identifier:prescriptionOrderItem.system"></a>
 ## identifier:prescriptionOrderItem.system

| | |
|----|----|
|Element Id|MedicationRequest.identifier:prescriptionOrderItem.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/prescription-order-item-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|MedicationRequest.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[medicationrequest Status](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/ValueSet/medicationrequest-status&#124;4.0.1) (Required) <br/>A coded concept specifying the state of the prescribing event. Describes the lifecycle of the prescription. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A code specifying the current state of the order. Generally, this will be active or completed state. 

| code | Definition |
|--|--|
| active | The prescription is 'actionable', but not all actions that are implied by it have occurred yet. It has not been dispensed or filled. |
| cancelled | The prescription is to be cancelled or it has been cancelled been withdrawn before any administrations have occurred. Prescriptions in the process of being cancelled will be regarded as active until all actions are complete. |
| stopped | Actions implied by the prescription are to be permanently halted, before all of the administrations occurred. This should not be used if the original order was entered in error|
|completed|All actions that are implied by the prescription have occurred.|

 #### Comment

 This element is labeled as a modifier because the status contains codes that mark the resource as not currently valid.

<a name="statusReason"></a>
 ## statusReason

| | |
|----|----|
|Element Id|MedicationRequest.statusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationRequestStatusReason](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationrequest-status-reason) (Required)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 This is generally only used for exception statuses such as `suspended` or `cancelled`. It is the clinical status reason for the cancellation.

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

 #### Comment

 This is generally only used for "exception" statuses such as "suspended" or "cancelled". The reason why the MedicationRequest was created at all is captured in reasonCode, not here.

<a name="category"></a>
 ## category

| | |
|----|----|
|Element Id|MedicationRequest.category|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreMedicationRequestCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationRequestCategory) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 In primary care the code of `community` should be used. In secondary care the category will often match the Episode/Spell type.

| Code | System | Display |
|---|---|
| leave | https://fhir.nhs.uk/CodeSystem/medicationrequest-category | Leave |
|outpatient | http://terminology.hl7.org/CodeSystem/medicationrequest-category |Outpatient |
| discharge | http://terminology.hl7.org/CodeSystem/medicationrequest-category | Discharge |
| community |http://terminology.hl7.org/CodeSystem/medicationrequest-category | Community |
| inpatient  |http://terminology.hl7.org/CodeSystem/medicationrequest-category | Inpatient |

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

 #### Comment

 The category can be used to include where the medication is expected to be consumed or other types of requests.

<a name="category.coding:patientClassFHIR"></a>
 ## category.coding:patientClassFHIR

| | |
|----|----|
|Element Id|MedicationRequest.category.coding:patientClassFHIR|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationRequestCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationrequest-category) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|patientClassFHIR|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="category.coding:patientClassFHIR.system"></a>
 ## category.coding:patientClassFHIR.system

| | |
|----|----|
|Element Id|MedicationRequest.category.coding:patientClassFHIR.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://terminology.hl7.org/CodeSystem/medicationrequest-category|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="category.coding:patientClassUK"></a>
 ## category.coding:patientClassUK

| | |
|----|----|
|Element Id|MedicationRequest.category.coding:patientClassUK|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationRequestCategory](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationrequest-category) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|patientClassUK|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="category.coding:patientClassUK.system"></a>
 ## category.coding:patientClassUK.system

| | |
|----|----|
|Element Id|MedicationRequest.category.coding:patientClassUK.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/medicationrequest-category|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="medication[x]"></a>
 ## medication[x]

| | |
|----|----|
|Element Id|MedicationRequest.medication[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[UKCoreMedicationCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationCode) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)([NHSDigitalMedicationRequestCodeableConcept](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-CodeableConcept))[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalMedicationRequestMedication](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Medication))<br/> [Aggregation - bundled](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 Only Virtual Medical Products (VMP) and Actual Medical Products (AMP) can be used.

 #### Comment

 Any code from the SnomedCT UK DMD subset for VMP, AMP and VTM concepts

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

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|MedicationRequest.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)<br/> [Aggregation - bundled](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 A resource reference to a Patient with a traced NHS Number is required, an untraced NHS Number **MUST NOT** be used.

```json
 "subject": {
                    "type": "Patient",
                    "reference": "urn:uuid:bde9eba6-079f-4210-8108-6ea8db58de8c",
                    "display": "Miss Bernie Kanfeld"
                }
```

 #### Comment

 The subject on a medication request is mandatory.  For the secondary use case where the actual subject is not provided, there still must be an anonymized subject specified.

 #### Constraints 

- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="subject.identifier.system"></a>
 ## subject.identifier.system

| | |
|----|----|
|Element Id|MedicationRequest.subject.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhs-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="authoredOn"></a>
 ## authoredOn

| | |
|----|----|
|Element Id|MedicationRequest.authoredOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The date (and perhaps time) when the prescription was initially written or authored on.

<a name="requester"></a>
 ## requester

| | |
|----|----|
|Element Id|MedicationRequest.requester|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRoleFull](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-Full))<br/> [Aggregation - bundled](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 The requester must contain a resource reference to the Practitioner who has electronically signed the prescription.

If the `requester` can not take responsibility for the prescription, i.e. they would not be the prescriber on the FP10. Then the **extension responsiblePractitioner** must be populated.

```json
"requester": {
    "reference": "urn:uuid:56166769-c1c4-4d07-afa8-132b5dfca666"
},
```

 #### Constraints 

- **eps-3** (*ERROR*) requester - An identifier reference plus a display name or resource reference must be provided

<a name="basedOn"></a>
 ## basedOn

| | |
|----|----|
|Element Id|MedicationRequest.basedOn|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([DomainResource](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/DomainResource) [MedicationRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/MedicationRequest))|

<br/>

 #### Definition

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

<a name="groupIdentifier"></a>
 ## groupIdentifier

| | |
|----|----|
|Element Id|MedicationRequest.groupIdentifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

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

 #### Requirements

 Requests are linked either by a "basedOn" relationship (i.e. one request is fulfilling another) or by having a common requisition. Requests that are part of the same requisition are generally treated independently from the perspective of changing their state or maintaining them after initial creation.

 #### Comment

 ITK HL7v3 Mapping = The groupIdentifier is equivalent to ParentPrescription.id (prescription-order-number). The extension is used to carry the ParentPrescription.id (UUID).

<a name="groupIdentifier.extension:PrescriptionOrderUUID.url"></a>
 ## groupIdentifier.extension:PrescriptionOrderUUID.url

| | |
|----|----|
|Element Id|MedicationRequest.groupIdentifier.extension:PrescriptionOrderUUID.url|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionId|
|[type](https://www.hl7.org/fhir/datatypes.html)|[http://hl7.org/fhirpath/System.String](https://www.hl7.org/fhir/datatypes.html#http://hl7.org/fhirpath/System.String)|

<br/>

 #### Definition

 Source of the definition for the extension code - a logical name or a URL.

 #### Comment

 The definition may point directly to a computable or human-readable definition of the extensibility codes, or it may be a logical URI as declared in some other specification. The definition SHALL be a URI for the Structure Definition defining the extension.

<a name="groupIdentifier.extension:PrescriptionOrderUUID.value[x].system"></a>
 ## groupIdentifier.extension:PrescriptionOrderUUID.value[x].system

| | |
|----|----|
|Element Id|MedicationRequest.groupIdentifier.extension:PrescriptionOrderUUID.value[x].system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/prescription|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="groupIdentifier.system"></a>
 ## groupIdentifier.system

| | |
|----|----|
|Element Id|MedicationRequest.groupIdentifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/prescription-order-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="courseOfTherapyType"></a>
 ## courseOfTherapyType

| | |
|----|----|
|Element Id|MedicationRequest.courseOfTherapyType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationRequestCourseOfTherapyCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationrequest-course-of-therapy) (Required)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The description of the overall pattern of the administration of the medication to the patient.
Required for prescription-order

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

 #### Comment

 The type of prescription e.g. acute, continuous, etc. Was extension in STU3 https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-PrescriptionType-1 and Digital Medicine uses international codes, so continuous in place of repeat.

<a name="note"></a>
 ## note

| | |
|----|----|
|Element Id|MedicationRequest.note|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Annotation](https://www.hl7.org/fhir/datatypes.html#Annotation)|

<br/>

 #### Definition

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
 ## dosageInstruction

| | |
|----|----|
|Element Id|MedicationRequest.dosageInstruction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Dosage](https://www.hl7.org/fhir/datatypes.html#Dosage)([NHSDigitalDosage](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Dosage))|

<br/>

 #### Definition

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

 #### Comment

 There are examples where a medication request may include the option of an oral dose or an Intravenous or Intramuscular dose.  For example, "Ondansetron 8mg orally or IV twice a day as needed for nausea" or "Compazine® (prochlorperazine) 5-10mg PO or 25mg PR bid prn nausea or vomiting".  In these cases, two medication requests would be created that could be grouped together.  The decision on which dose and route of administration to use is based on the patient's condition at the time the dose is needed.

<a name="dosageInstruction.additionalInstruction"></a>
 ## dosageInstruction.additionalInstruction

| | |
|----|----|
|Element Id|MedicationRequest.dosageInstruction.additionalInstruction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[SNOMEDCTAdditionalDosageInstructions](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/ValueSet/additional-instruction-codes) (Example) <br/>A coded concept identifying additional instructions such as "take with water" or "avoid operating heavy machinery". |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

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

 #### Requirements

 Additional instruction is intended to be coded, but where no code exists, the element could include text.  For example, "Swallow with plenty of water" which might or might not be coded.

 #### Comment

 Information about administration or preparation of the medication (e.g. "infuse as rapidly as possibly via intraperitoneal port" or "immediately following drug x") should be populated in dosage.text.

<a name="dosageInstruction.patientInstruction"></a>
 ## dosageInstruction.patientInstruction

| | |
|----|----|
|Element Id|MedicationRequest.dosageInstruction.patientInstruction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

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

<a name="dispenseRequest"></a>
 ## dispenseRequest

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Indicates the specific details for the dispense or medication supply part of a medication request (also known as a Medication Prescription or Medication Order).  Note that this information is not always sent with the order.  There may be in some settings (e.g. hospitals) institutional or system support for completing the dispense details in the pharmacy department.

<a name="dispenseRequest.extension:performerSiteType"></a>
 ## dispenseRequest.extension:performerSiteType

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.extension:performerSiteType|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|performerSiteType|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionperformerSiteType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType))|

<br/>

 #### Definition

 Used to indicate type of pharmacist

<a name="dispenseRequest.validityPeriod"></a>
 ## dispenseRequest.validityPeriod

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.validityPeriod|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Period](https://www.hl7.org/fhir/datatypes.html#Period)|

<br/>

 #### Definition

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

 #### Requirements

 Indicates when the Prescription becomes valid, and when it ceases to be a dispensable Prescription.

 #### Comment

 It reflects the prescribers' perspective for the validity of the prescription. Dispenses must not be made against the prescription outside of this period. The lower-bound of the Dispensing Window signifies the earliest date that the prescription can be filled for the first time. If an upper-bound is not specified then the Prescription is open-ended or will default to a stale-date based on regulations.

<a name="dispenseRequest.numberOfRepeatsAllowed"></a>
 ## dispenseRequest.numberOfRepeatsAllowed

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.numberOfRepeatsAllowed|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[unsignedInt](https://www.hl7.org/fhir/datatypes.html#unsignedInt)|

<br/>

 #### Definition

 The number of repeat issues authorised if specified. <br> <b>MUST</b> be present where a `continuous` or `continuous-repeat-dispensing` is authorised for a defined number of issues. <br> <b>MUST</b> NOT be specified where the number of repeat issues has not been defined. Therefore, the numberOfRepeats allowed is the total number of allowed issues. See also <a href="#repeatInformation">extension repeatInformation</a>

For `continuous` orders and `continuous-repeat-dispensing` with intent=`reflex-order` (i.e., orders sent from EPS to pharmacists) this <b>MUST</b> be zero. The `numberOfRepeatsAllowed` in the extension to `basedOn` can be used to convey this information to inform patients that they need to re-order the medication.

 #### Comment

 If displaying "number of authorized fills", add 1 to this number.

<a name="dispenseRequest.quantity"></a>
 ## dispenseRequest.quantity

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.quantity|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([SimpleQuantity](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity))|

<br/>

 #### Definition

 The amount that is to be dispensed for one fill.

<a name="dispenseRequest.expectedSupplyDuration"></a>
 ## dispenseRequest.expectedSupplyDuration

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.expectedSupplyDuration|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Duration](https://www.hl7.org/fhir/datatypes.html#Duration)|

<br/>

 #### Definition

 The `expectedSupplyDuration` entity is required for repeat dispensing (repeatable) prescriptions only.

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

 #### Comment

 In some situations, this attribute may be used instead of quantity to identify the amount supplied by how long it is expected to last, rather than the physical quantity issued, e.g. 90 days supply of medication (based on an ordered dosage). When possible, it is always better to specify quantity, as this tends to be more precise. expectedSupplyDuration will always be an estimate that can be influenced by external factors.

<a name="dispenseRequest.expectedSupplyDuration.code"></a>
 ## dispenseRequest.expectedSupplyDuration.code

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.expectedSupplyDuration.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|d|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A computer processable form of the unit in some unit representation system.

 #### Requirements

 Need a computable form of the unit that is fixed across all forms. UCUM provides this for quantities, but SNOMED CT provides many units of interest.

 #### Comment

 The preferred system is UCUM, but SNOMED CT can also be used (for customary units) or ISO 4217 for currency.  The context of use may additionally require a code from a particular system.

<a name="dispenseRequest.performer"></a>
 ## dispenseRequest.performer

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.performer|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalOrganization](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4.test@2.5.3-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Organization))|

<br/>

 #### Definition

 For non token based prescriptions the destination pharmacy **MUST** be recorded in the *dispenseRequest.performer.identifier* and a identifier reference (not a resource reference) with an ANANA/ODS Code **MUST** used. 

The extension https://fhir.nhs.uk/StructureDefinition/Extension-DM-PerformerSiteType **MUST** be present.

Patients pharmacy preferences may be sourced from PDS.

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

<a name="dispenseRequest.performer.identifier.system"></a>
 ## dispenseRequest.performer.identifier.system

| | |
|----|----|
|Element Id|MedicationRequest.dispenseRequest.performer.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/ods-organization-code|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 #### Requirements

 There are many sets  of identifiers.  To perform matching of two identifiers, we need to know what set we're dealing with. The system identifies a particular set of unique identifiers.

 #### Comment

 Identifier.system is always case sensitive.

<a name="substitution"></a>
 ## substitution

| | |
|----|----|
|Element Id|MedicationRequest.substitution|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 Within UK healthcare, substitution is not the norm and so this element will normally be set to a default of `false`.

Substitution being set to false is a mandatory requirement for EPS..

Substituition is a mandatory requirement for EPS.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important Note:</h4>
Within UK healthcare, substitution is not the norm so the international FHIR definition where "_If nothing is specified substitution may be done._" does not align with UK healthcare prescribing best practice.<br/>
<p>It could be unwise to assume all UK implementations will prevent substitution if not explicitly stated, especially if the same clinical system has been previously implemented outside the UK. <br/></p>
<p>UK Core has profiled this element as MANDATORY and MUST have a default boolean value of <code>false</code> to denote substitution is not allowed.</p>
</div>
<h3 id="allowing-substitution">Allowing substitution</h3>
<p>Where substitution to be be allowed, set to <code>true</code>. The inclusion of the coded reason is optional as the valueset defined in FHIR is of limited benefit to UK healthcare.</p>

```json

"substitution": {
        "allowedBoolean": false
    }

```