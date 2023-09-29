## Element: `supportingInformation` <span class="mro-circle optional" title="Optional"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: <b>optional</b> for an MVP implemementation.
</div>

Can reference any number of FHIR resources and if implemented, some examples of use include:

- Reference an [Observation](http://hl7.org/fhir/stu3/Observation.html) resource to share data like the patient’s height and weight.
- Reference a [Condition](http://hl7.org/fhir/stu3/Condition.html) resource to share a patient’s condition if this influences the pharmacy dispensing process. For example; [105502003 Dependence on renal dialysis (finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=105502003&edition=uk-edition) or [46177005 End stage renal disease (disorder)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=46177005&edition=uk-edition) would justify an unusual dosage on a prescription.
- Reference an [AllergyIntolorance](http://hl7.org/fhir/STU3/allergyintolerance.html) resource to share a patient’s allergy to make it clear why certain medication is being requested. For example, a Penicillin allergy.
- Reference a [CarePlan](http://hl7.org/fhir/STU3/careplan.html) resource where medication dispensing is considered as part of a specific treatment regimen. For example, care plans for stroke patients.

---