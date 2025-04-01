## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

This indicates the source of a secondary reported record.

This provides additional context to the source of the immunisation record where it is not based on information from the person who administered the vaccine. The `reportOrigin` element can be absent if the record is **NOT** from a primary source, but the origin of the record is otherwise not recorded / known.

This **MUST** be absent where the `primarySource` element has the value of `true`.

<h5><ins>Example</ins></h5>

```xml
<reportOrigin>
    <coding>
        <system value="http://hl7.org/fhir/stu3/valueset-immunization-origin.html">
        <code value="provider" />
        <display value="Other Provider" />
    </coding>
</reportOrigin>
```

---