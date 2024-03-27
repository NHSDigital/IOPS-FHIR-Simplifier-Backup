## {{page-title}}

The results of a query for consultation details **MUST** return a List containing references to all the Encounter resources which represent each consultation that is returned.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then it **MUST** be returned where the `emptyReason.code` has the value of `no-content-recorded`, and the `List.note` element **MUST** be populated with the text "Information not available".

```xml
<List>
    <emptyReason>
        <coding>
            <system value="https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-ListEmptyReasonCode-1" />
            <code value="no-content-recorded" />
            <display value="No Content Recorded" />
        </coding>
    </emptyReason>
</List>
```