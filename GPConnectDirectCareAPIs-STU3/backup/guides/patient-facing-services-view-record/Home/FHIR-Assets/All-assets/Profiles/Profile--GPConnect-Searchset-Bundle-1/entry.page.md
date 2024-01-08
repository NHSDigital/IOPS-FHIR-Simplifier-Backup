## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

Items that make up the Bundle.

<h5><ins>Example</ins></h5>

```xml
<entry>
    <fullUrl value='http://exampleGPSystem.co.uk/GP0001/STU3/1/gpconnect-documents/DocumentReference/27863182736'/>
    <resource>
        <subject>
        <reference value='Patient/04603d77-1a4e-4d63-b246-d7504f8bd833'/>
        </subject>
        <created value='2019-06-24T09:35:00+11:00'/>
        <author>
        <reference value='Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7'/>
        </author>
        <content>
        <attachment>
            <size value='3654'/>
            <contentType value='application/msword'/>
            <url value='http://exampleGPSystem.co.uk/GP0001/STU3/1/gpconnect-documents/Binary/07a6483f-732b-461e-86b6-edb665c45510'/>
        </attachment>
        </content>
        <type>
        <coding>
            <display value='Inpatient final discharge letter'/>
            <system value='http://snomed.info/sct'/>
            <code value='824331000000106'/>
        </coding>
        </type>
        <identifier>
        <value value='bb237762-dde2-11e9-9d36-2a2ae2dbcce4'/>
        <system value='https://fhir.nhs.uk/Id/cross-care-setting-identifier'/>
        </identifier>
        <description value='Discharge Summary'/>
        <status value='current'/>
        <masterIdentifier>
        <value value='bb2374e2-dde2-11e9-9d36-2a2ae2dbcce4'/>
        <system value='LocalSystem/1'/>
        </masterIdentifier>
        <indexed value='2019-07-02T09:43:41+11:00'/>
        <id value='27863182736'/>
        <meta>
        <profile value='https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-DocumentReference-1'/>
        </meta>
    </resource>
</entry>
```

---