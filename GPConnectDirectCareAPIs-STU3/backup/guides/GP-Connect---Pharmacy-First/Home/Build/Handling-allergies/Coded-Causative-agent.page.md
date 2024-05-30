## {{page-title}}

The causitive agent for the allergy or intolerance can be represented within the FHIR `AllergyIntolerance.code`.

When recording an allergy to a medication substance, the provider system **SHOULD** use a dm+d concept class or alternatively, when the allergy is not recorded against a medication substance, the relevant set of SNOMED CT.

<br />

As per guidance within the [UKCoreAllergyCode value set](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/Terminology/AllValueSets/ValueSet-UKCore-AllergyCode?version=2.0.0):


<table>
<tr>
    <td>
        A set of codes from the following dm+d (dictionary of medicines and devices) concept classes that define a medication or medication ingredient that the patient has an allergy or intolerance to:
    </td>
    <td>
        <ul>
            <li>VTM – Virtual Therapeutic Moiety</li>
            <li>VMP – Virtual Medicinal Product</li>
            <li>AMP – Actual Medicinal Product</li>
            <li>Ingredient</li>
        </ul>
    </td>
    </tr>
    <tr>
    <td>
        A set of codes from the SNOMED CT UK coding system that:
    </td>
    <td>
        <ul>
            <li>identify a substance or pharmaceutical or biologic product that the patient has an allergy or intolerance to</li>
            <li>state that the patient has no known allergy or does not have a specific allergy</li>
            <li>provide a degrade of information about a drug or non-drug allergy</li>
        </ul>
    </td>
</tr>
<tr>
    <td colspan="2">
        Where no dm+d or SNOMED CT coded information is available, a specific code from the <a href="https://terminology.hl7.org/5.5.0/CodeSystem-v3-NullFlavor.html">nullFlavor Code System</a> can be used instead to indicate this.
    </td>
</tr>
</table>

---