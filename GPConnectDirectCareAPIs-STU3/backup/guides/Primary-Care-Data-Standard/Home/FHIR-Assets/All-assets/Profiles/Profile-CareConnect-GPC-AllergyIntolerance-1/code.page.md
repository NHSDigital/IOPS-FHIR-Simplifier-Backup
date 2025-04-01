## {{page-title}}


<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The causative agent such as food, drug or substances that has caused or may cause an allergy, intolerance or adverse reaction in this patient.

Systems will evolve to use the specified vocabulary of SNOMED CT concepts from the specified subset. The subset includes products and concepts from the substance and product hierarchies and allows medication concepts from the dm+d SNOMED CT extension.

In the interim this coded element will hold the primary code for the AllergyIntolerance which may in the case of drug allergies be a medication code or a pre-coordinated code which triggers decision support on the system.

Where the AllergyIntolerance has no coded representation in the source system, but is identified as such in the source record then the appropriate degrade code may be used and the text of the AllergyIntolerance placed in the text of the code.


<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <display value="Transfer-degraded drug allergy" />
        <code value="196461000000101" />
        <system value="http://snomed.info/sct" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="294801000000114" />
                <descriptionId value="294801000000114" />
                <descriptionDisplay value="Transfer-degraded drug allergy (record artifact)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="Allergy to paracetemol" />
</code>

```

---