## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `RecipientType` element **MUST** be set to a value taken from FHIR ValueSet [ITK-RecipientType-1](https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1).

The meaning of `RecipientType` is applied in a common way across all ITK3 messaging. 

- `FA` ("For action") in this case indicates that the recipient is expected to take the action of attaching the payload contents to the patient record. 

- `FI` ("For information") is analogous to an email "CC" where no action is expected from the recipient, and the message could be deleted.

<h5><ins>Example</ins></h5>

```xml
<!-- For Action -->
<extension url="RecipientType">
    <valueCoding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1" />
        <code value="FA" />
        <display value="For Action" />
    </valueCoding>
</extension>

<!-- For Information -->
<extension url="RecipientType">
    <valueCoding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1" />
        <code value="FI" />
        <display value="For Information" />
    </valueCoding>
</extension>
```

---