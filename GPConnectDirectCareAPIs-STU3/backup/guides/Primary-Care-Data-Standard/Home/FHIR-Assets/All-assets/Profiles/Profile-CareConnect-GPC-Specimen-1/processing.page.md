## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="optional"></span> Optional


<h5><ins>Guidance</ins></h5>

Information around processing, and processing step details (where relevant).


<h5><ins>Example</ins></h5>

```xml
<processing>
    <description value="Foo" />
    <procedure>
        <coding>
            <system value="http://hl7.org/fhir/v2/0373" />
            <code value="NEUT" />
            <display value="Neutralization" />
        </coding>
    </procedure>
    <additive>
        <reference value="substance-00ofds2" />
    </additive>
    <timeDateTime value="2022-12-05T13:17:00Z" />
</processing>
```

---