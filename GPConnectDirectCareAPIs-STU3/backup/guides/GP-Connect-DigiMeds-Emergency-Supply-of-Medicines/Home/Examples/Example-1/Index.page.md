## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>WARNING</b>: The example provided below, while formatted as valid FHIR, relies on outdated curated profiles that do not align with current profiles and values. This discrepancy will cause validation errors when using built-in FHIR validation tools.
</div>

Although libraries like HAPI or Firely can successfully serialize this FHIR data, their underlying validation mechanisms will identify these inconsistencies. Consequently, the receiver of this data will be required to implement an additional mapping layer after serialization to ensure compatibility.

---