## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `basedOn` element **SHOULD** be populated with a reference to a `ProcedureRequest` that contains details of a request that was made, providing it is known.

Where present this may also include details of who requested the tests and why the test was requested.

Test requests are not usually submitted in a FHIR format, so this may not be the original request, but rather a container to hold details that were present in the original request.

<h5><ins>Example</ins></h5>

```xml
<basedOn>
    <reference value="procedure-request--001ksid8" />
</basedOn>
```

---