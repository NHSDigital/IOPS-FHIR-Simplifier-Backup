### NHSDigital-MedicationRequest-Outcome

| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Outcome](https://simplifier.net/guide/DigitalMedicines/DM-MedicationRequest-Outcome) | 

<br>

<br>

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'Differential')">Differential</button>
  <button class="tablinks" onclick="openTab(event, 'Combined')">Combined</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>
<div id="Differential" class="tabcontent" style="display:block">
  <h3>Differential</h3> from {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}} <br><br>

  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Outcome, diff}}
</div>
<div id="Combined" class="tabcontent" >
   <h3>Combined</h3> with {{link:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MedicationRequest}} <br><br>
  {{tree: https://fhir.nhs.uk/StructureDefinition/NHSDigital-MedicationRequest-Outcome, hybrid}}
</div>
<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  See examples in {{pagelink:prescription-order-response}}
</div>

### Relationship to DM-MedicationRequest

`DM-MedicationRequest-Outcome` is similar to the {{pagelink:DM-MedicationRequest.md}} profile but has relaxed rules and less constraints. 

This profile expresses the minimum conformance for MedicationRequest resources when used with `prescription-order-update` messages. Where practical, the conformance rules for {{pagelink:DM-MedicationRequest.md}} should also be followed by suppliers. Consumers should be tolerant of conformance rules being exceeded, 
i.e. received MedicationRequest resources may conform to both this profile and {{pagelink:DM-MedicationRequest.md}} profiles.  


### Administrative Status extension(statusHistory))

The administrative status is held in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionStatusHistory}} and is mandatory for `DM-MedicationRequest-Outcome`

The `status` of the MedicationRequest is linked to the administrative status. In the example below the request to cancel an prescription item (MedicationRequest) failed as the prescription was with the dispenser. In this case the `status` of the MedicationRequest would be `active`.

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionStatusHistory",
        "extension": [
            {
                "url": "status",
                "valueCoding": {
                    "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-status-history",
                    "code": "R-0002",
                    "display": "Prescription/item was not cancelled – With dispenser"
                }
            }
        ]
    }
  ]
```

In the second example below, the prescription item has been returned by the pharamcy and so the 
`status` of the MedicationRequest would be `cancelled`.

```json
"extension": [
    {
        "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionStatusHistory",
        "extension": [
            {
                "url": "status",
                "valueCoding": {
                    "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-status-history",
                    "code": "R-0001",
                    "display": "Prescription/item was cancelled"
                }
            }
        ]
    }
]
```

### medication[x]

Is required in the base `MedicationRequest` resource. When this is not available a `medicationCodeableConcept` with a top level SNOMED Medication Product code **MUST** be used. 

| Code | Display |
|--
| 763158003 | Medicinal product |

E.g.

```json
"medicationCodeableConcept": {
    "coding": [
        {
            "system": "http://snomed.info/sct",
            "code": "763158003",
            "display": "Medicinal product"
        }
    ]
```


