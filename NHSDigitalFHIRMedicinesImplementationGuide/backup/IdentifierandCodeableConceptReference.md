### Identifier and CodeableConcept Reference

Using references by identifier is the preferred option in FHIR Messaging (and EPS). This is focused on using codes from either NHS Data Dictionary or SNOMED CT.
It is recommended that the `reference.display` is populated with appropriate text as per the guidance within this document.

```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
  <subject>
    <identifier>
      <system value="https://fhir.nhs.uk/Id/nhs-number" />
      <value value="2245386903" />
    </identifier>
    <!-- where 2245386903 is the NHS number for Joe Bloggs held as the 'id' -->
    <display value="Joe Bloggs" />
  </subject>
  <medicationCodeableConcept>
    <coding>
      <system value="http://snomed.info/sct" />
      <code value="323465006" />
      <display value="Flucloxacillin 500mg capsules" />
    </coding>
  </medicationCodeableConcept>
</MedicationRequest>
```