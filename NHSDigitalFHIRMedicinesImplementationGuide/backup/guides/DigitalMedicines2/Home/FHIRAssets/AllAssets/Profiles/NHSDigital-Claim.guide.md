### NHSDigital-Claim

| Profile url | FHIR Module | Normative Status |
|-|-|-|
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim) | | trial-use |


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
          {{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim, snapshot}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree:https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim, diff}}
        </div>
<div id="Examples"  class="tab-pane">

- {{pagelink:claimmappedfromv3-duplicate-2 }}
- {{pagelink:claim-update-duplicate-2}}  
- {{pagelink:claimexample2-duplicate-2}}

</div>
   <div id="Constraints" role="tabpanel" class="tab-pane">
<br />
@```
from StructureDefinition
where url='https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim'
for differential.element.constraint
select key, human, severity, expression
```
</div>

</div>

---

<br/>


 #### Definition

 A provider issued list of professional services and products which have been provided, or are to be provided, to a patient which is sent to an insurer for reimbursement.

 #### Comment

 The Claim resource fulfills three information request requirements: Claim - a request for adjudication for reimbursement for products and/or services provided; Preauthorization - a request to authorize the future provision of products and/or services including an anticipated adjudication; and, Predetermination - a request for a non-bind adjudication of possible future products and/or services.


- <a href="#extension:replacementOf">extension:replacementOf</a>
- <a href="#extension:agent">extension:agent</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#type">type</a>
- <a href="#type.coding.system">type.coding.system</a>
- <a href="#type.coding.code">type.coding.code</a>
- <a href="#use">use</a>
- <a href="#patient">patient</a>
- <a href="#patient.identifier.system">patient.identifier.system</a>
- <a href="#created">created</a>
- <a href="#provider">provider</a>
- <a href="#priority">priority</a>
- <a href="#priority.coding.system">priority.coding.system</a>
- <a href="#priority.coding.code">priority.coding.code</a>
- <a href="#prescription">prescription</a>
- <a href="#prescription.identifier.system">prescription.identifier.system</a>
- <a href="#payee">payee</a>
- <a href="#payee.type.coding.system">payee.type.coding.system</a>
- <a href="#payee.type.coding.code">payee.type.coding.code</a>
- <a href="#payee.type.coding.display">payee.type.coding.display</a>
- <a href="#payee.party.identifier.system">payee.party.identifier.system</a>
- <a href="#insurance">insurance</a>
- <a href="#insurance.coverage.identifier.system">insurance.coverage.identifier.system</a>
- <a href="#insurance.coverage.identifier.value">insurance.coverage.identifier.value</a>
- <a href="#item">item</a>
- <a href="#item.extension:prescriptionStatus">item.extension:prescriptionStatus</a>
- <a href="#item.extension:prescriptionStatusReason">item.extension:prescriptionStatusReason</a>
- <a href="#item.sequence">item.sequence</a>
- <a href="#item.productOrService.coding.system">item.productOrService.coding.system</a>
- <a href="#item.productOrService.coding.code">item.productOrService.coding.code</a>
- <a href="#item.productOrService.coding.display">item.productOrService.coding.display</a>
- <a href="#item.programCode">item.programCode</a>
- <a href="#item.programCode:exemptionEvidence">item.programCode:exemptionEvidence</a>
- <a href="#item.programCode:exemptionEvidence.coding.system">item.programCode:exemptionEvidence.coding.system</a>
- <a href="#item.programCode:prescriptionChargeExemption">item.programCode:prescriptionChargeExemption</a>
- <a href="#item.programCode:prescriptionChargeExemption.coding.system">item.programCode:prescriptionChargeExemption.coding.system</a>
- <a href="#item.detail">item.detail</a>
- <a href="#item.detail.extension:medicationRequest">item.detail.extension:medicationRequest</a>
- <a href="#item.detail.extension:sequenceIdentifier">item.detail.extension:sequenceIdentifier</a>
- <a href="#item.detail.sequence">item.detail.sequence</a>
- <a href="#item.detail.productOrService">item.detail.productOrService</a>
- <a href="#item.detail.modifier">item.detail.modifier</a>
- <a href="#item.detail.programCode">item.detail.programCode</a>
- <a href="#item.detail.programCode.coding">item.detail.programCode.coding</a>
- <a href="#item.detail.programCode:prescriptionCharge">item.detail.programCode:prescriptionCharge</a>
- <a href="#item.detail.programCode:prescriptionCharge.coding.system">item.detail.programCode:prescriptionCharge.coding.system</a>
- <a href="#item.detail.programCode:dispensingEndorsement">item.detail.programCode:dispensingEndorsement</a>
- <a href="#item.detail.programCode:dispensingEndorsement.coding.system">item.detail.programCode:dispensingEndorsement.coding.system</a>
- <a href="#item.detail.quantity">item.detail.quantity</a>
- <a href="#item.detail.subDetail">item.detail.subDetail</a>
- <a href="#item.detail.subDetail.sequence">item.detail.subDetail.sequence</a>
- <a href="#item.detail.subDetail.productOrService">item.detail.subDetail.productOrService</a>
- <a href="#item.detail.subDetail.quantity">item.detail.subDetail.quantity</a>

<a name="extension:replacementOf"></a>
 ## extension:replacementOf

| | |
|----|----|
|Element Id|Claim.extension:replacementOf|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|replacementOf|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionreplacementOf](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-replacementOf))|

<br/>

 #### Definition

 Used for replacement Claims, this should reference the Claim.identifier of the Claim being replaced.

```json

  "extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-replacementOf",
            "valueIdentifier": {
                "value": "46055273-3001-41bd-86a0-f8dba7f2161a"
            }
        }
    ],

```

<a name="extension:agent"></a>
 ## extension:agent

| | |
|----|----|
|Element Id|Claim.extension:agent|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|agent|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionProvenanceAgent](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-Provenance-agent))|

<br/>

 #### Definition

 The person submitting/authoring the Claim

```json

   "extension":  [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-Provenance-agent",
            "valueReference": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
                    "value": "884562163557"
                },
                "display": "dummy full name"
            }
        }
    ],
```

<a name="identifier"></a>
 ## identifier

| | |
|----|----|
|Element Id|Claim.identifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Identifier](https://www.hl7.org/fhir/datatypes.html#Identifier)|

<br/>

 #### Definition

 **MUST** be unique for each Claim. In EPS this must be a UUID with a system of `https://fhir.nhs.uk/Id/prescription-dispense-item-number`

```json

      "identifier":  [
          {
              "system": "https://fhir.nhs.uk/Id/prescription-dispense-item-number",
              "value": "4509B70D-D8B8-EA03-1105-64557CB54A29"
          }
      ],

```

 #### Requirements

 Allows claims to be distinguished and referenced.

<a name="status"></a>
 ## status

| | |
|----|----|
|Element Id|Claim.status|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[FinancialResourceStatusCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/fm-status&#124;4.0.1) (Required) <br/>A code specifying the state of the resource instance. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 For EPS the following **MUST** be used.

```json

      "status": "active",
      "type": {
          "coding":  [
              {
                   "system": "http://terminology.hl7.org/CodeSystem/claim-type",
                    "code": "pharmacy",
                    "display": "Pharmacy"
             }             
          ]
      },
      "use": "claim",

```

 #### Requirements

 Need to track the status of the resource as 'draft' resources may undergo further edits while 'active' resources are immutable and may only have their status changed to 'cancelled'.

 #### Comment

 This element is labeled as a modifier because the status contains codes that mark the resource as not currently valid.

<a name="type"></a>
 ## type

| | |
|----|----|
|Element Id|Claim.type|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ClaimTypeCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/claim-type) (Extensible) <br/>The type or discipline-style of the claim. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 The category of claim, e.g. oral, pharmacy, vision, institutional, professional.

 #### Requirements

 Claim type determine the general sets of business rules applied for information requirements and adjudication.

 #### Comment

 The majority of jurisdictions use: oral, pharmacy, vision, professional and institutional, or variants on those terms, as the general styles of claims. The valueset is extensible to accommodate other jurisdictional requirements.

<a name="type.coding.system"></a>
 ## type.coding.system

| | |
|----|----|
|Element Id|Claim.type.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://terminology.hl7.org/CodeSystem/claim-type|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="type.coding.code"></a>
 ## type.coding.code

| | |
|----|----|
|Element Id|Claim.type.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|pharmacy|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 #### Requirements

 Need to refer to a particular code in the system.

<a name="use"></a>
 ## use

| | |
|----|----|
|Element Id|Claim.use|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|claim|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[Use](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/claim-use&#124;4.0.1) (Required) <br/>The purpose of the Claim: predetermination, preauthorization, claim. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A code to indicate whether the nature of the request is: to request adjudication of products and services previously rendered; or requesting authorization and adjudication for provision in the future; or requesting the non-binding adjudication of the listed products and services which could be provided in the future.

 #### Requirements

 This element is required to understand the nature of the request for adjudication.

<a name="patient"></a>
 ## patient

| | |
|----|----|
|Element Id|Claim.patient|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([Patient](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/Patient))|

<br/>

 #### Definition

 **MUST** be an identifier reference using the Patients NHS Number.

```json

      "patient": {
          "identifier": {
              "system": "https://fhir.nhs.uk/Id/nhs-number",
              "value": "2300992742"
          }
      },

```

 #### Requirements

 The patient must be supplied to the insurer so that confirmation of coverage and service history may be considered as part of the authorization and/or adjudiction.

 #### Constraints 

- **patient-reference** (*ERROR*) An identifier reference or resource reference must be provided
- **patient-nhs** (*ERROR*) Supplied NHS Number is outside the English and Welsh NHS Number range or length of the number is wrong.

<a name="patient.identifier.system"></a>
 ## patient.identifier.system

| | |
|----|----|
|Element Id|Claim.patient.identifier.system|
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

<a name="created"></a>
 ## created

| | |
|----|----|
|Element Id|Claim.created|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[dateTime](https://www.hl7.org/fhir/datatypes.html#dateTime)|

<br/>

 #### Definition

 The date of the Claim

```json

  "created": "2004-09-16T16:30:00+00:00",

```

 #### Requirements

 Need to record a timestamp for use by both the recipient and the issuer.

 #### Comment

 This field is independent of the date of creation of the resource as it may reflect the creation date of a source document prior to digitization. Typically for claims all services must be completed as of this date.

<a name="provider"></a>
 ## provider

| | |
|----|----|
|Element Id|Claim.provider|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([NHSDigitalPractitionerRoleSDS](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-PractitionerRole-SDS))<br/> Aggregation - [contained](http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html)|

<br/>

 #### Definition

 The organisation responsible for the claim, this must be a reference to a contained PractitoinerRole

```json
 "provider": {
        "reference" : "#provider"
    },
```

The contained PractitionerRole

```json
{
    "resourceType": "Claim",
    "id": "258E153F-567B-4D60-B045-BA315A6B8DB0",
    "contained": [
  {
      "resourceType": "PractitionerRole",
      "id": "provider",
      "identifier": [
        {
          "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
          "value": "454567759542"
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
        "reference": "#organisation"
      },
      "telecom": [
        {
          "system": "phone",
          "use": "work",
          "value": "01234567890"
        }
      ]
    },
    {
      "resourceType": "Organization",
      "id": "organisation",
      "identifier": [
        {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "VNE51"
        }
      ],
      "address": [
        {
          "city": "West Yorkshire",
          "use": "work",
          "line": [
            "17 Austhorpe Road",
            "Crossgates",
            "Leeds"
          ],
          "postalCode": "LS15 8BA"
        }
      ],
      "active": true,
      "type": [
        {
          "coding": [
            {
              "system": "https://fhir.nhs.uk/CodeSystem/organisation-role",
              "code": "182",
              "display": "PHARMACY"
            }
          ]
        }
      ],
      "name": "The Simple Pharmacy",
      "telecom": [
        {
          "system": "phone",
          "use": "work",
          "value": "0113 3180277"
        }
      ]
    }        
    ],
```

 #### Comment

 Typically this field would be 1..1 where this party is responsible for the claim but not necessarily professionally responsible for the provision of the individual products and services listed below.
 
 GMC Reference Number **MUST NOT** be used as a Practitioner identifier

<a name="priority"></a>
 ## priority

| | |
|----|----|
|Element Id|Claim.priority|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ProcessPriorityCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/process-priority) (Example) <br/>The timeliness with which processing is required: stat, normal, deferred. |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Desired processing ugency. Fixed value.

```json
"priority": {
        "coding": [
            {
                "system": "http://terminology.hl7.org/CodeSystem/processpriority",
                "code": "normal"
            }
        ]
    }
```

 #### Requirements

 The provider may need to indicate their processing requirements so that the processor can indicate if they are unable to comply.

 #### Comment

 If a claim processor is unable to complete the processing as per the priority then they should generate and error and not process the request.

<a name="priority.coding.system"></a>
 ## priority.coding.system

| | |
|----|----|
|Element Id|Claim.priority.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://terminology.hl7.org/CodeSystem/processpriority|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="priority.coding.code"></a>
 ## priority.coding.code

| | |
|----|----|
|Element Id|Claim.priority.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|normal|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 #### Requirements

 Need to refer to a particular code in the system.

<a name="prescription"></a>
 ## prescription

| | |
|----|----|
|Element Id|Claim.prescription|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Reference](https://www.hl7.org/fhir/datatypes.html#Reference)([DeviceRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/DeviceRequest) [MedicationRequest](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/MedicationRequest) [VisionPrescription](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/VisionPrescription))|

<br/>

 #### Definition

 References to the original prescription, the `groupIdentifier` contains both the ShortForm prescription id and long form UUID variant. See [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest) for more details.

This MUST not be used to reference the MedicationRequest.

```json

"prescription": {
    "extension": [
        {
            "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-GroupIdentifier",
            "extension": [
                {
                    "url": "shortForm",
                    "valueIdentifier": {
                        "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                        "value": "82D996-C81010-11DB12"
                    }
                },
                {
                    "url": "UUID",
                    "valueIdentifier": {
                        "system": "https://fhir.nhs.uk/Id/prescription",
                        "value": "b2fc79f0-2793-4736-9b2d-0976c21e73a5"
                    }
                }
            ]
        }
    ]
},

```

 #### Requirements

 Required to authorize the dispensing of controlled substances and devices.

<a name="prescription.identifier.system"></a>
 ## prescription.identifier.system

| | |
|----|----|
|Element Id|Claim.prescription.identifier.system|
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

<a name="payee"></a>
 ## payee

| | |
|----|----|
|Element Id|Claim.payee|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 The recipient of benefits payable. This is the ODS Code of the Pharmacy (provider) making the Claim.

See provider for example of a contained Organization.

```json

"payee": {
    "type": {
        "coding": [
            {
                "system": "http://terminology.hl7.org/CodeSystem/payeetype",
                "value": "provider",
                "display": "Provider"
            }
        ]
    },
    "party": {
        "reference": "#organisation",
        "display": "The Simple Pharmacy"
    }
}
```

 #### Requirements

 The provider needs to specify who they wish to be reimbursed and the claims processor needs express who they will reimburse.

 #### Comment

 Often providers agree to receive the benefits payable to reduce the near-term costs to the patient. The insurer may decline to pay the provider and choose to pay the subscriber instead.

<a name="payee.type.coding.system"></a>
 ## payee.type.coding.system

| | |
|----|----|
|Element Id|Claim.payee.type.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://terminology.hl7.org/CodeSystem/payeetype|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="payee.type.coding.code"></a>
 ## payee.type.coding.code

| | |
|----|----|
|Element Id|Claim.payee.type.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|provider|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 #### Requirements

 Need to refer to a particular code in the system.

<a name="payee.type.coding.display"></a>
 ## payee.type.coding.display

| | |
|----|----|
|Element Id|Claim.payee.type.coding.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 A representation of the meaning of the code in the system, following the rules of the system.

 #### Requirements

 Need to be able to carry a human-readable meaning of the code for readers that do not know  the system.

<a name="payee.party.identifier.system"></a>
 ## payee.party.identifier.system

| | |
|----|----|
|Element Id|Claim.payee.party.identifier.system|
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

<a name="insurance"></a>
 ## insurance

| | |
|----|----|
|Element Id|Claim.insurance|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 For EPS this is the NHS Business Services Authority. The sequence value must always be 1.

```json

"insurance":  [
    {
        "sequence": 1,
        "focal": true,
        "coverage": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "T1450"
            },
            "display": "NHS BUSINESS SERVICES AUTHORITY"
        }
    }
],
```

 #### Requirements

 At least one insurer is required for a claim to be a claim.

 #### Comment

 All insurance coverages for the patient which may be applicable for reimbursement, of the products and services listed in the claim, are typically provided in the claim to allow insurers to confirm the ordering of the insurance coverages relative to local 'coordination of benefit' rules. One coverage (and only one) with 'focal=true' is to be used in the adjudication of this claim. Coverages appearing before the focal Coverage in the list, and where 'Coverage.subrogation=false', should provide a reference to the ClaimResponse containing the adjudication results of the prior claim.

<a name="insurance.coverage.identifier.system"></a>
 ## insurance.coverage.identifier.system

| | |
|----|----|
|Element Id|Claim.insurance.coverage.identifier.system|
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

<a name="insurance.coverage.identifier.value"></a>
 ## insurance.coverage.identifier.value

| | |
|----|----|
|Element Id|Claim.insurance.coverage.identifier.value|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 The portion of the identifier typically relevant to the user and which is unique within the context of the system.

 #### Comment

 If the value is a full URI, then the system SHALL be urn:ietf:rfc:3986.  The value's primary purpose is computational mapping.  As a result, it may be normalized for comparison purposes (e.g. removing non-significant whitespace, dashes, etc.)  A value formatted for human display can be conveyed using the [Rendered Value extension](http://hl7.org/fhir/R4/extension-rendered-value.html). Identifier.value is to be treated as case sensitive unless knowledge of the Identifier.system allows the processer to be confident that non-case-sensitive processing is safe.

<a name="item"></a>
 ## item

| | |
|----|----|
|Element Id|Claim.item|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 <table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="25%"></th>
     <th data-no-sort width="25%">item (prescription)</th>
     <th data-no-sort width="25%">detail (requested medication)</th>
     <th data-no-sort width="25%">subDetail (dispensed medication)</th>
   </tr>
 </thead>
 <tbody>
  <tr>
    <td>
    productOrService
    </td>
    <td>
    16076005 Prescription
    </td>
    <td>
    dm+d code of requested medication
    </td>
    <td>
    dm+d code of dispensed medication
    </td>
   </tr>
   <tr>
    <td>
    programCode
    </td>
    <td>
    exemptionEvidence
    prescriptionChargeExemption
    </td>
    <td>
    prescriptionCharge
    dispensingEndorsement
    additionalInstructions
    </td>
    <td>
    </td>
   </tr>
   <tr>
   <tr>
    <td>
    modifier
    </td>
    <td>
    </td>
    <td>
    MedicationDispenseType
    </td>
    <td>
    </td>
   </tr>
   <tr>
     <tr>
    <td>
    quantity
    </td>
    <td>
    </td>
    <td>
    MedicationRequest.quantity
    </td>
    <td>
    MedicationDispense.quantity
    </td>
   </tr>
   <tr>
   </tbody>
</table>

 #### Requirements

 The items to be processed for adjudication.

<a name="item.extension:prescriptionStatus"></a>
 ## item.extension:prescriptionStatus

| | |
|----|----|
|Element Id|Claim.item.extension:prescriptionStatus|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionStatus|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSTaskBusinessStatus](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus))|

<br/>

 #### Definition

 This will generally match the value of the last `dispense-notification` message.

This should match the `status` of the associated [NHSDigital-Task](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task)

```json

"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatus",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/CodeSystem/EPS-task-business-status",
            "code": "0006",
            "display": "Dispensed"
        }
    }
] 
 ```

<a name="item.extension:prescriptionStatusReason"></a>
 ## item.extension:prescriptionStatusReason

| | |
|----|----|
|Element Id|Claim.item.extension:prescriptionStatusReason|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionStatusReason|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionEPSTaskBusinessStatusReason](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatusReason))|

<br/>

 #### Definition

 Mandatory if the medication was not dispensed. 
This should match the `statusReason` of the associated [NHSDigital-Task](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-Task)

```json

"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-EPS-TaskBusinessStatusReason",
        "valueCoding": {
            "system": "https://fhir.nhs.uk/ValueSet/DM-medicationdispense-status-reason",
            "code": "0001",
            "display": "Not required as instructed by the patient"
        }
    }
],

```

<a name="item.sequence"></a>
 ## item.sequence

| | |
|----|----|
|Element Id|Claim.item.sequence|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[positiveInt](https://www.hl7.org/fhir/datatypes.html#positiveInt)|

<br/>

 #### Definition

 A number to uniquely identify item entries.

 #### Requirements

 Necessary to provide a mechanism to link to items from within the claim and within the adjudication details of the ClaimResponse.

<a name="item.productOrService.coding.system"></a>
 ## item.productOrService.coding.system

| | |
|----|----|
|Element Id|Claim.item.productOrService.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|http://snomed.info/sct|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="item.productOrService.coding.code"></a>
 ## item.productOrService.coding.code

| | |
|----|----|
|Element Id|Claim.item.productOrService.coding.code|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|16076005|
|[type](https://www.hl7.org/fhir/datatypes.html)|[code](https://www.hl7.org/fhir/datatypes.html#code)|

<br/>

 #### Definition

 A symbol in syntax defined by the system. The symbol may be a predefined code or an expression in a syntax defined by the coding system (e.g. post-coordination).

 #### Requirements

 Need to refer to a particular code in the system.

<a name="item.productOrService.coding.display"></a>
 ## item.productOrService.coding.display

| | |
|----|----|
|Element Id|Claim.item.productOrService.coding.display|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[string](https://www.hl7.org/fhir/datatypes.html#string)|

<br/>

 #### Definition

 A representation of the meaning of the code in the system, following the rules of the system.

 #### Requirements

 Need to be able to carry a human-readable meaning of the code for readers that do not know  the system.

<a name="item.programCode"></a>
 ## item.programCode

| | |
|----|----|
|Element Id|Claim.item.programCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ExampleProgramReasonCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/ex-program-code) (Example) <br/>Prescription Charge Exemption |
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *coding.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Exemption evidence - code to denote which evidence for exemption has been seen.

Prescription Charge Exemption - code to denote the exemption reason 
```json  

"programCode": [
    {
        "coding": [
              {
                "code": "0001",
                "system": "https://fhir.nhs.uk/CodeSystem/prescription-charge-exemption",
                "display": "Patient has paid appropriate charges"
              }
            ]
          },
          {
            "coding": [
              {
                "system": "https://fhir.nhs.uk/CodeSystem/DM-exemption-evidence",
                "code": "no-evidence-seen",
                "display": "No Evidence Seen"
              }
            ]
          }
        ]

```

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.programCode:exemptionEvidence"></a>
 ## item.programCode:exemptionEvidence

| | |
|----|----|
|Element Id|Claim.item.programCode:exemptionEvidence|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSBSAPrescriptionExemptionEvidence](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-vs-exemption-evidence) (Extensible)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|exemptionEvidence|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Identifies the program under which this may be recovered.

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.programCode:exemptionEvidence.coding.system"></a>
 ## item.programCode:exemptionEvidence.coding.system

| | |
|----|----|
|Element Id|Claim.item.programCode:exemptionEvidence.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/DM-exemption-evidence|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="item.programCode:prescriptionChargeExemption"></a>
 ## item.programCode:prescriptionChargeExemption

| | |
|----|----|
|Element Id|Claim.item.programCode:prescriptionChargeExemption|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[DMprescriptionchargeexemption](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-prescription-charge-exemption) (Required) <br/>Prescription Charge Exemption |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionChargeExemption|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Identifies the program under which this may be recovered.

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.programCode:prescriptionChargeExemption.coding.system"></a>
 ## item.programCode:prescriptionChargeExemption.coding.system

| | |
|----|----|
|Element Id|Claim.item.programCode:prescriptionChargeExemption.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/prescription-charge-exemption|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="item.detail"></a>
 ## item.detail

| | |
|----|----|
|Element Id|Claim.item.detail|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 A claim detail line. Relates to MedicationRequest

 #### Requirements

 The items to be processed for adjudication.

<a name="item.detail.extension:medicationRequest"></a>
 ## item.detail.extension:medicationRequest

| | |
|----|----|
|Element Id|Claim.item.detail.extension:medicationRequest|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|medicationRequest|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionClaimMedicationRequestReference](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-ClaimMedicationRequestReference))|

<br/>

 #### Definition

 This should match the `identifier` of the associated [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest)

```json

"extension":  [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-ClaimMedicationRequestReference",
        "valueReference": {
            "identifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "33560bee-bc0c-4e3b-a155-71591eee9ca5"
            }
        }
    }
],

```

<a name="item.detail.extension:sequenceIdentifier"></a>
 ## item.detail.extension:sequenceIdentifier

| | |
|----|----|
|Element Id|Claim.item.detail.extension:sequenceIdentifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|sequenceIdentifier|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Extension](https://www.hl7.org/fhir/datatypes.html#Extension)([ExtensionClaimSequenceIdentifier](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/StructureDefinition/Extension-ClaimSequenceIdentifier))|

<br/>

 #### Definition

 Optional Extension Element - found in all resources.

<a name="item.detail.sequence"></a>
 ## item.detail.sequence

| | |
|----|----|
|Element Id|Claim.item.detail.sequence|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[positiveInt](https://www.hl7.org/fhir/datatypes.html#positiveInt)|

<br/>

 #### Definition

 An integer to identify the item within the resource. Fixed value.

```json

"sequence": 1,

```

 #### Requirements

 Necessary to provide a mechanism to link to items from within the claim and within the adjudication details of the ClaimResponse.

<a name="item.detail.productOrService"></a>
 ## item.detail.productOrService

| | |
|----|----|
|Element Id|Claim.item.detail.productOrService|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[DMMedicationRequestCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-MedicationRequest-Code) (Required) <br/>DMD Medication Code |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 This should match the `medicationCodeableConcept` of the associated [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest)

```json

"productOrService": {
    "coding":  [
        {
            "system": "http://snomed.info/sct",
            "code": "322237000",
            "display": "Paracetamol 500mg soluble tablets"
        }
    ]
},

```

 #### Requirements

 Necessary to state what was provided or done.

 #### Comment

 If this is an actual service or product line, i.e. not a Group, then use code to indicate the Professional Service or Product supplied (e.g. CTP, HCPCS, USCLS, ICD10, NCPDP, DIN, RxNorm, ACHI, CCI). If a grouping item then use a group code to indicate the type of thing being grouped e.g. 'glasses' or 'compound'.

<a name="item.detail.modifier"></a>
 ## item.detail.modifier

| | |
|----|----|
|Element Id|Claim.item.detail.modifier|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[MedicationDispenseType](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-medicationdispense-type) (Required) <br/>MedicationDispense Type |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 If the code is `0002 - Item not dispensed` then the extension `prescriptionStatusReason` is required.

This should match the `type` of the last associated [NHSDigital-MedicationDispense](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense)

```json

"modifier":  [
    {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/medicationdispense-type",
                "code": "0001",
                "display": "Item fully dispensed"
            }
        ]
    }
],

```

 #### Requirements

 To support inclusion of the item for adjudication or to charge an elevated fee.

 #### Comment

 For example in Oral whether the treatment is cosmetic or associated with TMJ, or for Medical whether the treatment was outside the clinic or out of office hours.

<a name="item.detail.programCode"></a>
 ## item.detail.programCode

| | |
|----|----|
|Element Id|Claim.item.detail.programCode|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[ExampleProgramReasonCodes](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/ValueSet/ex-program-code) (Example) <br/>Program specific reason codes. |
|[Slicing](https://www.hl7.org/fhir/profiling.html#slicing)| *OPEN* discriminator -  *VALUE* *coding.system*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Dispensing Endorsement  - Details of the endorsement(s) to support the claim for this medication item. 

Charge Payment - Details on whether a prescription charge was paid for the medication treatment.

```json

"programCode":  [
    {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/DM-prescription-charge",
                "code": "paid-once",
                "display": "Paid Once"
            }
        ]
    },
    {
        "coding":  [
            {
                "system": "https://fhir.nhs.uk/CodeSystem/medicationdispense-endorsement",
                "code": "IP",
                "display": "Invoice Price"
            }
        ]
    }
],

```

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.detail.programCode.coding"></a>
 ## item.detail.programCode.coding

| | |
|----|----|
|Element Id|Claim.item.detail.programCode.coding|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Coding](https://www.hl7.org/fhir/datatypes.html#Coding)|

<br/>

 #### Definition

 A reference to a code defined by a terminology system.

 #### Requirements

 Allows for alternative encodings within a code system, and translations to other code systems.

 #### Comment

 Codes may be defined very casually in enumerations, or code lists, up to very formal definitions such as SNOMED CT - see the HL7 v3 Core Principles for more information.  Ordering of codings is undefined and SHALL NOT be used to infer meaning. Generally, at most only one of the coding values will be labeled as UserSelected = true.

<a name="item.detail.programCode:prescriptionCharge"></a>
 ## item.detail.programCode:prescriptionCharge

| | |
|----|----|
|Element Id|Claim.item.detail.programCode:prescriptionCharge|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSBSAPrescriptionCharge](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-vs-prescription-charge) (Required)|
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|prescriptionCharge|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Identifies the program under which this may be recovered.

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.detail.programCode:prescriptionCharge.coding.system"></a>
 ## item.detail.programCode:prescriptionCharge.coding.system

| | |
|----|----|
|Element Id|Claim.item.detail.programCode:prescriptionCharge.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/DM-prescription-charge|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="item.detail.programCode:dispensingEndorsement"></a>
 ## item.detail.programCode:dispensingEndorsement

| | |
|----|----|
|Element Id|Claim.item.detail.programCode:dispensingEndorsement|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[NHSBSADispensingEndorsement](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/DM-dispensing-endorsement) (Required) <br/>Program specific reason codes |
|[Slice Name](https://www.hl7.org/fhir/profiling.html#slicing)|dispensingEndorsement|
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 Identifies the program under which this may be recovered.

 #### Requirements

 Commonly used in in the identification of publicly provided program focused on population segments or disease classifications.

 #### Comment

 For example: Neonatal program, child dental program or drug users recovery program.

<a name="item.detail.programCode:dispensingEndorsement.coding.system"></a>
 ## item.detail.programCode:dispensingEndorsement.coding.system

| | |
|----|----|
|Element Id|Claim.item.detail.programCode:dispensingEndorsement.coding.system|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|Fixed Value|https://fhir.nhs.uk/CodeSystem/medicationdispense-endorsement|
|[type](https://www.hl7.org/fhir/datatypes.html)|[uri](https://www.hl7.org/fhir/datatypes.html#uri)|

<br/>

 #### Definition

 The identification of the code system that defines the meaning of the symbol in the code.

 #### Requirements

 Need to be unambiguous about the source of the definition of the symbol.

 #### Comment

 The URI may be an OID (urn:oid:...) or a UUID (urn:uuid:...).  OIDs and UUIDs SHALL be references to the HL7 OID registry. Otherwise, the URI should come from HL7's list of FHIR defined special URIs or it should reference to some definition that establishes the system clearly and unambiguously.

<a name="item.detail.quantity"></a>
 ## item.detail.quantity

| | |
|----|----|
|Element Id|Claim.item.detail.quantity|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([SimpleQuantity](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity))|

<br/>

 #### Definition

 This should match the `quantity` of the associated [NHSDigital-MedicationRequest](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest)

```json

"quantity": {
    "value": 200,
    "unit": "unit dose",
    "system": "http://snomed.info/sct",
    "code": "408102007"
},

```

 #### Requirements

 Required when the product or service code does not convey the quantity provided.

<a name="item.detail.subDetail"></a>
 ## item.detail.subDetail

| | |
|----|----|
|Element Id|Claim.item.detail.subDetail|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|0..*|
|[type](https://www.hl7.org/fhir/datatypes.html)|[BackboneElement](https://www.hl7.org/fhir/datatypes.html#BackboneElement)|

<br/>

 #### Definition

 subDetail is only present if the medication has been dispensed.

 #### Requirements

 The items to be processed for adjudication.

<a name="item.detail.subDetail.sequence"></a>
 ## item.detail.subDetail.sequence

| | |
|----|----|
|Element Id|Claim.item.detail.subDetail.sequence|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[positiveInt](https://www.hl7.org/fhir/datatypes.html#positiveInt)|

<br/>

 #### Definition

 An integer id for each medication dispense.

```json

"sequence": 1,


```

 #### Requirements

 Necessary to provide a mechanism to link to items from within the claim and within the adjudication details of the ClaimResponse.

<a name="item.detail.subDetail.productOrService"></a>
 ## item.detail.subDetail.productOrService

| | |
|----|----|
|Element Id|Claim.item.detail.subDetail.productOrService|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[Terminology Binding](https://www.hl7.org/fhir/terminologies.html)|[DMMedicationDispenseCode](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=https://fhir.nhs.uk/ValueSet/NHSDigital-MedicationDispense-Code) (Extensible) <br/>DMD Medication Code |
|[type](https://www.hl7.org/fhir/datatypes.html)|[CodeableConcept](https://www.hl7.org/fhir/datatypes.html#CodeableConcept)|

<br/>

 #### Definition

 This should match the `medicationCodeableConcept` of the associated [NHSDigital-MedicationDispense](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense)

```json

"productOrService": {
    "coding":  [
        {
            "system": "http://snomed.info/sct",
            "code": "3416211000001106",
            "display": "Salbutamol 100micrograms/dose inhaler (Sandoz Ltd) 200 dose"
        }
    ]
},

```

 #### Requirements

 Necessary to state what was provided or done.

 #### Comment

 If this is an actual service or product line, i.e. not a Group, then use code to indicate the Professional Service or Product supplied (e.g. CTP, HCPCS, USCLS, ICD10, NCPDP, DIN, RxNorm, ACHI, CCI). If a grouping item then use a group code to indicate the type of thing being grouped e.g. 'glasses' or 'compound'.

<a name="item.detail.subDetail.quantity"></a>
 ## item.detail.subDetail.quantity

| | |
|----|----|
|Element Id|Claim.item.detail.subDetail.quantity|
|[Cardinality](https://www.hl7.org/fhir/conformance-rules.html#cardinality)|1..1|
|[type](https://www.hl7.org/fhir/datatypes.html)|[Quantity](https://www.hl7.org/fhir/datatypes.html#Quantity)([SimpleQuantity](https://simplifier.net/resolve?target=simplifier&fhirVersion=R4&scope=uk.nhsdigital.medicines.r4@0.0.0-prerelease&canonical=http://hl7.org/fhir/StructureDefinition/SimpleQuantity))|

<br/>

 #### Definition

 This should match the `quantity` of the associated [NHSDigital-MedicationDispense](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical=https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationDispense)

```json

"quantity": {
    "value": 200,
    "unit": "unit dose",
    "system": "http://snomed.info/sct",
    "code": "408102007"
}

```

 #### Requirements

 Required when the product or service code does not convey the quantity provided.