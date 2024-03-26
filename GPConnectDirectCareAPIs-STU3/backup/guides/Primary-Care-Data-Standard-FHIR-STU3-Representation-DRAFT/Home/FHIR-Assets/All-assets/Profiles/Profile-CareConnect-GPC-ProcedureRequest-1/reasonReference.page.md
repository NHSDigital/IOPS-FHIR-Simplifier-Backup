## {{page-title}}

<h5><ins>Usage</ins></h5>

#### For investigations

<span class="mro-circle required" title="Required"></span> Required

#### For diary entries

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

#### For investigations

A reference to any conditions the patient has that are supplied by the requesting healthcare professional due to their relevance to the test request.

#### For diary entries

A diary entry may have a linked problem which represents the reason for the diary entry. This is required information where it exists, but the problem **MUST** be included and reference the diary entry. The diary entry **MUST NOT** reference to the problem.

<h5><ins>Example</ins></h5>

```xml
<reasonReference>
    <reference value="condition-00t29s" />
</reasonReference>
```

---