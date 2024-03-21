## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>TODO:</strong> This should be a 'MUST SUPPORT' / 'Required' element.
</div>

<h5><ins>Guidance</ins></h5>

### For structural lists

Where the list is used to create primary or secondary lists in response to a query this is when the list was created.

### For lists used in consultations

The system rather than clinical date time for when the consultation was last edited, that is, the date time the consultation was last modified on the source system.

If no separate date time is recorded for consultation sub sections, the overall audit date of the consultation is replicated at all levels.

The clinically significant or effective consultation date is provided by the associated `Encounter` profile.

<h5><ins>Example</ins></h5>

```xml
<date value="2022-11-01T11:09:00Z">
```

---