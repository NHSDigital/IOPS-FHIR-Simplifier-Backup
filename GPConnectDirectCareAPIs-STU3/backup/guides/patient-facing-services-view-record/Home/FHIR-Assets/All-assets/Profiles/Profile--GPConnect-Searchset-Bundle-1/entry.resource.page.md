## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

A resource carried within the Bundle. This can be any type of resource, for example `Patient`, `Organization`, `DocumentReference`.

<h5><ins>Example</ins></h5>

```xml
<entry>
    <resource>
        <Organization>
        <id value='db67f447-b30d-442a-8e31-6918d1367eeb'/>
        <meta>
            <versionId value='636064088098730113'/>
            <profile value='https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Organization-1'/>
        </meta>
        <identifier>
            <system value='https://fhir.nhs.uk/Id/ods-organization-code'/>
            <value value='O001'/>
        </identifier>
        <name value='The Trevelyan Practice'/>
        <telecom>
            <system value='phone'/>
            <value value='03003035678'/>
            <use value='work'/>
        </telecom>
        <address>
            <line value='Trevelyan Square'/>
            <line value='Boar Ln'/>
            <city value='Leeds'/>
            <district value='West Yorkshire'/>
            <postalCode value='LS1 6AE'/>
        </address>
        </Organization>
    </resource>
</entry>
```

---