## {{page-title}}


<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

Conveys the reaction resulting from the allergy / intolerance as a code.

This element is mandatory in the FHIR base profile and so if no data is present please use the `nullFlavour` as outlined here.

Where no code is available, but a textual description of the reaction is available, then the `nullFlavor` UNC **MAY** be used and the textual description conveyed via reaction/description.

If no reaction has explicitly been recorded, but the reaction element is present to convey severity, then reaction/manifestation **SHOULD** be coded as the nullFlavor `NI`.

If the patient has been asked, but is unable to specify a reaction the nullFlavor, `ASKU` **SHOULD** be used.

<h5><ins>Example</ins></h5>

```xml
<reaction>
    <manifestation>
        <coding>
            <display value="Peanut-induced anaphylaxis" />
            <code value="241933001" />
            <system value="http://snomed.info/sct" />
            <snomedCT>
                <extension>
                  <descriptionId value="362151013" />
                  <descriptionDisplay value="Peanut-induced anaphylaxis (disorder)" />
                </extension>
                <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            </snomedCT>
        </coding>
        <text value="Anaphalactic shock" />
    </manifestation>
</reaction>
```

---