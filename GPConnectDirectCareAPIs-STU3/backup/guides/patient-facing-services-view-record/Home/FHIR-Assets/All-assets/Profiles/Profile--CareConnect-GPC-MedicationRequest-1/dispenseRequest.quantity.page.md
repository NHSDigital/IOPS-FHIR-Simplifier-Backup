## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The quantity to dispense.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: If the value is text, then the extension <code>dispenseRequest.quantityText</code> <strong>MUST</strong> be used.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: The extension for `quantityText` is not currently within FHIR R4 / UK Core.
</div>


<h5><ins>Example</ins></h5>

Fully coded

```xml
<dispenseRequest>
    ...
    <quantity>
        <value value="14" />
        <unit value="capsule" />
        <system value="http://snomed.info/sct" />
        <code value="732937005" />
    </quantity>
    ...
</dispenseRequest>
```


Free text

```xml
<dispenseRequest>
    ...
    <quantity>
        <extension url="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationQuantityText-1">
            <valueString value="14 caspules" />
        </extension>
    </quantity>
    ...
</dispenseRequest>
```

---