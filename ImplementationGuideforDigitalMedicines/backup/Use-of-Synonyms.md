# {{page-title}}

In most instances it is anticipated that the UK Preferred term should be the term applied to SNOMED CT concepts. For some cases the anatomically correct SNOMED-CT term may not be easily understood by the patient or clinician, so the use of a synonym may be preferred. 

See UKCore [Guidance on the use of CodeableConcept](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/Guidance/CodeableConcept-Guidance?version=1.1.3).

An example when using the **preferred term** "Injection - action".

```xml
<!-- Method, using a preferred term -->
<method>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="129326001"/>
        <display value="Injection - action"/>
    </coding>
</method>
```

An example when using the **synonym** "Injection" of the preferred term "Injection - action".

```xml
<!-- Method, using a synonym -->
<method>
    <coding>
        <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescDisplay">
            <valueString value="Injection" />
        </extension>
        <system value="http://snomed.info/sct"/>
        <code value="129326001"/>
        <display value="Injection - action"/>
    </coding>
</method>
```
