## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### Test Group Header

Reference(s) to the test result(s) observation(s) that make up the test group.

This **MUST** be qualified using the related.type ‘has-member’.

### Individual Test Result

Reference to the test group header observation if the result is part of a test group.

This **MUST** be qualified using the related.type ‘derived-from’.

### Filing Comments

Reference to the test result or test group header that the filing comments resource relates to. Where the filing comments relate to the test report, the reference is made from the ‘Test report’ to the filing comment only.

This **MUST** be qualified using the related.type ‘derived-from’.

### Observations

Can be used to reference another resource related to this observation

<i class="fa fa-link"></i> [Value Set: observation-relationshiptypes](http://hl7.org/fhir/stu3/valueset-observation-relationshiptypes.html)

### Blood Pressure

Contains any hierarchical information between uncategorised data items.

- Populate `related.target` with a reference to the related item of uncategorised data
- Where the related item is a child of this item set `related.type` to `has-member`
- Where the related item is a parent of this item set `related.type` to `derived-from`

<h5><ins>Example</ins></h5>

```xml
<related>
    <type value="sequel-to" />
    <target>
        <reference value="observation-9gf21a" />
    </target>
</related>
```

---