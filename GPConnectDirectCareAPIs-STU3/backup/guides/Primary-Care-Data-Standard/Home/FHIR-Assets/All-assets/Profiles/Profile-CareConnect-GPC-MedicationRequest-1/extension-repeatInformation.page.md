## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Only populate for a medication request with an `intent` that has been set to `plan`. 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: For a medication request with an <code>intent</code> of <code>order</code>, then none of the repeatInformation fields are populated.
</div>

#### numberOfRepeatPrescriptionsAllowed

The number of repeat issues authorised if specified.

- This **MUST** be present where a repeat is authorised for a defined number of issues.
- It **MUST NOT** be specified for acute prescriptions or where the number of repeat issues has not been defined. There is no concept of an initial dispense in GP Connect usage. Therefore, the `numberOfRepeats` allowed is the total number of allowed issues.

<br />

#### numberOfRepeatPrescriptionsIssued

Running total of number of issues made against a repeat authorisation.

- This **MUST** be zero, if not yet issued.

<br />

#### authorisationExpiryDate

The date a repeat prescription authorisation will expire.

- Only populate for a medication request with an `intent` set to `plan`.

```xml
<extension>
    <url value="https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1" />
    <!-- number of repeat Rx allowed -->
    <extension>
        <url value="numberOfRepeatPrescriptionsAllowed" />
        <valuePositiveInt value="3">
    </extension>
    <!-- number of repeat Rx issued -->
    <extension>
        <url value="numberOfRepeatPrescriptionsIssued" />
        <valuePositiveInt value="0" />
    </extension>
    <!-- authorisation expiry date -->
    <extension>
        <url value="authorisationExpiryDate" />
        <valueDateTime value="2023-01-13T00:00:00Z" />
    </extension>
</extension>
```

---