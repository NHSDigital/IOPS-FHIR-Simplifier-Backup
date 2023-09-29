### Identifier and Resource References

The two approaches to referencing can be used together. E.g.

An identifier reference such as 

```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
  <subject>
    <identifier>
      <system value="https://fhir.nhs.uk/Id/nhs-number" />
      <value value="2245386903" />
    </identifier>
    <display value="Joe Bloggs" />
  </subject>
</MedicationRequest>
```
can be combined with a resource reference

```xml

<MedicationRequest>
  <subject>
    <reference value="https://fhir.midyorks.nhs.uk/Patient/2245386903" />
    <display value="Joe Bloggs" />
  </subject>
</MedicationRequest>

```

Resulting in this example

```xml

<MedicationRequest>
  <subject>
    <reference value="https://fhir.midyorks.nhs.uk/Patient/2245386903" />
     <identifier>
      <system value="https://fhir.nhs.uk/Id/nhs-number" />
      <value value="2245386903" />
    </identifier>
    <display value="Joe Bloggs" />
  </subject>
</MedicationRequest>

```

In this example a receiving system has a choice. 

If NHS Number and patient name is sufficient they can process the MedicationRequest without any further API calls or have to resolve the reference within the Bundle.

If they need more Patient details, they can either follow the reference 
`https://fhir.midyorks.nhs.uk/Patient/2245386903`, or use the NHS Number to query a local such as PAS/MPI or Patient Demographic Service(PDS).


