### NHSDigital-Claim

| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim](https://simplifier.net/guide/DigitalMedicines/DM-Claim) | 


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
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    <div class="tab-content snippet">
       
        <div id="Combined" role="tabpanel" class="tab-pane active">
            <br>
          <br><br>
          {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim, hybrid}}
        </div>
         <div id="Differential" role="tabpanel" class="tab-pane">
            <br>
         {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-Claim, diff}}
        </div>
<div id="Examples"  class="tab-pane">

- {{pagelink:claimmappedfromv3 }}
- {{pagelink:claim-update.md}}  
- {{pagelink:claimexample2.md}}

</div>
</div>

---

<br>

- <a href="#agent">extension agent</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status, type and use</a>
- <a href="#patient">patient</a>
- <a href="#created">created</a>
- <a href="#provider">provider</a>
- <a href="#priority">priority</a>
- <a href="#prescription">prescription</a>
- <a href="#payee">payee</a>
- <a href="#insurance">insurance</a>
- <a href="#itemoverview">item, detail and subDetail</a>
- <a href="#item">item</a>
  - <a href="#prescriptionStatus">extension prescriptionStatus</a>
  - <a href="#prescriptionStatusReason">extension prescriptionStatusReason</a>
  - <a href="#itemsequence">sequence</a>
  - <a href="#itemproductOrService">productOrService</a>
  - <a href="#itemprogramCode">programCode</a>
  - <a href="#detail">detail</a>
    - <a href="#detailsequenceIdentifier">extension sequenceIdentifier</a>
    - <a href="#detailmedicationRequest">extension medicationRequest</a>
    - <a href="#detailrepeatInformation">extension repeatInformation</a>
    - <a href="#detailproductOrService">productOrService</a>
    - <a href="#detailmodifier">modifier</a>
    - <a href="#detailquantity">quantity</a>
    - <a href="#detailprogramCode">programCode</a>
    - <a href="#subdetail">subDetail</a>
      - <a href="#subdetailsequence">sequence</a>
      - <a href="#subdetailproductOrService">productOrService</a>
      - <a href="#subdetailquantity">quantity</a>

<br>

<a name="agent"></a>
### extension agent <a href="#agent" title="link to here" class="self-link"><i class="bi-link"></i></a> 

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

````

<br>

<a name="identifier"></a>
### identifier <a href="#identifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

**MUST** be unique for each Claim. In EPS this must be a UUID with a system of `https://fhir.nhs.uk/Id/prescription-dispense-item-number`

```json

      "identifier":  [
          {
              "system": "https://fhir.nhs.uk/Id/prescription-dispense-item-number",
              "value": "4509B70D-D8B8-EA03-1105-64557CB54A29"
          }
      ],

````

<br>

<a name="status"></a>
### status, type and use <a href="#status" title="link to here" class="self-link"><i class="bi-link"></i></a> 

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

<br>

<a name="patient"></a>
### patient  <a href="#patient" title="link to here" class="self-link"><i class="bi-link"></i></a> 

**MUST** be an identifier reference using the Patients NHS Number.

```json

      "patient": {
          "identifier": {
              "system": "https://fhir.nhs.uk/Id/nhs-number",
              "value": "2300992742"
          }
      },

```

<br />

<a name="created"></a>
### created  <a href="#created" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The date of the Claim

```json

  "created": "2004-09-16T16:30:00+00:00",

```

<br />

<a name="provider"></a>
### provider <a href="#provider" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The organisation responsible for the claim

```json
"provider": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "VNE51"
        },
        "display": "The Simple Pharmacy"
    },
```

<br />

<a name="priority"></a>
### priority <a href="#priority" title="link to here" class="self-link"><i class="bi-link"></i></a> 

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


<br>

<a name="prescription"></a>
### prescription  <a href="#prescription" title="link to here" class="self-link"><i class="bi-link"></i></a> 

References to the original prescription, the `groupIdentifier` contains both the ShortForm prescription id and long form UUID variant. See {{pagelink:NHSDigital-MedicationRequest}} for more details.

This MUST not be used to reference the MedicationRequest, this is done via <a href="#detailmedicationRequest">extension medicationRequest</a>

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
    ],
    "display": "The original prescription"
},

```

<br>

<a name="payee"></a>
### payee <a href="#payee" title="link to here" class="self-link"><i class="bi-link"></i></a> 

The recipient of benefits payable. This is the ODS Code of the Pharmacy (provider) making the Claim.

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
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "AB123"
        },
        "display": "The Simple Pharmacy"
    }
}
```

<br>

<a name="insurance"></a>
### insurance <a href="#insurance" title="link to here" class="self-link"><i class="bi-link"></i></a> 

For EPS this is the NHS Business Services Authority. The sequence value must match the sequence number used in the the `item` section. 

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

<br>

<a name="itemoverview"></a>
## item, detail and subDetail <a href="#itemoverview" title="link to here" class="self-link"><i class="bi-link"></i></a> 

- <a href="#item">item</a> refers to the prescription as a whole
- <a href="#detail">detail</a> refers to the MedicationRequest within the prescription.
- <a href="#subdetail">subDetail</a> refers to the MedicationDispense's which relate to a MedicationRequest.

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

<a name="item"></a>
## item <a href="#item" title="link to here" class="self-link"><i class="bi-link"></i></a> 


<a name="prescriptionStatus"></a>
### item.prescriptionStatus(extension) <a href="#prescriptionStatus" title="link to here" class="self-link"><i class="bi-link"></i></a> 

A Code from {{pagelink:DM-Task-Status-Reason.md}}. This will generally match the value of the last `dispense-notification` message.
This should match the `status` of the associated {{pagelink:NHSDigital-Task}}

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
],


```

<br>

<a name="prescriptionStatusReason"></a>
### item.prescriptionStatusReason(extension) <a href="#prescriptionStatusReason" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Mandatory if the medication was not dispensed. The reason will be a code from {{pagelink:DM-medicationdispense-status-reason}}
This should match the `statusReason` of the associated {{pagelink:NHSDigital-Task}}

Should be this CodeSystem 
https://fhir.nhs.uk/CodeSystem/medicationdispense-status-reason

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

<br>

<a name="itemsequence"></a>
### item.sequence  <a href="#itemsequence" title="link to here" class="self-link"><i class="bi-link"></i></a> 

An integer to identify the item within the resource. This should match the sequence value in insurance. Fixed value.

```json

"sequence": 1,

```

<br>


<a name="itemproductOrService"></a>
### item.productOrService <a href="#itemproductOrService" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Mandatory fixed value.

```json

"productOrService": {
    "coding":  [
        {
            "system": "http://snomed.info/sct",
            "code": "16076005",
            "display": "Prescription"
        }
    ]
},

```


<br>

<a name="itemprogramCode"></a>
### item.programCode <a href="#itemprogramCode" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Codes from:

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="50%">ValueSet</th>
     <th data-no-sort width="25%">Min Occurrence </th>
     <th data-no-sort width="25%">Max Occurrence </th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:DM-prescription-charge-exemption}}
    </td>
    <td>
0
    </td>
    <td>
1
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:DM-vs-exemption-evidence}}
    </td>
    <td>
0
    </td>
    <td>
1
    </td>
   </tr>
   </tbody>
</table>

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

<br>


<a name="detail"></a>
## detail <a href="#detail" title="link to here" class="self-link"><i class="bi-link"></i></a> 


<a name="detailsequenceIdentifier"></a>
### detail.sequenceIdentifier(extension) <a href="#deatailsequenceIdentifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

A uuid to identify the line item

```json

"extension":  [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-ClaimSequenceIdentifier",
        "valueIdentifier": {
            "system": "https://fhir.nhs.uk/Id/claim-sequence-identifier",
            "value": "18fc8a8b-f7c7-4367-80ce-1f4fc84c962d"
        }
    }
],

```

<br>

<a name="detailmedicationRequest"></a>
### detail.medicationRequest(extension) <a href="#deatailmedicationRequest" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This should match the `identifier` of the associated {{pagelink:NHSDigital-MedicationRequest}}

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

<br>

<a name="detailsequence"></a>
### detail.sequence  <a href="#deatailsequence" title="link to here" class="self-link"><i class="bi-link"></i></a> 

An integer to identify the item within the resource. This should match the sequence value in insurance.

```json

"sequence": 1,

```

<br>

<a name="detailproductOrService"></a>
### detail.productOrService <a href="#deatailproductOrService" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This should match the `medicationCodeableConcept` of the associated {{pagelink:NHSDigital-MedicationRequest}}

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

<br>

<a name="detailmodifier"></a>
### detail.modifier <a href="#deatailmodifier" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This is the current status of the dispensed medications and is a code from {{pagelink:DM-MedicationDispense-Type}}

If the code is `0002 - Item not dispensed` then the extension <a href="#prescriptionStatusReason">extension prescriptionStatusReason</a> is required.

This should match the `type` of the last associated {{pagelink:NHSDigital-MedicationDispense}}

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

<br>


<a name="detailquantity"></a>
### detail.quantity <a href="#deatailquantity" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This should match the `quantity` of the associated {{pagelink:NHSDigital-MedicationRequest}}

```json

"quantity": {
    "value": 200,
    "unit": "unit dose",
    "system": "http://snomed.info/sct",
    "code": "408102007"
},

```

<a name="detailprogramCode"></a>
### item.detail.programCode <a href="#detailprogramCode" title="link to here" class="self-link"><i class="bi-link"></i></a> 

Dispense Exemption Codes from 

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="50%">ValueSet</th>
     <th data-no-sort width="25%">Min Occurrence </th>
     <th data-no-sort width="25%">Max Occurrence </th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:DM-vs-prescription-charge}}
    </td>
    <td>
0
    </td>
    <td>
1
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:DM-dispensing-endorsement}}
    </td>
    <td>
0
    </td>
    <td>
*
    </td>
   </tr>
   </tbody>
</table>



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

<br>


<br>

<a name="subdetail"></a>
## subDetail <a href="#detail" title="link to here" class="self-link"><i class="bi-link"></i></a> 

subDetail is only present if the medication has been dispensed.

<br>

<a name="subdetailsequence"></a>
### item.detail.subDetail.sequence <a href="#subdetailsequence" title="link to here" class="self-link"><i class="bi-link"></i></a> 

An integer id for each medication dispense.

```json

"sequence": 1,


```

<br>

<a name="subdetailproductOrService"></a>
### item.detail.subDetail.productOrService <a href="#subdetailproductOrService" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This should match the `medicationCodeableConcept` of the associated {{pagelink:NHSDigital-MedicationDispense}}

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

<br>


<a name="subdetailquantity"></a>
### item.detail.subDetail.quantity <a href="#subdetailquantity" title="link to here" class="self-link"><i class="bi-link"></i></a> 

This should match the `quantity` of the associated {{pagelink:NHSDigital-MedicationDispense}}

```json

"quantity": {
    "value": 200,
    "unit": "unit dose",
    "system": "http://snomed.info/sct",
    "code": "408102007"
}

```


