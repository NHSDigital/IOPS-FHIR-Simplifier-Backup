## {{page-title}}

### id

The logical id of all FHIR resources **SHALL** be populated in accordance with the [FHIR specification requirements](https://www.hl7.org/fhir/STU3/resource.html#id), meaning that population of the element is expected.

### Address

The `Address` data type is used in many of the FHIR resources across the GP Connect API. Where an element using the `Address` data type is present in a FHIR resource the following population guidance **SHALL** be followed:

- The address **SHALL** be populated using the elements:
    - `line`
        - E.g. House name, flat number, house number and street & village or locality. Multiple `line` elements **SHALL** be populated, where more than one line is present.
    - `city`
    - `district`
        - This element is to carry county, where present.
    - `postalCode`
    - `country`
- Where an element is not present, the element **SHALL NOT** be populated.
- The `text` element **SHOULD NOT** be populated within the address.
- `use` **SHALL** be populated for patient or patient contact addresses and **SHOULD** be populated in other contexts.

Example:

```json
{
  "use": "home",
  "line": [
    "Trevelyan Square",
    "Boar Ln"
  ],
  "city": "Leeds",
  "district": "West Yorkshire",
  "postalCode": "LS1 6AE"
}
```

### ContactPoint

The `ContactPoint` data type is used in many of the FHIR resources across the GP Connect API. Where an element using the `ContactPoint` data type is present in a FHIR resource the following population guidance **SHALL** be followed:

- The telecom number or address (telephone number, email address etc) **SHALL** be populated in the value element
 `system` **SHALL** be populated in all circumstances
- `use` **SHALL** be populated for patient or patient contact telecom details and **SHOULD** be populated in other contexts.
Example:

```json
{
  "system": "phone",
  "value": "01454587554",
  "use": "home"
}
```

### Patient.contact

The `Patient.contact` element **SHALL** be populated where demographic information is available in the Patient record for those individuals who may need to be contacted in connection with the Patient’s appointment. In accordance with the FHIR definition, it is "Not applicable to register pedigree and family ties beyond use of having contact"

- `relationship.text` **SHALL** be populated with the type of relationship, for example Emergency context, Next of kin, or Carer. The element **SHALL** also be used where a family relationship is recorded, for example Daughter. Multiple relationship entries are allowed.
- `relationship.coding` **SHALL NOT** be populated
- `name`, `telecom`, `address`, `gender`, `organization` and `period` **SHALL** be populated where data is available
- `address` and `telecom` **SHALL** follow the [Address](#address) and [ContactPoint](#contactpoint) rules above for population of these elements

Example:

```json
{
  "relationship": [
    {
      "text": "Emergency contact"
    },
    {
      "text": "Next of kin"
    },
    {
      "text": "Daughter"
    }
  ],
  "name": {
    "use": "official",
    "text": "JACKSON Jane (Miss)",
    "family": "Jackson",
    "given": [
      "Jane"
    ],
    "prefix": [
      "Miss"
    ]
  },
  "telecom": [
    {
      "system": "phone",
      "value": "07777123123",
      "use": "mobile"
    }
  ],
  "address": {
    "use": "home",
    "type": "physical",
    "line": [
      "Trevelyan Square",
      "Boar Ln"
    ],
    "city": "Leeds",
    "district": "West Yorkshire",
    "postalCode": "LS1 6AE"
  },
  "gender": "female"
}
```

### Bundle.entry.fullUrl

For {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-StructuredRecord-Bundle-1}}:
- Providers **SHOULD NOT** populate `Bundle.entry.fullUrl`
- Consumers **MUST NOT** use `Bundle.entry.fullUrl`

For {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-Searchset-Bundle-1}}:
- Providers **SHOULD** populate `Bundle.entry.fullUrl`
- Consumers **MUST** use `Bundle.entry.fullUrl`
