## {{page-title}}

<h5><ins>Guidance</ins></h5>

Prefarable as structured dosage aligned to the FHIR dose syntax guidance. But as minimum, can be provided as text.

<h5><ins>Example</ins></h5>




Structured dose syntax:

```xml
<dosageInstruction>
    <text value="10 milligram - two times a day - oral - Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <patientInstruction value="Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <timing>
        <repeat>
            <frequency value="1" />
            <period value="2" />
            <periodUnit value="d" />
            <when value="C" />
        </repeat>
    </timing>
    <route>
        <coding>
            <system value="https://snomed.info/sct" />
            <code value="26643006" />
        </coding>
        <text value="oral" />
    </route>
    <doseQuantity>
        <value value="10" />
        <unit value="milligram" />
        <system value="https://unitsofmeasure.org" />
        <code value="mg" />
    </doseQuantity>
</dosageInstruction>
```
Legacy (free text):
```xml
<dosage>
    <text value="10 milligram - two times a day - oral - Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <patientInstruction value="Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
</dosage>
```
