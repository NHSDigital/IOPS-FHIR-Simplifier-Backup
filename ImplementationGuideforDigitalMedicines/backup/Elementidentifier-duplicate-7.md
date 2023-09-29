## Element: `identifier` <span class="mro-circle mandatory" title="Mandatory"></span>

A business required element to identify the clinical practitioner using their professional code issued by their professional body.

The <code>identifier.system</code> must be the appropriate uri for the professional body:

- General Medical Council = [https://fhir.hl7.org.uk/Id/gmc-number](https://fhir.hl7.org.uk/Id/gmc-number)
- Nursing and Midwifery Council = [https://fhir.hl7.org.uk/Id/nmc-number](https://fhir.hl7.org.uk/Id/nmc-number)
- General Pharmaceutical Council = [https://fhir.hl7.org.uk/Id/gphc-number](https://fhir.hl7.org.uk/Id/gphc-number)
- Health and Care Processional Council = [https://fhir.hl7.org.uk/Id/hcpc-number](https://fhir.hl7.org.uk/Id/hcpc-number)

The <code>identifier.value</code> must be the practitioner’s professional code issued by their professional body.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> Where a user has been issued with an NHS Identity (e.g. issued with an NHS Smartcard) it is recommended to include their SDS User Id as an additional identifier.
</div>

The <code>identifier.system</code> must be:

- Spine Directory Services = [https://fhir.nhs.uk/Id/sds-user-id](https://fhir.nhs.uk/Id/sds-user-id)

The <code>identifier.value</code> must be the SDS-User Identifier.


### Example

The example below contains a practitioner (e.g., a consultant with a GMC Code) who has an SDS User Id of 1415870201 and a GMC code of C2134567:

```xml
{
  "resourceType": "Practitioner",
  ...
  "identifier": [
          {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "1415870201"
          },
          {
            "system": "https://fhir.hl7.org.uk/Id/gmc-number",
            "value": "C2134567"
          }
        ]
  ...
}
```

---