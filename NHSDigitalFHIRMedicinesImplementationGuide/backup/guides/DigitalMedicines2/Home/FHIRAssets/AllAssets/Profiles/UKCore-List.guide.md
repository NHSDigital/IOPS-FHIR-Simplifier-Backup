## UKCore-List


| Profile url |
|--
| [https://fhir.nhs.uk/StructureDefinition/UKCore-List](https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.medicines.r4&canonical=https://fhir.nhs.uk/StructureDefinition/UKCore-List) |

| Conformance Url |
|--
| [https://fhir.nhs.uk/StructureDefinition/UKCore-List](https://simplifier.net/ukcore/ukcorelist) | 

This is a list of repeat medications referenced from **CommunicationRequest**.

Each medication item must contain a single medication entry. A medication entry is free text but must contain the medication item name/description using dm+d terms, where these concepts exist or where a mapping from a proprietary terminology exists, otherwise expressed using proprietary terms. Where applicable the statement should contain the current issue number and maximum number of issues authorised, e.g. “Bendroflumethiazide 2.5 mg Tablets (3/6)”. It may also contain dosage instructions or other relevant information.

```json
{
    "resourceType": "List",
    "status": "current",
    "mode": "snapshot",
    "code": {
        "text": "Repeat Medications"
    },
    "subject": {
        "reference": "urn:uuid:848d8470-bd51-494e-9347-8142ea75cb23"
    },
    "entry": [
        {
            "item": {
                "display": "Bendroflumethiazide 2.5 mg Tablets (3/6)"
            }
        },
        {
            "item": {
                "display": "Salbutamol 100micrograms/dose inhaler CFC free 200 dose (2/6)"
            }
        }
    ]
}
```

### Conformance Rules

<br>

| Source Data Item | Target FHIR Element | Additional Conformance |
|--
| | code.text | Default to 'Repeat Medications'  |
|  | subject (patient) | The subject of the list entries | 
| medication | entry[].item.display | DM+D name of the repeat medication |

Example: {{pagelink:List-duplicate-2}}
