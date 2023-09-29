## {{page-title}}

### Primary Care / Community Supply

Applicable for the following use cases;
- Primary Care, Community Care and Urgent and Emergency Care (UEC) medication requests to community pharmacy (aka an `FP10` in England or `GP10` in Scotland). 
- Outpatient medication requests to be dispensed by a Community Pharmacy (aka an `FP10HNC`).
- Outpatient medication requests to a contracted Outpatient pharmacy.
- Outpatient medication requests to a Homecare medicines provider.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: For implementations within England using the Electronic Prescription Service (EPS), refer to the specific implementation guidance below; <br /><br />
    <a href="https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir" class="nhsd-a-button nhsd-!t-margin-bottom-0" target="_blank">NHS England Electronic Prescription Service FHIR API</a>
</div>

### Secondary Care

Applicable for the following use cases;
- Inpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy and intended for administration on a hospital ward.
- Medication requests, for a named patient who is on short-term leave from an inpatient stay (but is not discharged), to be dispensed by the hospital pharmacy and intended for administration at home.
- Discharge medication requests, for a named patient, to be dispensed by the hospital pharmacy and issued on discharge for administration at home.
- Outpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy and intended for administration in the Outpatients department, Accident and Emergency department, or Day unit.
- Outpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy for administration at home.

Applicable FHIR resources: `MedicationRequest` and `MedicationDispense`

{{render: use-cases}}{:img-resonsive}

The use of FHIR resources for these use cases is identical except for the following;
- Care setting identified by the `MedicationRequest.category`.
- The quantity of discharge medication to supply may be defined within a `MedicationRequest.dispenseRequest`.

---