## {{page-title}}

Whenever possible, the provider system should use a dm+d concept class or alternative to record allergies. If the allergy is not specifically related to a medication substance, the relevant SNOMED CT code should be used.

When neither of these options is feasible, allergy information can be transferred using one of the following three methods:

### Scenario 1

Only the text representation of the allergy is known.

```xml
<AllergyIntolerance xmlns="http://hl7.org/fhir">
  <id value="allergy-intolerance-snippet-1" />
  <clinicalStatus value="active" />
  <verificationStatus value="unconfirmed" />
  <code>
    <coding>
      <system value="http://snomed.info/sct" />
      <code value="196471000000108" />
      <display value="Transfer-degraded non-drug allergy (record artifact)" />
    </coding>
    <text value="Latex" />
  </code>
  <patient>
    <reference value="urn:uuid/14a25380-9796-4c8b-bb9d-6d8e29275565" />
  </patient>
</AllergyIntolerance>
```

### Scenario 2

A text representation of the allergy is known, but any associated coding is unrecognised by the system.

```xml
<AllergyIntolerance xmlns="http://hl7.org/fhir">
  <id value="allergy-intolerance-snippet-2" />
  <clinicalStatus value="active" />
  <verificationStatus value="unconfirmed" />
  <code>
    <coding>
      <system value="http://snomed.info/sct" />
      <code value="196461000000101" />
      <display value="Transfer-degraded drug allergy (record artifact)" />
    </coding>
    <text value="9339101000001105 | Septrin" />
  </code>
  <patient>
    <reference value="urn:uuid:7bf016d4-1dd0-484b-844d-163945f42884" />
  </patient>
</AllergyIntolerance>
```


### Scenario 3

A pre-coordinated allergy code is known which is not part of the permitted value set in the ValueSet