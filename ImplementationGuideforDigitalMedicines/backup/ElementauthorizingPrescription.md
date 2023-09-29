## Element: `authorizingPrescription` <span class="mro-circle required" title="Required"></span>

This is a required element where the prescription is known and available when constructing the `MedicationDispense` resource.


**Supply Events**

Examples of where medications can be supplied without as a prescription below:


- Emergency supply
- Over The Counter (OTC)
- Patient Group Directions (PGD) 
- Minor Ailment Schemes.


**Dispense Events**

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important</strong>: Where the prescription is available, it is recommended to reference via a URL - using the <code>identifier</code> element rather than adding the <code>medicationRequest</code> as a bundle - to avoid duplication.
</div>

---