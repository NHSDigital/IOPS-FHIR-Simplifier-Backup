## Example

These are worked examples to illustrate use of Medicinal Product information and how it applies to prescriptions for a developer. It does not replace any regulatory requirement. 

### Borderline Endorsement

`Dextrose` is listed under Part XV Borderline Substances of the {{pagelink:DrugTariff}}

{{render:Borderline}}

In {{pagelink:NHSDigital-MedicationRequest.md}} this will be recorded 
in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement}}

```json
    "extension":  [
      {
          "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement",
          "valueCodeableConcept": {
              "coding":  [
                {
                    "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-endorsement",
                    "code": "ACBS",
                    "display": "Advisory Committee on Borderline Substances"
                }
            ]
        }
    }
  ],
```

### SLS Endorsement and Controlled Drug

`Clobazam` is a drug used in the treatment of Epilepsy

From consultation of the {{pagelink:drugtariff}} we find this drug comes under Part XVIIIB and the rules state: 

**The Prescriber must endorse the prescription with the reference "SLS"**

{{render:DrugTariff-duplicate-2}}

In {{pagelink:NHSDigital-MedicationRequest.md}} this will be recorded 
in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-PrescriptionEndorsement}}

```json
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

From the {{pagelink:DMDBrowser}} we find VMP products such 
Clobazam 1.25mg/5ml oral suspension (SNOMED CT 14410211000001106) is a Controlled Drug.

{{render:ControlledDrugDMD}}

In {{pagelink:NHSDigital-MedicationRequest.md}} this will be recorded 
in the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-DM-ControlledDrug}}. Note also the quantity is also written on words.

```json
{
    "url": "https://fhir.nhs.uk/StructureDefinition/Extension-DM-ControlledDrug",
    "extension": [
        {
            "url": "quantityWords",
            "valueString": "twenty"
        },
        {
            "url": "schedule",
            "valueCoding": {
                "system": "https://fhir.nhs.uk/CodeSystem/medicationrequest-controlled-drug",
                "code": "CD4-1",
                "display": "Schedule 4 (Part I)"
            }
        }
    ]
}
```






