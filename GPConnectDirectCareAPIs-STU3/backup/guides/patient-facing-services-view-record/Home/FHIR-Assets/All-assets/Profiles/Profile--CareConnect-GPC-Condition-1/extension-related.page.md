## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

Related condition

Extension URL
https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-ConditionRelationship-1

<h5><ins>Example</ins></h5>

```xml
<related>
        <type>
                <url value="System: https://fhir-test.hl7.org.uk/STU3/CodeSystem/CareConnect-ConditionRelationship-1" />
                <valueCode value="Nesting" />
        </type>
        <target>
                <url value="System: https://fhir-test.hl7.org.uk/STU3/CodeSystem/CareConnect-GPC-Condition-1" />
                <valueReference value="condition--002lpi2" />
        </target>
</related>
```

---