## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important</strong>: Determining the value of this element when constructing the resource.
</div>

##### When the `MedicationRequest` and `MedicationDispense` are <u>known</u>

If the `basedOn` (medication request) and `partOf` (medication dispense) elements are known, and defined within the `MedicationStatement`, then care should be taken as to how the `medication[x]` element is populated.

If `substitution` is allowed within the `MedicationRequest` resource then the medicine dispensed may differ to the request. In this case, this element must reflect the dispensed medication in the `MedicationDispense` resource.

Also note that the `dosageInstruction` may differ from what was originally requested.

Even if `substution` is not allowed, it may be prudent to check that medication requested is equal to what was dispensed.

<br />

##### When the `MedicataionRequest` or `MedicationDispsnese` are <u>not known</u>

The medication component should be constructed by the information provided from the source.


<h5><ins>Example</ins></h5>

```xml
<medicationReference>
    <identifier>
        <system value="https://simplifier.net/gpconnect2" />
        <value value="example--gpc-data-model--medication-request" />
    </identifier>
</medicationReference>
```

---