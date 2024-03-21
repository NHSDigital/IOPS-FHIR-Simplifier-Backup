## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>TODO:</strong> This should be a 'MUST SUPPORT' / 'Required' element.
</div>

<h5><ins>Guidance</ins></h5>

### For lists used in consultations

Mandatory reference to the `Encounter` profile providing the context for the consultation (Date/Doctor/Place ….)

The Encounter reference is provided by all Lists in the structure rather than the top-level List(Consultation) only.

<h5><ins>Example</ins></h5>

```xml
<encounter>
    <reference value="encounter-12iaq" />
</encounter>
```

---