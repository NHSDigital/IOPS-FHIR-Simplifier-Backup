## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    This element has been removed from FHIR <code>R4</code> so <strong>should not be implemented</strong> as part of an <code>STU3</code> or <code>CareConnect</code> implementation.
</div>


<h5><ins>Example</ins></h5>

```xml
<package>
    <container>
        <coding>
            <system value="http://hl7.org/fhir/medication-package-form" />
            <code value="box" />
            <display value="Box" />
        </coding>
        <text value="A container with a flat base and sides, typically square or rectangular and having a lid." />
    </container>
    <content>
        <itemReference value="medication-882qwf" />
        <amount>
            <system value="http://unitsofmeasure.org" />
            <value value="500">
            <unit value="milliliter" />
            <code value="mL" />
        </amount>
    </content>
    <batch>
        <lotNumber value="1x495b" />
        <expirationDate value="2023-01-01T00:00:00Z" />
    </batch>
</package>
```

---