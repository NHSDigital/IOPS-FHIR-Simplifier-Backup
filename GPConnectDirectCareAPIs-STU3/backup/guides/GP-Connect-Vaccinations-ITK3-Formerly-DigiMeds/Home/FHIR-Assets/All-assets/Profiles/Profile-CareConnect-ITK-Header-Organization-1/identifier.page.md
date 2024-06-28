## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

The ODS Organisation Code for the sending organisation **MUST** be present in the `odsOrganisationCode` slice of the `identifier` element.


<h5><ins>Example</ins></h5>

```xml
<identifier>
    <system value="https://fhir.nhs.uk/Id/ods-organization-code"/>
    <value value="T48NT"/>
</identifier>
```