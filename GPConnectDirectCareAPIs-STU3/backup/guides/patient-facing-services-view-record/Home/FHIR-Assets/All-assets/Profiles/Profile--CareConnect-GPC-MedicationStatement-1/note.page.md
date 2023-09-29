## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

All notes that are associated with this medication / medical device record.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: All patient notes and prescriber notes at authorisation(plan) and issue(order) level MUST be included in this field. They MUST be concatenated and indicate the level the notes come from (for example, First Issue) and be prefixed with either "Patient Notes:" or "Prescriber Notes:" as appropriate.
</div>


<h5><ins>Example</ins></h5>

```xml
<note>
    <author>
        <reference value="practitioner-00134" />
    </author>
    <time value="2022-10-19T10:12:00Z" />
    <text>
        First Issue | Prescriber notes: Lorem ipsum dolor sit amet, consectetur adipiscing... | Patient notes: Ut enim ad minim veniam, quis nostrud exercitation...
    </text>
</note>
```

---