## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `identifier` element **MUST** contain a single entry populated to the [HumanName](http://hl7.org/fhir/stu3/datatypes.html#humanname) resource:

- the value for `use` **MUST** be the `official` name
- the value for `family` **MUST** be the patient surname
- the value for `given` **SHOULD** contain the patient forename(s)
- the remaining elements (e.g., `text`, `prefix`, `suffix`, `period`) are optional

<h5><ins>Example</ins></h5>

```xml
<name>
    <use value="official"/>
    <family value="PACKET"/>
    <given value="Chris"/>
</name>
```

---