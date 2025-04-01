## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

Kind of document, a value **SHOULD** be taken from the SNOMED refset `1127551000000109 |Record composition type simple reference set (foundation metadata concept)|`. Other classifications of documents **SHOULD** be sent as text.

<h5><ins>Example</ins></h5>

```xml
<type>
    <coding>
        <display value="Inpatient final discharge letter" />
        <code value="824331000000106" />
        <system value="http://snomed.info/sct" />
    </coding>
</type>
```

---