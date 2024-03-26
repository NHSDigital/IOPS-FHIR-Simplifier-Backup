## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The type of consultation as displayed by the system.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: It is preferred that a SNOMED concept be used rather over free-text.
</div>

<h5><ins>Example</ins></h5>

```xml
<type>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="325861000000105" />
        <display value="Face to face consultation encounter type (record artifact)" />
    </coding>
    <text>F2F</text>
</type>
```

---