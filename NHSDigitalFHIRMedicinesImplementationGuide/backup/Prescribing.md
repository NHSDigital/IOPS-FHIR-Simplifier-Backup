### Prescribing (VMP, AMP and VTM)

#### Different prescribing practices and recording between primary and secondary care

Differences between secondary and primary care prescribing practices mean that there are differences in the way that medication is recorded in primary and secondary care. In hospital, a prescriber will
record a medication for the nursing team to administer to the patient. This will usually be the generic name, plus dose, quantity, route and frequency. The nurse administering the medication will use this
information to select the correct quantity of an actual product to give to the patient. In primary care, prescriptions are created by selecting a single medicinal product, with the rest of the prescription
expressed in terms of that product.

**Primary care medication** records are product based:

- virtual medicinal product (VMP) - eg `amoxicillin 500mg capsule`
- actual medicinal product (AMP) – eg `amoxil 500mg capsules (Dowelhurst Ltd)`.

The VMP code for `amoxicillin 500mg capsule` includes the active ingredient (amoxicillin), the strength
(500 mg) and the form (capsule).

The following information is included in the structure of the medication record:

– dosage instructions (eg one, three times daily)
- quantity (eg 15 capsules)
- duration (eg five days).

**Hospital prescribing records** are dose based (and may also be product based):

- Virtual therapeutic moiety (VTM) – eg amoxicillin

The following information is included in the structure of the medication record:

- medication form (eg capsule)
- dose (eg 500mg)
- route (eg oral)
- medication frequency (eg one, three times daily).

#### VMP

The Virtual Medicinal Product (VMP) describes the generic title for a product including the form and strength.

```json
"medicationCodeableConcept": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "323510009",
                "display": "Amoxicillin 500mg capsules"
            }
        ]
    },
```

#### AMP

The Actual Medicinal Product (AMP) describes an actual product which is known to have been available linked to the name of a particular supplier.

```json
"medicationCodeableConcept": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "10460611000001105",
                "display": "Amoxil 500mg capsules (Dowelhurst Ltd)"
            }
        ]
    },
```

#### VTM Example

This is for illustrative purposes and should not be used, see section on form below for more details.

```json
"medicationCodeableConcept": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "27658006",
                "display": "Amoxicillin"
            }
        ]
    },
```

#### Relationships

The relationships between VTM, VMP and AMP are:

- a VTM may be linked to one or more VMPs
- a VMP may be linked to one or more AMPs.

In terms of SNOMED CT, relationships between VTM, VMP and AMP can be described as:

- `amoxil 500mg capsules (Dowelhurst Ltd)` (AMP) is a `amoxicillin 500mg capsule` (VMP)
- `amoxicillin 500mg capsule` (VMP) is a `oral form amoxicillin` which is a `amoxicillin` (VTM).

<br>

{{render:MedicationClass}}

#### Form 

The dose, quantity and duration details are contained within the FHIR `MedicationRequest` resource. Form is not and this presents problems with VTM medications. 
For VTM prescriptions the use of FHIR `Medication` resource is highly recommended to express the form of the medication.

In the example below the VTM `Amoxicillin` is represented as a FHIR `Medication`

```json
{
    "resourceType": "Medication",
    "id": "vtm-amoxicillin",
    "code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "27658006",
                "display": "Amoxicillin"
            }
        ]
    },
    "form": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "385049006",
                "display": "Capsule"
            }
        ]
    }
}
```

When a medication needs to be represented using a FHIR `Medication`, the FHIR `MedicationRequest` resource **MUST** use a `medicationReference` instead of a `medicationCodeableConcept` to the `Medication` resource

E.g. 

```json
"medicationReference": {
        "reference":  "Medication/vtm-amoxicillin",
        "display": "Amoxicillin Capsule"
    }
```

or a reference within a FHIR Bundle

```json
"medicationReference": {
        "reference":  "urn:uuid:495df5c5-5931-4795-960d-d2188bec3c2e",
        "display": "Amoxicillin Capsule"
    }
```

It is recommend to make use of `display` to hold the medication name and also the form. The use of contained resources to hold the Medication resource is discouraged (and is not suported by Electronic Prescription Service).
