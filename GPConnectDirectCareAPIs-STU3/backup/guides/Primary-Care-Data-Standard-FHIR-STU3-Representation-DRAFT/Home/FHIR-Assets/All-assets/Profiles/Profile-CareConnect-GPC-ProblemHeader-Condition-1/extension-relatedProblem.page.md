## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

A complex extension that details the relationship of this ProblemHeader (Condition) profile to another or a number of other ProblemHeader (Condition) profile.

For each `relatedProblemHeader.target`, the provider **MUST** supply a value of `parent`, `child` or `sibling`

<h5><ins>Example</ins></h5>

```xml
<extension>
    <!-- type -->
    <extension>
        <url value="type" />
        <valueCode value="child" />
    </extension>
    <!-- target -->
    <extension>
        <url value="target" />
        <valueReference value="problem-header-condition-0057t1v" />
    </extension>
</extension>
```

---