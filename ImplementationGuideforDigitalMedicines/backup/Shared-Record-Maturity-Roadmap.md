## {{page-title}} (applies to England only)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This is a <strong>suggested</strong> maturity roadmap for the architectural options described above and is <strong>work-in-progress</strong>. <i class="fas fa-hammer"></i>
</div>

It is based on the **current assumption** that the ultimate goal is a "*patient-centric single and only*" shared record.

{{render: shared-records-maturity-roadmap}}{:img-responsive}

The starting architecture will be dictated by ambition, but most likely, the available connected clinical systems within the shared record eco-system.

For example, if no existing systems can provide a query interface but can share data as part of bulk or event-based extracts then you will probably start with a **persisted copy** architecture.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>NOTE:</strong> The following descriptions for transitions through the maturity roadmap are described at a very high level. The detailed complexity of these has not been over-looked and this guidance will be updated over time.
</div>

### Transition: Federated to Hybrid (adding Persisted Copy)

- Introduce a persistence layer to store records obtained by mechanisms such as event-sourcing or bulk data extracts.
- Key design decisions will include what business triggers will result in data persistance.
- Data returned to querying consumer systems is an amalgamation of data retreived from federated queries plus that retreived from persisted data.

### Transition: Persisted Copy to Hybrid (adding Federated)

- Introduce a query proxy for systems that have implemented a query interface.
- Data returned to querying consumer systems is an amalgamation of data retreived from persisted data plus that retreived from federated queries.

### Transition: Persisted Copy to Persisted Single and Only

- Provider systems transition from accessing local records to shared records. This will take time and may start with a subset of records, i.e. maybe start with allergy records. This transition may seem enormous but for those clinical systems that already use cloud-based records, it is switching the provider cloud environment. Some data will remain in the local provider enviroment but the volume should decrease over time, as the size of shared records increases.
- Provider systems transition their record queries from their propriatary APIs to a FHIR API; as shared records should be exposed via a FHIR API. The software change for this could be significant. 

### Transition: Hybrid to Persisted Single and Only

- As per 'Persisted Copy to Persisted Single and Only' above.
- Federated access to records may continue for those provider systems that have not moved across to using a persisted single and only shared record.

### Transition: Patient-Centric Persisted Copy to Patient-Centric Single and Only

- Provider systems transition from copying elements of the local record into the patient-centric record, to using the patient-centric record as the default/master. This will take time and may start with a subset of records, i.e. maybe start with allergy records.
- This transition becomes more feasible once the volume of patients opting to use patient-centric stores increases.

### Transition: Persisted Single and Only to Patient-Centric Single and Only

- This transition could occur in two different ways;
  - A shared regional/provider-specific record has the nessasary APIs added to give the patient control and ownership, including, if requested, the ability for the patient to move their record to another provider.
  - A data migration from a regional/provider-specific shared record provider to a patient-centric shared record provider.

---
