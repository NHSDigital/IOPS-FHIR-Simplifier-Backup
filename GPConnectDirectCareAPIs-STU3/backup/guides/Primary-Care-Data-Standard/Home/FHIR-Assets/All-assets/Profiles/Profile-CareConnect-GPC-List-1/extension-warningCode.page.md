## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### For structural list use only

A code or codes warning of an issue related to this list.

This extension is used to capture warnings that the list may be incomplete as data has been excluded due to confidentiality or may be missing due to data being in transit. It **MUST** be populated using the appropriate code from the table in the warning codes section on the resource population fundamentals page.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ListWarningCode-1" />
    <valueCodeableConcept>
        <coding>
            <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-ListWarningCode-1" />
            <code value="data-awaiting-filing" />
            <display value="Data Awaiting Filing" />
        </coding>
    </valueCodeableConcept>
</extension>
```

---