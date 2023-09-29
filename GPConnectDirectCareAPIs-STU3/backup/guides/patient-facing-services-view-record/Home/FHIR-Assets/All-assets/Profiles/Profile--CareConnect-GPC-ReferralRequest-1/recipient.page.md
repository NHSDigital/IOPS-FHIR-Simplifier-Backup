## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `recipient` element can be used to indicate which practitioner and / or organisation the patient has been referred to, providing that it has been recorded in a suitable coded format.

If the referral recipient details are in a form which cannot be returned as a referenced resource, the details should be populated in the `note` element as key value pairs.

<h5><ins>Example</ins></h5>


```xml
<recipient>
    <reference>
        <identifier>
            <system value="https://fhir.nhs.uk/Id/ods-organization-code" />
            <value value="Q72" />
            <display value="NHS ENGLAND NORTH EAST AND YORKSHIRE (YORKSHIRE AND HUMBER) (Q72)" />
        </identifier>
    </reference>
</recipient>
```

OR


```xml
<note>
    <author>
        <reference value="practitioner-948392" />
    </author>
    <time value="2022-10-13T16:59:00Z" />
    <text>
        Practitioner: Dr Make-you-well
        Organisation: An example organisation
    </text>
</note>
```

---