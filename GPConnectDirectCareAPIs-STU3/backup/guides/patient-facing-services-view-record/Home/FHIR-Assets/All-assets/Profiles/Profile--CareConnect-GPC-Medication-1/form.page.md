## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

Within the dm+d terminology, the VMP, AMP, VMPP and AMPP concepts include a coded form.

Where a medication is identified using a VTM concept and the prescriber wishes to qualify with a form then use this element.

Coded forms should be taken from either the dm+d or from the SNOMED-CT hierarchy as a descendant of the concept [736542009 Pharmaceutical dose form](https://termbrowser.nhs.uk/?perspective=full&conceptId1=736542009).

<h5><ins>Example</ins></h5>

```xml
<form>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="427129005" />
        <display value="Conventional release oral coated capsule (dose form)" />
    </coding>
</form>
```

---