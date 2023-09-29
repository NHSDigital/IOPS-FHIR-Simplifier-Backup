## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

A reference to the result(s) which are contained in the `DiagnosticReport`.

This may contain references to standalone test results, test group headers (which then reference further results) or a mixture of both.

Test results which are part of a test group will not be referenced by this element, the reference will be to the test group which will in turn reference the test results.

In GP systems this will also contain a reference to an observation that contains the details of the time that the report was filed into the record. 

This will be identified in the `Observation.code` element, and will be populated with the SNOMED code:


<i class="fa fa-link"></i> [37331000000100 | Comment note (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=37331000000100)

<h5><ins>Example</ins></h5>

```xml
<result>
    <reference value="observation--002lpi2" />
</result>
```

---