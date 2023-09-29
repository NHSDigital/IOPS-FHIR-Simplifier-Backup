## Element: `medication[x]` <span class="mro-circle mandatory" title="Mandatory"></span>

### Populating the element

Can be either a dm+d code as a CodeableConcept or reference to UK Medication. CodeableConcept is preferred where no more information would be provided by reference to UK Core Medication.

Where a dm+d code exists it MUST be used either as `CodeableConcept.coding` or as `Medication.Medication.code`

Where CodeableConcept is used `CodeableConcept.coding` is dm+d code and `CodeableConcept.text` is dm+d text. Where no dm+d code is available drug name can be provided as text as `CodeableConcept.text`

A Reference to UK Core Medication should only be used when there is additional information to record which is not explicit in CodeableConcept for example where:

- To specify a VTM with a specific form 
- To record manufacture against VTM, VMP and VMP
- To record batch number

---