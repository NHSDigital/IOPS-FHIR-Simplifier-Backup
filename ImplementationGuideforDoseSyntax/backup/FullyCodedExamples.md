# Fully Coded Examples

The following `medicationRequest` examples are fully machine-readable in that they **do not** include any free-text instructions within either `additionalInstruction`, `patientInstruction` or `text`.

Examples use combinations of the following elements of the R4 medicationRequest and FHIR Dosage structure;

* `form`
* `method`
* `doseAndRate.doseQuantity`
* `frequency`, `period` and `frequencyMax`
* `when`
* `route`
* `site`
* `asNeededBoolean`
* `boundsDuration`
* `count`
* `event`

Where clinically appropriate, each example is shown as both a **dose-based** and **product-based** instruction.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important:</strong> Examples are not complete with respect to all mandatory or required data for an R4 implementation but instead highlight the variety of use of the FHIR Dosage structure
</div>

---