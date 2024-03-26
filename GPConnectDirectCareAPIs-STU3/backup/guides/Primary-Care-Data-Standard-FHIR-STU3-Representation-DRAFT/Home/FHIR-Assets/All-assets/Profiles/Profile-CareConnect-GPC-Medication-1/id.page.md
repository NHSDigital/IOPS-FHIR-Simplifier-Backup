## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

It is recommended this is the medication unique dm+d concept id. This use of this identifier will provide a unique mechanism to return a Medication resource in a RESTful implementation anywhere across the NHS.

For example:

<i class="fa fa-link" aria-hidden="true"></i> https://my.fhir.server/medication/87652004

Where `87652004` in this example is the unique dm+d concept id for the Virtual Therapeutic Moiety for Atenolol.


Where a medication is not within the dm+d and therefore does not have a dm+d code then the approach will be a local implementation decision. If you have a local FHIR Medication Resource server that is being used to share drug data locally then using the Medication Reference URL is OK.

If the data is being shared outside of the local environment then the Medication resource should only reference dm+d data.

<h5><ins>Example</ins></h5>

```xml
<id value="https://my.fhir.server/medication/87652004"/>
```

---