## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

A value from a set of SNOMED codes which can be used to describe a type of care setting that the document has come from (if available).

The SNOMED codes have been selected from the 'Services' simple reference set of the SNOMED CT UK coding system.

The most complete list for this valueset can be found in the NHS FHIR HL7 UK Core guidance below:

[https://simplifier.net/hl7fhirukcorer4/ukcore-caresettingtype](https://simplifier.net/hl7fhirukcorer4/ukcore-caresettingtype)


<h5><ins>Example</ins></h5>

```xml
<extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-CareSettingType-1">
    <valueCodeableConcept>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="789718008" />
            <display value="Cardiology service" />
        </coding>
    </valueCodeableConcept>
</extension>
```

---