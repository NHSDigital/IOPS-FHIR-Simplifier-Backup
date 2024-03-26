## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Warning</b>: This element is not present in FHIR R4 / UK Core.
</div>

This is the date the immunisation record (given or not given) was entered on the clinical system. This may be an audit trail date or equivalent for the record. If the immunisation has been transferred by GP2GP this **SHOULD** be the recorded date from the original record entry from the originating system.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DateRecorded-1" />
    <valueDateTime value="2022-10-17T14:21:00Z" />
</extension>
```

---