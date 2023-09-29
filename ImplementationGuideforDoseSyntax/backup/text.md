## Element: `text`

Free text dosage instructions.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: Use the <code>text</code> element to convey a dosage in a human readable format.
</div>

In the future, a nationally available Dose to Text Service (similiar to the one in our [Demonstrator](https://simplifier.net/guide/DoseSyntaxImplementationGuidanceforFHIRSTU3/DosetoTextTranslation)) will be available, and will be recommended to be used.

In the interim - if the `text` element is used: 

Information to clinicians about administration or preparation of the medication (e.g. “infuse as rapidly as possibly via intraperitoneal port” or “immediately following drug x”) should be populated in `dosage.text`. It may also be be used (rarely) for cases where the instructions to patient are too complex to code.

The use of the `Dosage.text` element is discouraged to maximise dosage instructions defined using the coded structures. This position may be subject to change as a result of initial clinical and implementation experience or feedback from the FHIR community.

The `Dosage.text` element would also be populated in an implementation which does not support the coded structures.

In some cases, where the same instruction is relevant to both a clinician and patient, then the instructions may be repeated using several dosage structures - additionalInstruction or patientInstruction toward patient, text toward the clinician. This will ensure the receiving system makes the information available to the appropriate person.

---