## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

If the practitioner is represented with structured data such that the family name can be determined (this should be the case when they originate from an internal system) this data **SHOULD** be used to populate `name` including `name.family`. `name.text` **MUST NOT** be populated.

If the practitioner is not represented with structured data or the family name can not be determined (this may be the case when they originate from an external system), `name.text` **MUST** be populated with the full name.

<h5><ins>Example</ins></h5>

```xml
<name>
    <family value="Black"/>
    <given value="Sarah"/>
    <prefix value="Mrs"/>
</name>
```

---