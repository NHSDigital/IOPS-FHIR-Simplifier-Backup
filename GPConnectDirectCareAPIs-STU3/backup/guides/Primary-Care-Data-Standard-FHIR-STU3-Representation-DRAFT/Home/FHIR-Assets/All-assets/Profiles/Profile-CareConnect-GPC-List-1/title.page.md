## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>TODO:</strong> This should be a 'MUST SUPPORT' / 'Required' element.
</div>

<h5><ins>Guidance</ins></h5>

A human-readable title of the list being sent.

### For structural lists

Descriptive name for the list. The list titles for primary and secondary lists **MUST** be the titles as provided in the tables in {{pagelink:Home/Build/Returning-data-in-lists/Index.page.md}}.

### For lists used in consultations

For example:

**List(Consultation)**

- use the type or the name of the consultation, as it appears to users of the users in the source system
- this will be a duplicate of consultation type / name provided in `Encounter.type`

**List(Topic)**

- the name of the corresponding Topic section in the source consultation (if it is named)

**List(Heading)**

- the name of the heading section on the source system

<h5><ins>Example</ins></h5>

```xml
<title value="Face to face consultation encounter type (record artifact)" />
```

---