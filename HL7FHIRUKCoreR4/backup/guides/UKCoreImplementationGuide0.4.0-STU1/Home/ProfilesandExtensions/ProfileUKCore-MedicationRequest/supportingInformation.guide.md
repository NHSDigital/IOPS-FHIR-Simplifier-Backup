## `supportingInformation`

Optional.Information to support ordering of the medication by reference to <a href="https://www.hl7.org/fhir/r4/resourcelist.html">any FHIR resource </a>where a UK Core profile exists the resource being referenced should conform to the profile.

Some examples of use include:

- Reference an `Observation` resource to share data like the patient’s height and weight.
- Reference a `Condition` resource to share a patient’s condition if this influences the pharmacy dispensing process. For example; [105502003 Dependence on renal dialysis (finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=105502003&edition=uk-edition) or [46177005 End stage renal disease (disorder)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=46177005&edition=uk-edition) would justify an unusual dosage on a prescription.
- Reference an `AllergyIntolerance` resource to share a patient’s allergy to make it clear why certain medication is being requested. For example, a Penicillin allergy.
- Reference a `CarePlan` resource where medication dispensing is considered as part of a specific treatment regimen. For example, care plans for stroke patients.



---
