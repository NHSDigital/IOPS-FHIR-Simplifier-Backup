## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Person and their organization requesting authorisation for prescription.

May not always be the user who entered the record on the system but, where a system supports attribution to a responsible clinician, the attributed clinician **MUST** be referenced here.

If it was prescribed at another practice and has been imported via GP2GP. In that case, the `onBehalfOf` **MUST** be completed with a reference to the other organisation.

<i class="fa fa-link" aria-hidden="true"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Organization-1}}

<h5><ins>Example</ins></h5>

```xml
<requester>
    <agent>
        <identifier>
            <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
            <value value="00143922" />
        </identifier>
    </agent>
</requester>
```

---