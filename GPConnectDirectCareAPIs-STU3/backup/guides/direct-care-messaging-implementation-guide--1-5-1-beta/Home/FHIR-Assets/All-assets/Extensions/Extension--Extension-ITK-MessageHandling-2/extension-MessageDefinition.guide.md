## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The `MessageDefinition` element **MUST** be set to fixed value of `https://fhir.nhs.uk/STU3/MessageDefinition/ITK-GPConnectSendDocument-MessageDefinition-1`

More information about the `MessageDefinition` can be found below.

[ITK-GPConnectSendDocument-MessageDefinition-1](https://fhir.nhs.uk/STU3/MessageDefinition/ITK-GPConnectSendDocument-MessageDefinition-1)




<h5><ins>Example</ins></h5>

```xml
<!-- Message payload definition for GP Connect -->
<extension>
    <url value="MessageDefinition" />
    <valueReference>
        <reference value="https://fhir.nhs.uk/STU3/MessageDefinition/ITK-GPConnectSendDocument-MessageDefinition-1" />
    </valueReference>
</extension>
```

---