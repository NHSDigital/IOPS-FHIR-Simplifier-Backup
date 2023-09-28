## `authorizingPrescription`
This is a required element where the prescription is known and available when constructing the `MedicationDispense` resource.

**Supply Events**

Examples of where medications can be supplied without as a prescription below:

- Emergency supply
- Over The Counter (OTC)
- Patient Group Directions (PGD) 
- Minor Ailment Schemes.

**Dispense Events**

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h3>Important</h3>
 Where the prescription is available, it is recommended to reference via a URL - using the <code>identifier</code> element rather than adding the <code>medicationRequest</code> as a bundle - to avoid duplication.
</div>

---
