## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `RecipientType` element **MUST** be set to a value taken from FHIR ValueSet [ITK-RecipientType-1](https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1).

The meaning of `RecipientType` is applied in a common way across all ITK3 messaging. 

- `FA` ("For action") means the recipient has been sent the payload for action. The action required by the recipient will be either explicit in the payload or there will be a business rule defined. In this case, "FA" indicates that the recipient is expected to take the action of attaching the payload contents to the patient record. 

- `FI` ("For information") means that no action is required by the recipient and they may process the payload as they see fit.


<h5><ins>Example</ins></h5>

```xml
<!-- For Action -->
<extension>
    <url value="RecipientType" />
    <valueCoding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1" />
        <code value="FA" />
        <display value="For Action" />
    </valueCoding>
</extension>

<!-- For Information -->
<extension>
    <url value="RecipientType" />
    <valueCoding>
        <system value="https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1" />
        <code value="FI" />
        <display value="For Information" />
    </valueCoding>
</extension>
```

---