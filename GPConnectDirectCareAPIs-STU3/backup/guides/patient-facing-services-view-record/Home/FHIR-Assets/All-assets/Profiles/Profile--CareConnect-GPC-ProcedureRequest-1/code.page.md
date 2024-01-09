## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

#### For investigations:

The `code` element can be used to represent the tests requested by the requesting healthcare professional. 

In the event of a code not being available, providers **MUST** populate the `code.text` field with the text `No code available`.

<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="8941001000001100" />
        <display value="Not available (qualifier value)" />
        <snomedCT>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid" />
            <extension>
            <valueId value="8941001000001100" />
                <descriptionId value="8941001000001100" />
                <descriptionDisplay value="Not available (qualifier value)" />
            </extesion>
        </snomedCT>
    </coding>
    <text value="No code available" />
</code>
```

#### For diary entries

The planned event, action or activity.

<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="408490001" />
        <display value="Antipsychotic drug therapy" />
    </coding>
    <text value="No code available" />
</code>
```

---