## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>TODO:</strong> This should be a 'MUST SUPPORT' / 'Required' element.
</div>

<h5><ins>Guidance</ins></h5>

### For structural lists

What order the list is in.

<h5><ins>Example</ins></h5>

```xml
<orderedBy>
    <coding>
        <system value="http://terminology.hl7.org/CodeSystem/list-order" />
        <code value="system" />
        <display value="Sorted by System" />
    </coding>
</orderedBy>
```

### For lists used in consultations

The order the list has been provided. By convention the list entries should appear in the same order as they appear in the source system.

As such, in most cases it is expected that this element will be populated with the value `system`.

<i class="fa fa-link"></i> [CodeSystem: List Order Codes](https://terminology.hl7.org/3.1.0/CodeSystem-list-order.html)

<h5><ins>Example</ins></h5>

```xml
<orderedBy>
    <coding>
        <system value="http://terminology.hl7.org/CodeSystem/list-order" />
        <code value="system" />
        <display value="Sorted by System" />
    </coding>
</orderedBy>
```

---