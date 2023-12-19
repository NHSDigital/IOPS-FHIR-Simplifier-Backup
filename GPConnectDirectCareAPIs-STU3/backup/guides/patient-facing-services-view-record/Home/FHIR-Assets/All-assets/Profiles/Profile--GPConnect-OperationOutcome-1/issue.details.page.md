## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The details of the Spine error will be contained within the element. The Spine error code is included in `details.coding.code` and `details.coding.display` fields.
These shall be taken from the standard set of NHS Spine error codes as defined in the [spine-error-or-warning-code-1](https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1) value set. The Spine error and warning codes provide a greater degree of error handling granularity, and also ensure a standardised error handling approach across NHS APIs.

<h5><ins>Example</ins></h5>

```xml
<details>
    <coding>
        <system value="https://fhir.nhs.uk/STU3/ValueSet/Spine-ErrorOrWarningCode-1"/>
        <code value="INVALID_NHS_NUMBER"/>
        <display value="Invalid NHS number"/>
    </coding>
    <text value="Invalid NHS number"/>
</details>
```

---