## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

### For consultation lists with a type of Topic only

References to any problems that have been linked to this section of the consultation in the sending clinical system.

These links will have been added by a clinician at the sending practice.

<i class="fa fa-link"></i> [Code-system: Care Connect Condition Relationship](https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-ConditionRelationship-1)

<h5><ins>Example</ins></h5>

```xml
<extension>
    <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedProblemHeader-1" />
    <!-- type -->
    <extension>
        <url value="type" />
        <valueCodeableConcept>
            <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-ConditionRelationship-1" />
            <code value="sibling" />
            <display value="Sibling" />
        </valueCodeableConcept>
    </extension>
    <!-- target -->
    <extension>
        <url value="target" />
        <valueReference value="problem-header-condition" />
    </extension>
</extension>
```

---