## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `status` element **MUST** contain either the vaccine product that was administered or intended to be administered.

Where the vaccine product that was administered is not known then the null flavour value code `UNK` **MUST** be populated.

<h5><ins>Example</ins></h5>

Where the vaccine product is known.

```xml
<vaccineCode>
    <system value="http://snomed.info/sct" />
    <code value="1119349007" />
    <display value="Vaccine product containing only severe acute respiratory syndrome coronavirus 2 messenger ribonucleic acid (medicinal product)" />
</vaccineCode>
```

Where the vaccine product is not known.

```xml
<vaccineCode>
    <coding>
    <system value="http://hl7.org/fhir/v3/NullFlavor" />
    <code value="UNK" />
    <display value="Unknown" />
</vaccineCode>
```

---