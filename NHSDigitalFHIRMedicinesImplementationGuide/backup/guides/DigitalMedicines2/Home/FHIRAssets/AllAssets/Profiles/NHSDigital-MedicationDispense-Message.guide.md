## {{page-title}}

| Profile url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Message](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Message) |

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  >
            <a href="#Combined" role="tab" data-toggle="tab">Combined</a>
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
       
        <div id="Combined" role="tabpanel" class="tab-pane">
            <br>
            Combined with {{link:https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense}} <br><br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Message, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
            {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Message, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br>
            {{dict: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Message, hybrid}}
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

        </div>
    </div>
</div>



 ## extension

| | Description |
|----|----|
|Element Id|MedicationDispense.extension|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)|

 An Extension

 ## extension:prescriptionStatus

| | Description |
|----|----|
|Element Id|MedicationDispense.extension:prescriptionStatus|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus) )|

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

 ## extension:repeatInformation

| | Description |
|----|----|
|Element Id|MedicationDispense.extension:repeatInformation|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-RepeatInformation) )|

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

 ## identifier

| | Description |
|----|----|
|Element Id|MedicationDispense.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

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

 ## identifier.system

| | Description |
|----|----|
|Element Id|MedicationDispense.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 ## identifier.value

| | Description |
|----|----|
|Element Id|MedicationDispense.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 ## status

| | Description |
|----|----|
|Element Id|MedicationDispense.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[http://hl7.org/fhir/ValueSet/medicationdispense-status|4.0.1](https://simplifier.net/search?canonical=http://hl7.org/fhir/ValueSet/medicationdispense-status|4.0.1) (Required)A coded concept specifying the state of the dispense event. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

 The status of the individual medication item, this will normally indicate whether the medication has been picked up or not. 

| Code | Display | Definition |
|--|--|
| completed | Completed | The dispensed product has been picked up. |
| in-progress | In Progress | The dispensed product is ready for pickup. |

 ## statusReason[x].coding

| | Description |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

 A reference to a code defined by a terminology system.

 ## statusReason[x].coding.system

| | Description |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 The identification of the code system that defines the meaning of the symbol in the code.

 ## statusReason[x].coding.code

| | Description |
|----|----|
|Element Id|MedicationDispense.statusReason[x].coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 ## category.coding.system

| | Description |
|----|----|
|Element Id|MedicationDispense.category.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 The identification of the code system that defines the meaning of the symbol in the code.

 ## category.coding.code

| | Description |
|----|----|
|Element Id|MedicationDispense.category.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 ## medication[x]

| | Description |
|----|----|
|Element Id|MedicationDispense.medication[x]|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationCode](https://simplifier.net/search?canonical=https://fhir.hl7.org.uk/ValueSet/UKCore-MedicationCode) (Extensible)|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)([https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-CodeableConcept](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-CodeableConcept) )[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Medication](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense-Medication))|

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

 ## subject

| | Description |
|----|----|
|Element Id|MedicationDispense.subject|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Patient))|

 A reference to the patient via a traced NHS Number is required, an untraced NHS Number MUST NOT be used. This can be sent in two ways, first option is via a `identifier reference`. Only the NHS Number. Full example: {{pagelink: stdispenseevent-partial}}

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
Full example: {{pagelink: stdispenseevent-partialwithPatientResource}}
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

 ## subject.identifier.system

| | Description |
|----|----|
|Element Id|MedicationDispense.subject.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/Id/nhs-number|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 ## subject.identifier.value

| | Description |
|----|----|
|Element Id|MedicationDispense.subject.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 ## performer

| | Description |
|----|----|
|Element Id|MedicationDispense.performer|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

 The pharmacist and pharmacy MUST be present and MUST use `identifier references`. This means FHIR Practitioner, Organization and PractitionerRole resource are not included in the FHIR Message. Professional codes and ODS codes should be used instead. `sds-user-role-id` is permitted to identify a Practitioner(& Role) but professional codes are preferred to support wider NHS interoperability.


```json
 "performer": [
    {
        "actor": {
            "reference" : "#requester"
        }
    }
],
```

 ## performer.actor

| | Description |
|----|----|
|Element Id|MedicationDispense.performer.actor|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole))|

 The device, practitioner, etc. who performed the action.  It should be assumed that the actor is the dispenser of the medication.

 ## performer.actor.identifier.system

| | Description |
|----|----|
|Element Id|MedicationDispense.performer.actor.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 ## performer.actor.identifier.value

| | Description |
|----|----|
|Element Id|MedicationDispense.performer.actor.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 ## performer.actor.display

| | Description |
|----|----|
|Element Id|MedicationDispense.performer.actor.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 Plain text narrative that identifies the resource in addition to the resource reference.

 ## location.identifier.system

| | Description |
|----|----|
|Element Id|MedicationDispense.location.identifier.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 Establishes the namespace for the value - that is, a URL that describes a set values that are unique.

 ## location.identifier.value

| | Description |
|----|----|
|Element Id|MedicationDispense.location.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 ## location.display

| | Description |
|----|----|
|Element Id|MedicationDispense.location.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 Plain text narrative that identifies the resource in addition to the resource reference.

 ## authorizingPrescription

| | Description |
|----|----|
|Element Id|MedicationDispense.authorizingPrescription|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Minimal](https://simplifier.net/search?canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Minimal))|

 A reference to the contained `MedicationRequest`. 

```json
"authorizingPrescription": [
    {
        "reference": "#m1"
    }
]
```

 ## authorizingPrescription.reference

| | Description |
|----|----|
|Element Id|MedicationDispense.authorizingPrescription.reference|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 A reference to a location at which the other resource is found. The reference may be a relative reference, in which case it is relative to the service base URL, or an absolute URL that resolves to the location where the resource is found. The reference may be version specific or not. If the reference is not to a FHIR RESTful server, then it should be assumed to be version specific. Internal fragment references (start with '#') refer to contained resources.

 ## type

| | Description |
|----|----|
|Element Id|MedicationDispense.type|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[https://fhir.nhs.uk/ValueSet/DM-medicationdispense-type](https://simplifier.net/search?canonical=https://fhir.nhs.uk/ValueSet/DM-medicationdispense-type) (Required)A ValueSet to identify the type of medication item status. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

 Indicates the type of dispensing event that is performed. For example, Trial Fill, Completion of Trial, Partial Fill, Emergency Fill, Samples, etc.

 ## type.coding.system

| | Description |
|----|----|
|Element Id|MedicationDispense.type.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 The identification of the code system that defines the meaning of the symbol in the code.

 ## type.coding.code

| | Description |
|----|----|
|Element Id|MedicationDispense.type.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 ## quantity

| | Description |
|----|----|
|Element Id|MedicationDispense.quantity|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([http://hl7.org/fhir/StructureDefinition/SimpleQuantity](https://simplifier.net/search?canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity) )|

 The amount of medication that has been dispensed. Includes unit of measure.

 ## quantity.value

| | Description |
|----|----|
|Element Id|MedicationDispense.quantity.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[decimal](https://www.hl7.org/fhir/datatypes.html#decimal)|

 The value of the measured amount. The value includes an implicit precision in the presentation of the value.

 ## quantity.unit

| | Description |
|----|----|
|Element Id|MedicationDispense.quantity.unit|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 A human-readable form of the unit.

 ## quantity.system

| | Description |
|----|----|
|Element Id|MedicationDispense.quantity.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

 The identification of the system that provides the coded form of the unit.

 ## quantity.code

| | Description |
|----|----|
|Element Id|MedicationDispense.quantity.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

 A computer processable form of the unit in some unit representation system.

 ## daysSupply

| | Description |
|----|----|
|Element Id|MedicationDispense.daysSupply|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([http://hl7.org/fhir/StructureDefinition/SimpleQuantity](https://simplifier.net/search?canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity) )|

 The amount of medication expressed as a timing amount.

 ## whenHandedOver

| | Description |
|----|----|
|Element Id|MedicationDispense.whenHandedOver|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

 The time the dispensed product was provided to the patient or their representative.

 ## note.text

| | Description |
|----|----|
|Element Id|MedicationDispense.note.text|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[markdown](https://www.hl7.org/fhir/datatypes.html#markdown)|

 The text of the annotation in markdown format.

 ## dosageInstruction

| | Description |
|----|----|
|Element Id|MedicationDispense.dosageInstruction|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Dosage](https://www.hl7.org/fhir/datatypes.html#Dosage)|

 At present only the `text` element **MUST** be provided. It is recommended the guidance in [FHIR Dose Syntax Implementation Guidance](https://developer.nhs.uk/apis/dose-syntax-implementation-1-3-2-alpha/dosage-overview.html) is followed. 

Note the structure of this section is similar as the {{pagelink:NHSDigital-MedicationRequest-duplicate-3}} from the `prescription-order`.

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

 ## dosageInstruction.text

| | Description |
|----|----|
|Element Id|MedicationDispense.dosageInstruction.text|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

 Free text dosage instructions e.g. SIG.

 ## substitution.wasSubstituted

| | Description |
|----|----|
|Element Id|MedicationDispense.substitution.wasSubstituted|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[boolean](https://www.hl7.org/fhir/datatypes.html#boolean)|

 True if the dispenser dispensed a different drug or product from what was prescribed.