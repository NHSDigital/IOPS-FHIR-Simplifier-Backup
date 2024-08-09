## {{page-title}}

As part of identifying the latest HPO terms applicable to a patient, servers MAY implement the [$lastn operation](https://hl7.org/fhir/R4/observation-operation-lastn.html), which uses the Observation search parameters to filter results and restricts the return of matching resources to the last n Observations for the patient. e.g. for the latest Renal Insufficiency HPO code value for Meir Lieberman:

```
GET [base]/Observation/$lastn?max=1&patient=Patient/Patient-MeirLieberman-Example&code=https://hpo.jax.org/app/|HP:0000083
```