## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="required"></span> Required


<h5><ins>Guidance</ins></h5>

Whether or how long patient abstained from food and/or drink.

Where this is indicated in the incoming EDIFACT report it will be indicated with an `F`. 

This **MUST** be used to populate the `valueCodeableConcept.text` element.

<i class="fa fa-link"></i> [ValueSet: hl7VS-relevantClincialInformation](https://terminology.hl7.org/5.0.0/ValueSet-v2-0916.html)

<h5><ins>Example</ins></h5>

```xml
<collection>
    <extension>
        <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-FastingStatus-1" />
        <valueCodeableConcept>
            <coding>
                <display value="The patient indicated they did not fast prior to the procedure." />
                <code value="NF" />
                <system value="http://terminology.hl7.org/ValueSet/v2-0916" />
            </coding>
            <text value="The patient indicated they did not fast prior to the procedure." />
        </valueCodeableConcept>
    </extension>
</collection>
```

---