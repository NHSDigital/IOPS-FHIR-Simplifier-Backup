## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The `extension.allergyEnd` contains the `endDate` and `endReason` for when the allergy or intolerance was recorded as resolved.

It **MUST** be populated if the `clinicalStatus` has the value of `resolved`.

- The `endDate` element is the date that the allergy or intolerance was recorded as resolved.
- The `reasonEnded` element is the reason that the allergy or intolerance was resolved.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The value "No information available" can be used in exception circumstances where a reason has not been recorded. For example, legacy data may not contain the reason.
</div>

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-AllergyIntoleranceEnd-1" />
    <extension>
        <endDate>
            <valueDateTime value="2022-07-07T14:07:48+00:00" />
        </endDate>
        <reasonEnded>
            <valueString  value="No information available" />
        </reasonEnded>
    </extension>
</extension>
```

---