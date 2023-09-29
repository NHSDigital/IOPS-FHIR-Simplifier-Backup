## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Where to find details of what resources and operations a FHIR server should expose to be a fully compliant GP Connect solution
</div>


## Introduction

GP Connect versions 1.x use the [FHIR STU3](http://hl7.org/fhir/STU3/) standard to specify the API and profiles.

## Profiling principles

Please see the {{pagelink:Home/Design/Design-approach/Data-model-principles.page.md}} page for further information.

## Profiles for each capability pack

The profiled FHIR resources required for each of the GP Connect capability packs are specified within the specific specification sections for each of the capabilities:

* [Foundations](datalibraryfoundation.html)
* [Access Record Structured](accessrecord_structured_development_resources_overview.html)
* [Access Document](access_documents_development_resources_overview.html)

## General FHIR resource population requirements

### Population of optional elements

The purpose of GP Connect is to make the patient data stored within the GP systems available externally so that it can be used to help improve the quality of patient care across the NHS. To give patients the best care possible the data made available through the GP Connect API should be as complete as possible. Therefore, it is expected that both provider and consumers:

* ***SHALL*** populate all the elements within FHIR resources subject to any Capability-specific variance, where data is available within their system irrespective of the cardinality of the elements within the FHIR resource profiles.


### Use of Must-Support flag

Some resource profiles used in GP Connect make use of the [Must-Support](https://www.hl7.org/fhir/STU3/conformance-rules.html#mustSupport) flag. 

Where a Must-Support flag is present on a resource element, a `consumer` system SHALL populate the field in the request body if data is available to do so, irrespective of the fact that field cardinality may be `0..1` or `0..*`. 

Similarly, `provider` systems SHALL populate an element in responses where data is available to do so, irrespective of optional cardinality. When a `provider` system receives data from a consumer for a field marked with the Must-Support flag, the provider system SHALL store this data field in such a way that the data element is preserved and the element can be populated in future responses to consumer requests for the resource in question.

If an element within a FHIR profile is marked as must support then all sub elements of that element SHALL also be considered must support.

## FHIR resource element/data type specific population requirements

### id

The logical id of all FHIR resources SHALL be populated in accordance with the [FHIR specification requirements](https://www.hl7.org/fhir/STU3/resource.html#id), meaning that population of the element is expected.


### Address

The `Address` data type is used in many of the FHIR resources across the GP Connect API. Where an element using the `Address` data type is present in a FHIR resource the following population guidance SHALL be followed:

- The address SHALL be populated using the elements:
  - `line`
    - E.g. House name, flat number, house number and street & village or locality.  Multiple `line` elements SHALL be populated, where more than one line is present.
  - `city`
  - `district`
    - This element is to carry county, where present.
  - `postalCode`
  - `country`
- Where an element is not present, the element SHALL NOT be populated.
  
- The `text` element SHOULD NOT be populated within the address.

- `use` SHALL be populated for patient or patient contact addresses and SHOULD be populated in other contexts.

Example:

```
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

The `ContactPoint` data type is used in many of the FHIR resources across the GP Connect API. Where an element using the `ContactPoint` data type is present in a FHIR resource the following population guidance SHALL be followed:

- The telecom number or address (telephone number, email address etc) SHALL be populated in the `value` element
- `system` SHALL be populated in all circumstances
- `use` SHALL be populated for patient or patient contact telecom details and SHOULD be populated in other contexts.

Example:

```
{
  "system": "phone",
  "value": "01454587554",
  "use": "home"
}
```

### Patient.contact

The Patient.contact element SHALL be populated where demographic information is available in the Patient record.  In accordance with the FHIR definition, it is "Not applicable to register pedigree and family ties beyond use of having contact".

- `relationship.text` SHALL be populated with the type of relationship, for example *Emergency context*, *Next of kin*, or *Carer*.  The element SHALL also be used where a family relationship is recorded, for example *Daughter*.  Multiple relationship entries are allowed.
- `relationship.coding` SHALL NOT be populated
- `name`, `telecom`, `address`, `gender`, `organization` and `period` SHALL be populated where data is available
- `address` and `telecom` SHALL follow the 'Address' and 'ContactPointrules' above for population of these elements

Example:

```
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

Providers SHOULD NOT populate `Bundle.entry.fullUrl`.

Consumers MUST NOT use `Bundle.entry.fullUrl`.

---
