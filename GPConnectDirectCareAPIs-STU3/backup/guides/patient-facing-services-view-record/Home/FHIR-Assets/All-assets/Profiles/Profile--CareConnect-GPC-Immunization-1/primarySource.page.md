## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

This indicates whether the record is based on information from the person who administered or intended to administer the vaccine.

This **MUST** be true where the immunisation record was recorded by the person who administered the vaccine or directly on behalf of the administrator of the vaccine (this includes recording the immunisation based on a complete, original, verifiable document from the administration of the vaccine).

This **MUST** be `false` where it is a secondary report of a vaccination for example the recollection of the patient, the patient’s parent, carer or guardian or a secondary document.

As this relates to the context of the original source of the immunisation record, a record from a GP2GP transfer is still a primary record if it was originally recorded as primary.

If it is not known whether the record of the vaccination was made from a primary or secondary source, then return the default value of `true`.

<h5><ins>Example</ins></h5>

```xml
<primarySource value="true" />
```

---