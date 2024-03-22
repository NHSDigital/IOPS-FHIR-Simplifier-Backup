## {{page-title}}

When populating the MedicationRequest profile it may appear that fields are duplicated in other associated resources. This is by design and has two benefits:

- provides context for each individual resource
- enables consumers to know that if no data has been populated it was because no data was available

This leads to the following two principles that **MUST** be applied when populating MedicationRequest profiles:

1. All mandatory fields **MUST** be populated.
2. Required fields **MUST** be populated where the data exists in the system