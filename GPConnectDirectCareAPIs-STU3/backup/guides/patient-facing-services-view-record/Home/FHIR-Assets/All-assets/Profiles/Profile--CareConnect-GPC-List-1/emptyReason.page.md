## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### For structural list use only

Explanation as to why the list is empty (if applicable).

A FHIR code of `no-content-recorded` **MUST** be recorded in `emptyReason.code` if a query returns no results to enter into a list. In this case, `List.note` **MUST** be populated with the text ‘Information not available’.

<h5><ins>Example</ins></h5>

```xml
<emptyReason>
    <coding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-ListEmptyReasonCode-1" />
        <code value="no-content-recorded" />
        <display value="No Content Recorded" />
    </coding>
</emptyReason>
```