### Dispensing (AMPP and VMPP)

Dispensing records should be pack based (Actual Medicinal Product Pack - AMPP) but product codes (VMP, AMP or VMPP) are permissible as defined within the “Guidance for Endorsement” (Ref: NPFIT-ETP-EIM-0015). 

#### AMPP 

The Actual Medicinal Product Pack (AMPP) describes an actual product which is known to have been available linked to both the name of a particular supplier and information on the pack size of the product.

```json
"medicationCodeableConcept": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "10460811000001109",
                "display": "Amoxil 500mg capsules (Dowelhurst Ltd) 12 capsule"
            }
        ]
    },
```

#### VMPP

The Virtual Medicinal Product Pack (VMPP) describes the generic title for a generic or proprietary product pack which is known to have been available. The description includes the pack size.

```json
"medicationCodeableConcept": {
    "coding":  [
        {
            "system": "http://snomed.info/sct",
            "code": "5334111000001101",
            "display": "Amoxicillin 500mg capsules 12 capsule"
        }
    ]
}
```

#### Relationships

The relationships between AMPP and VMPP are:

- a VMP may be linked to one or more VMPPs
- a AMP may be linked to one or more AMPPs.
- a VMPP may be linked to one or more AMPPs

In terms of SNOMED CT, relationships between VTM, VMP and AMP can be described as:

- `Amoxil 500mg capsules (Dowelhurst Ltd) 12 capsule` (AMPP) is a `amoxil 500mg capsules (Dowelhurst Ltd)` (AMP)
- `Amoxicillin 500mg capsules 12 capsule` (VMPP) is a `amoxicillin 500mg capsule` (VMP).
- `Amoxil 500mg capsules (Dowelhurst Ltd) 12 capsule` (AMPP) is a `Amoxicillin 500mg capsules 12 capsule` (VMPP)

<br>

{{render:MedicationDispenseClass}}
