## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The category assigned to the condition with a fixed value of `problem-list-item`.

<i class="fa fa-link"></i> [CodeSystem: Care Connect Condition Category](https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-ConditionCategory-1)

<h5><ins>Example</ins></h5>

```xml
<category>
    <coding>
        <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-ConditionCategory-1" />
        <code value="problem-list-item" />
        <display value="Problem List Item" />
    </coding>
</category>
```

---