## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

A value from a set of SNOMED codes which can be used to describe a type of care setting that the document has come from (if available).

The SNOMED codes have been selected from the 'Services' simple reference set of the SNOMED CT UK coding system.

The most complete list for this valueset can be found in the NHS FHIR HL7 UK Core guidance below:

**Simplifier**
[https://simplifier.net/packages/ukcore.r4.02.00.00/2.0.0/files/365046](https://simplifier.net/packages/ukcore.r4.02.00.00/2.0.0/files/365046)


**SNOMED CT Browser**
[https://termbrowser.nhs.uk/?perspective=full&conceptId1=1127531000000102](https://termbrowser.nhs.uk/?perspective=full&conceptId1=1127531000000102)

<h5><ins>Example</ins></h5>

```xml
<extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-CareSettingType-1">
    <valueCodeableConcept>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="983341000000102" />
            <display value="Pharmacy First service (qualifier value)" />
        </coding>
    </valueCodeableConcept>
</extension>
```

---