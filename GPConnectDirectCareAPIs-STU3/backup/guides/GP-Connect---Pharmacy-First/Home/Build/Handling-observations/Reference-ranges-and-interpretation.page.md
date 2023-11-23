## {{page-title}}

Providers may supply a reference range along with the associated value - for example:

```xml
<referenceRange>
    <low>
        <value value="3.5"/>
    </low>
    <high>
        <value value="11.0"/>
    </high>
</referenceRange>
```
<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Where a reference range contains a less than <code>&lt;</code> or greater than <code>&gt;</code> operator it should be written to the <code>referenceRange.text</code> element as these operators are not supported in this context.
</div>

Similarly, a provider may wish to provide the interpretation to indicate whether the observation is abnormal (in line with Access Record: Structured).

https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-ObservationInterpretation-1


```xml
<interpretation>
    <coding>
        <system value="http://terminology.hl7.org/CodeSystem/v2-0078"/>
        <code value="A"/>
        <display value="Abnormal"/>
    </coding>
    <text value="Abnormal"/>
</interpretation>
```

The consumer may wish to observe this information, or they may chose to apply their own interpretation on the observation supplied.

---