## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The significance of the Problem, which **MUST** have a severity of either `major` or `minor`. 

Provider systems which records multiple levels above `major` or below `minor` should map appropariately to the two available codes within the FHIR definition.

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ProblemSignificance-1" />
    <valueCode value="major" />
</extension>
```

---