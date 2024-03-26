## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The reference range provides a guide for interpretation of the results.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: Where a reference range contains a less than (<code>&#60;</code>) or greater than (<code>&#62;</code>) operators, then it should be written to the <code>referenceRange.text</code> element as these operators are not supported in this context.
</div>

<i class="fa fa-link"></i> [Value Set: referencerange-meaning](http://hl7.org/fhir/stu3/valueset-referencerange-meaning.html)

<i class="fa fa-link"></i> [Value Set: referencerange-appliesto](http://hl7.org/fhir/stu3/valueset-referencerange-appliesto.html)

<h5><ins>Example</ins></h5>

```xml
<referenceRange>
    <low>
        <value value="133" />
        <unit value="millimole per liter" />
        <system value="http://unitsofmeasure.org" />
        <code value="mmol/L" />
    </low>
    <high>
        <value value="146" />
        <unit value="millimole per liter" />
        <system value="http://unitsofmeasure.org" />
        <code value="mmol/L" />
    </high>
    <type>
        <coding>
            <code value="normal" />
            <system value="http://hl7.org/fhir/ValueSet/referencerange-meaning" />
            <display value="Normal Range" />
        </coding>
    </type>
    <appliesTo>
        <code value="1747-5" />
        <system value="http://hl7.org/fhir/ValueSet/referencerange-appliesto" />
        <display value="Beaver" />
    </appliesTo>
</referenceRange>
```

<h5><ins>Example - low and high with value and unit</ins></h5>

```xml
<referenceRange>
    <low>
        <value value="2" />
        <unit value="micromole per liter" />
    </low>
    <high>
        <value value="5" />
        <unit value="micromole per liter" />
    </high>
</referenceRange>
```

<h5><ins>Example - high only, with value and unit</ins></h5>

```xml
<referenceRange>
    <high>
        <value value="5" />
        <code value="U/L" />
    </high>
</referenceRange>
```

<h5><ins>Example - text only</ins></h5>

```xml
<referenceRange>
    <text>
        <value value="< 200.000 mg/L" />
    </text>
</referenceRange>
```


---