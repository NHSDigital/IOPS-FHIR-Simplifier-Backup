## {{page-title}}

<h5><ins>Guidance</ins></h5>

A reference to a `CareConnect-GPC-Practitioner-1` profile, representting the clinician responsible for making the obsersvation.

Where the observation was performed at another organisation, then a reference to a `CareConnect-GPC-Organization` **MUST** be populated in the `performer` element. This will be in addition to the clinical practitioner, if both are available.

IF neither the performing organisation, or the clinical practitioner are known, then this **MUST** be populate with the details of the person who recorded teh data into the system.

<h5><ins>Example</ins></h5>

```xml
<reference>
<reference value="Practitioner/12345" >
 
</reference>
```

---