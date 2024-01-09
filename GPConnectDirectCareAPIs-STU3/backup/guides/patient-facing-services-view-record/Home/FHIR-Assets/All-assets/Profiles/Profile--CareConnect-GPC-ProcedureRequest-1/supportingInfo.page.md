## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

#### For investigations

A use-case for the `supportingInfo` element has not been defined.

#### For diary entries

Additional clinical information linked to the diary entry **MAY** be included, except a linked problem which **MUST** be included in the bundle as a {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProblemHeader-Condition-1}} which references the diary entry, not vice versa.

A document **MAY** be linked through a reference to the `Resource`.

<h5><ins>Example</ins></h5>

```xml
<supportingInfo>
    <reference value="observation-001sdk345" />
</supportingInfo>
```

---