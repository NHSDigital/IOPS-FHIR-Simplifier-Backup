## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

The quantity to dispense.

When quantity to dispense is available as a numerical value `dispenseRequest.quantity` **MUST** be populated, in preference to `dispenseRequest.quantityText`.

`Unit`, `system` and `code` elements **MUST** be populated when information is available.

If quantity is a textual value, then the extension `dispenseRequest.quantityText` **MUST** be used for both value and units, leaving quantity element unpopulated.

When quantity to dispense is a textual value this field **MUST** contain both the value of the quantity to dispense and the unit e.g. ‘ten tablets’, ‘90 capsules’, ‘one dose’, ‘three millilitres’, ‘quantity varies dependent on schedule’. No information should be populated into `dispenseRequest.quantity` in this scenario.

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