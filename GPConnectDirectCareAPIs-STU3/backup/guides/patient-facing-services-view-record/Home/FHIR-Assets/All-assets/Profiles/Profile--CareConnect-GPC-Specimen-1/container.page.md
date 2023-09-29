## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="optional"></span> Optional


<h5><ins>Guidance</ins></h5>

The direct container of specimen (tube/slide, etc.)


<h5><ins>Example</ins></h5>

```xml
<container>
    <identifier>
        <system value="https://foo.bar/id/container" />
        <value value="afed6b92-75ff-434d-9dc6-554cb09f4fd2" />
    </identifier>
    <description value="Bar" />
    <type>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="434711009" />
            <display value="Specimen container (physical object)" />
        </coding>
    </type>
    <capacity>
        <value value="15" />
        <unit value="milliliter" />
        <system value="http://unitsofmeasure.org" />
        <code value="mL" />
    </capacity>
    <specimenQuantity value="10" />
        <unit value="milliliter" />
        <system value="http://unitsofmeasure.org" />
        <code value="mL" />
    </specimenQuantity>
    <additiveReference value="substance-00192sk" />
</container>
```

---