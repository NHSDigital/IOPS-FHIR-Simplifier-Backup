## NHSDigital-MedicationDispense

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense) | [Medicines]() | trial-use |


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
See examples in {{pagelink:index-duplicate-44}}
        </div>
    </div>
</div>



---

<br/>

 #### Definition

 Indicates that a medication product is to be or has been dispensed for a named person/patient.  This includes a description of the medication product (supply) provided and the instructions for administering the medication.  The medication dispense is the result of a pharmacy system responding to a medication order.

 #### Constraints 

- **mdd-1** (*ERROR*) whenHandedOver cannot be before whenPrepared


- <a href="#extension:prescriptionStatus">extension:prescriptionStatus</a>
- <a href="#extension:repeatInformation">extension:repeatInformation</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#statusReason[x]">statusReason[x]</a>
- <a href="#statusReason[x].coding:notDispensedStatusReason">statusReason[x].coding:notDispensedStatusReason</a>
- <a href="#statusReason[x].coding:notDispensedStatusReason.system">statusReason[x].coding:notDispensedStatusReason.system</a>
- <a href="#statusReason[x].coding:amendmentStatusReason">statusReason[x].coding:amendmentStatusReason</a>
- <a href="#statusReason[x].coding:amendmentStatusReason.system">statusReason[x].coding:amendmentStatusReason.system</a>
- <a href="#medication[x]">medication[x]</a>
- <a href="#subject">subject</a>
- <a href="#subject.identifier.system">subject.identifier.system</a>
- <a href="#performer">performer</a>
- <a href="#authorizingPrescription">authorizingPrescription</a>
- <a href="#type">type</a>
- <a href="#quantity">quantity</a>
- <a href="#daysSupply">daysSupply</a>
- <a href="#whenPrepared">whenPrepared</a>
- <a href="#whenHandedOver">whenHandedOver</a>
- <a href="#dosageInstruction">dosageInstruction</a>

<a name="extension:prescriptionStatus"></a>
 ## extension:prescriptionStatus

| | |
|----|----|
|Element Id|MedicationDispense.extension:prescriptionStatus|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionStatus|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSTaskBusinessStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus))|

<br/>

 #### Definition

 This is the overall status of the `prescription-order`, it is not the status of the individual prescription item. This is a code from {{pagelink:DM-Task-Status-Reason-duplicate-2}}, all prescription status reasons in a `dispense-notification` FHIR Message Bundle must be the same.

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

<a name="extension:repeatInformation"></a>
 ## extension:repeatInformation

| | |
|----|----|
|Element Id|MedicationDispense.extension:repeatInformation|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|repeatInformation|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSRepeatInformation](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation))|

<br/>

 #### Definition

 The extension is mandatory for `continuous` and `continuous-repeat-dispensing`. The following elements **MUST** be populated 

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

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|MedicationDispense.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

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

 #### Comment

 This is a business identifier, not a resource identifier.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|MedicationDispense.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationDispense Status Codes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/medicationdispense-status&#124;4.0.1) (Required) <br/>A coded concept specifying the state of the dispense event. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 The status of the individual medication item, this will normally indicate whether the medication has been picked up or not. 

| Code | Display | Definition |
|--|--|--|
| completed | Completed | The dispensed product has been picked up. |
| in-progress | In Progress | The dispensed product is ready for pickup. |


<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-Medicines-ImplementationGuide/master/Diagrams/medication-dispense-status-flow.png" width="100%" hieght="auto"/>

 #### Comment

 This element is labeled as a modifier because the status contains codes that mark the resource as not currently valid.

<a name="statusReason[x]"></a>
 ## statusReason[x]

| | |
|----|----|
|Element Id|MedicationDispense.statusReason[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationDispense Status Reason Codes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/medicationdispense-status-reason) (Example) <br/>A code describing why a dispense was not performed. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Indicates the reason why a dispense was not performed.

<a name="statusReason[x].coding:notDispensedStatusReason"></a>
 ## statusReason[x].coding:notDispensedStatusReason

| | |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding:notDispensedStatusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationDispenseStatusReason](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationdispense-status-reason) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|notDispensedStatusReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="statusReason[x].coding:notDispensedStatusReason.system"></a>
 ## statusReason[x].coding:notDispensedStatusReason.system

| | |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding:notDispensedStatusReason.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/medicationdispense-status-reason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="statusReason[x].coding:amendmentStatusReason"></a>
 ## statusReason[x].coding:amendmentStatusReason

| | |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding:amendmentStatusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[TaskReasonCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-task-reason-code) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|amendmentStatusReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="statusReason[x].coding:amendmentStatusReason.system"></a>
 ## statusReason[x].coding:amendmentStatusReason.system

| | |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding:amendmentStatusReason.system|
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

<a name="medication[x]"></a>
 ## medication[x]

| | |
|----|----|
|Element Id|MedicationDispense.medication[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSDigitalMedicationCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-MedicationCode) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)([NHSDigitalMedicationDispenseCodeableConcept](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-CodeableConcept))[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalMedicationDispenseMedication](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Medication))<br/> Aggregation - [bundled](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 Actual Medical Product Packs (AMPP) SHOULD be used. 
It is valid to include a FHIR Medication resource within the FHIR Message, this practice is discouraged to simplify handling of the event messages.

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

 #### Comment

 If only a code is specified, then it needs to be a code for a specific product. If more information is required, then the use of the medication resource is recommended.  For example, if you require form or lot number, then you must reference the Medication resource.

<a name="subject"></a>
 ## subject

| | |
|----|----|
|Element Id|MedicationDispense.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPatientPDS](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient-PDS))<br/> Aggregation - [referenced](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)<br/> Aggregation - [bundled](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 A reference to the patient via a traced NHS Number is required, an untraced NHS Number MUST NOT be used. This can be sent in two ways, first option is via a `identifier reference`. Only the NHS Number:

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

 #### Comment

 SubstanceAdministration->subject->Patient.

 #### Constraints 

- **eps-2** (*WARNING*) subject - An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="subject.identifier.system"></a>
 ## subject.identifier.system

| | |
|----|----|
|Element Id|MedicationDispense.subject.identifier.system|
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

<a name="performer"></a>
 ## performer

| | |
|----|----|
|Element Id|MedicationDispense.performer|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 The pharmacist and pharmacy MUST be present and MUST use `identifier references`. This means FHIR Practitioner, Organization and PractitionerRole resource are not included in the FHIR Message. Professional codes and ODS codes should be used instead. `sds-user-role-id` is permitted to identify a Practitioner(& Role) but professional codes are preferred to support wider NHS interoperability.

```json
 "performer": [
    {
        "actor": {
            "reference" : "#performer"
        }
    }
],
```

The contained PractitionerRole:

```json
{
    "resourceType": "MedicationDispense",
    "id": "06167339-9337-d030-0366-514a6a46da17",
    "contained": [
        {
                        "resourceType": "PractitionerRole",
                        "id": "performer",
                        "identifier": [
                            {
                                "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
                                "value": "741555508105"
                            }
                        ],
                        "code": [
                            {
                                "coding": [
                                    {
                                        "system": "https://fhir.nhs.uk/CodeSystem/NHSDigital-SDS-JobRoleCode",
                                        "code": "S0030:G0100:R0620"
                                    }
                                ]
                            }
                        ],
                        "practitioner": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/sds-user-id",
                                "value": "7654321"
                            },
                            "display": "Mr Peter Potion"
                        },
                        "organization": {
                            "reference": "urn:uuid:2bf9f37c-d88b-4f86-ad5f-373c1416e04b"
                        },
                        "telecom": [
                            {
                                "system": "phone",
                                "use": "work",
                                "value": "0532567890"
                            }
                        ]
                   }
    ],
```

<a name="authorizingPrescription"></a>
 ## authorizingPrescription

| | |
|----|----|
|Element Id|MedicationDispense.authorizingPrescription|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalMedicationRequestMinimal](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Minimal))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)<br/> Aggregation - [referenced](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 A reference to the `MedicationRequest`. 

```json
"authorizingPrescription": [
    {
        "reference": "#m1"
    }
]
```

When a MedicationDispesne is sent in a FHIR Message bundle, which is the case with EPS NextGen `dispense-notifications`, a contained MedicationRequest is required. 

This MedicationRequest **MUST** follow the rules in [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest) and it is strongly recommended to reuse the `MedicationRequest` received when the prescription was downloaded. 

For example:

```json 
{
                "resourceType": "MedicationDispense",
                "contained":  [
                    {
                        "resourceType": "MedicationRequest",
                        "id": "m1",
                        "identifier":  [
                            {
                                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                                "value": "299c610b-f4f1-4eac-a7d7-4fb6b0556e11"
                            }
                        ],
                        "status": "active",
                        "intent": "order",
                        "medicationCodeableConcept": {
                            "coding":  [
                                {
                                    "system": "http://snomed.info/sct",
                                    "code": "39720311000001101",
                                    "display": "Paracetamol 500mg soluble tablets"
                                }
                            ]
                        },
                        "subject": {
                            "identifier": {
                                "system": "https://fhir.nhs.uk/Id/nhs-number",
                                "value": "9876543210"
                            }
                        },
                        "groupIdentifier": {
                            "extension":  [
                                {
                                    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionId",
                                    "valueIdentifier": {
                                        "system": "https://fhir.nhs.uk/Id/prescription",
                                        "value": "b2fc79f0-2793-4736-9b2d-0976c21e73a5"
                                    }
                                }
                            ],
                            "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                            "value": "82D996-C81010-11DB12"
                        },
                        "dispenseRequest": {
                            "quantity": {
                                "value": 100,
                                "unit": "tablet",
                                "system": "http://snomed.info/sct",
                                "code": "732936001"
                            }
                        },
                        "substitution": {
                            "allowedBoolean": false
                        }
                    }
                ],
                "authorizingPrescription":  [
                    {
                        "reference": "#m1"
                    }
                ],
```

This is based on a `MedicationRequest` in this implementation guide.
The uuid resource references are not permitted and must be replaced with identifier references. E.g. in this section from the `$release` 

```json
        "subject": {
            "reference": "urn:uuid:78d3c2eb-009e-4ec8-a358-b042954aa9b2"
        },
        "authoredOn": "2020-12-21T18:15:29+00:00",
        "requester": {
            "reference": "urn:uuid:56166769-c1c4-4d07-afa8-132b5dfca666"
        },
```

The requester reference can be removed and the subject reference changed to use the Patient's NHSNumber e.g. 

```json
        "subject": {
            "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9876543210"
        }
    },
```

 #### Comment

 Maps to basedOn in Event logical model.

<a name="type"></a>
 ## type

| | |
|----|----|
|Element Id|MedicationDispense.type|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationDispenseType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationdispense-type) (Required) <br/>A ValueSet to identify the type of medication item status. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Indicates the type of dispensing event that is performed. For example, Trial Fill, Completion of Trial, Partial Fill, Emergency Fill, Samples, etc.

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

<a name="quantity"></a>
 ## quantity

| | |
|----|----|
|Element Id|MedicationDispense.quantity|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([SimpleQuantity](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity))|

<br/>

 #### Definition

 The amount of medication that has been dispensed. Includes unit of measure.

```json
"quantity": {
    "value": 28,
    "unit": "capsule",
    "system": "http://snomed.info/sct",
    "code": "3316911000001105"
}
```

If no actual quantity has been dispensed then use a value of zero.

<a name="daysSupply"></a>
 ## daysSupply

| | |
|----|----|
|Element Id|MedicationDispense.daysSupply|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([SimpleQuantity](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity))|

<br/>

 #### Definition

 The amount of medication expressed as a timing amount.

```json
"daysSupply": {
    "value": 7,
    "unit": "Day",
    "system": "http://unitsofmeasure.org",
    "code": "d"
}
```

<a name="whenPrepared"></a>
 ## whenPrepared

| | |
|----|----|
|Element Id|MedicationDispense.whenPrepared|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The time when the dispensed product was packaged and reviewed.

```json
"whenPrepared": "2004-09-16T16:30:00+00:00"
```

<a name="whenHandedOver"></a>
 ## whenHandedOver

| | |
|----|----|
|Element Id|MedicationDispense.whenHandedOver|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The time the dispensed product was provided to the patient or their representative.
In HL7 v3 this is: *The date and local time that the medication is issued by the dispenser*.

```json
"whenHandedOver": "2004-09-16T16:30:00+00:00"
```

<a name="dosageInstruction"></a>
 ## dosageInstruction

| | |
|----|----|
|Element Id|MedicationDispense.dosageInstruction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Dosage](https://www.hl7.org/fhir/datatypes.html#Dosage)([NHSDigitalDosage](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Dosage))|

<br/>

 #### Definition

 At present only the `text` element **MUST** be provided. It is recommended the guidance in [FHIR Dose Syntax Implementation Guidance](https://developer.nhs.uk/apis/dose-syntax-implementation-1-3-2-alpha/dosage-overview.html) is followed. 

Note the structure of this section is similar as the [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest) from the `prescription-order`.

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

 #### Comment

 When the dose or rate is intended to change over the entire administration period (e.g. Tapering dose prescriptions), multiple instances of dosage instructions will need to be supplied to convey the different doses/rates. The pharmacist reviews the medication order prior to dispense and updates the dosageInstruction based on the actual product being dispensed.