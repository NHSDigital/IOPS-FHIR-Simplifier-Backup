
## {{page-title}}

Provider systems contribute to a Shared Record which holds a persisted copy of the medication records. The Shared Record is incremental, with new records added rather than replacing previous records. The result is a longitudinal Shared Record. Consumer systems query the Shared Record.

<!--In this example, the **Message Broker** system is akin to a **Shared Record** platform.

{{render:api-architecture-message-broker}}{:img-resonsive}
<br />-->

{{render: ics-persited-copy-architecture}}{:img-responsive}

<br />

(1) Provider systems, e.g. prescribing or dispensing systems, creates FHIR Resources, such as the MedicationRequest and **POST**s to the Shared Record.

(2) Consumer systems queries (**GET**s) the Shared Record to return FHIR Resoures they are interested in. This may be initiated via a manual process, such as a clinican requesting a patient's record, or via a polling mechanism.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: The addition of an <strong>Events Service</strong> can be used to notify subscribing systems of clinical events that can then trigger the query of the Shared Record.</i>
</div>

(3) The Shared Record response contains the relevant FHIR Resource(s). The consumer system can choose to persist all, part or none of the data, as the data can be queried on demand.
<!--
### Query a 'Persisted Copy' Shared Record with an Events service

As above, with the addition of an Events service to notify subscribing systems of clinical events that can trigger the query of the Shared Record.

In this example, the **Message Broker** system is akin to a **Shared Record** platform an also acts as an **events notification** system.

{{render:api-architecture-message-broker-events}}{:img-resonsive}

<br />

(1) Provider systems (e.g. prescribing and dispensing systems) creates FHIR resources (e.g. MedicationRequest) with a valid externally referencable `identifer` and **POST**s this to the Message Broker. The message broker adds the logical `id` on receipt.

(2) The message broker triggers an event, to notify subscribing systems of the new `MedicationRequest`; the dispensing system must be a subscriber for this event.

(3) The dispensing system **GET**s the `MedicationRequest` from the shared record system using the `identifer`. 

(4) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s this to the shared record system. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`. The message broker adds the logical `id` on receipt. 

(5) The message broker triggers an **event notification** to notify subscribing systems of the new `MedicationDispense`; the prescribing system must be a subscriber for this event.

(6) The prescribing system **GET**s the `MedicationDispense` from the message broker using the `identifer`.

(7) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`. -->

<!-- Benefits -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Potential Benefits
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-green">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <path d="M16,3.5L5.5,14L0,8.5L1.5,7l4,4l9-9L16,3.5z"></path>
                            </svg>
                        </span>
                    </span>
                    <span>Persisted data within a resilient shared record infrastructure gives protection from the risk of local provider system unavailability.
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-green">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <path d="M16,3.5L5.5,14L0,8.5L1.5,7l4,4l9-9L16,3.5z"></path>
                            </svg>
                        </span>
                    </span>
                    <span>Aggregation of records within the shared record allows for data analytics across data sets.</span>
                </li>
            </ul>
        </div>
    </div>
</div>

<br />

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Key Design Consideration
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="42%" height="42%" x="29%" y="29%">
    <path d="M8,16c-4.4,0-8-3.6-8-8s3.6-8,8-8s8,3.6,8,8S12.4,16,8,16z M8,2.3C4.9,2.3,2.3,4.9,2.3,8s2.6,5.7,5.7,5.7 s5.7-2.6,5.7-5.7S11.1,2.3,8,2.3z M8,12.9c-0.8,0-1.4-0.7-1.4-1.4C6.6,10.7,7.2,10,8,10c0.8,0,1.4,0.7,1.4,1.4 C9.4,12.2,8.8,12.9,8,12.9z M9.1,3.4l-0.3,6H7.1l-0.3-6H9.1z"></path>
</svg>
                        </span>
                    </span>
                    <span>What are the trigger events within provider systems to update the shared record?
                    </span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

One approach would be to share every medicines-related event with a shared record, as it happens. This works well in primary care and community care settings triggered by events such as prescribing, dispensing, supply and administration. It becomes complex for the secondary care setting as some medicines administered to an in-patient would not be relevant to see outside that care setting, for example pre-operation pain relief medication.

An alternative approach for secondary care is to update a shared record when there is a transfer of care event, such as a hospital admission or discharge/transfer. It is at these events when a medicines reconciliation activity typically occurs, which can be used as the trigger to query and then update a shared record.

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Key Design Consideration
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="42%" height="42%" x="29%" y="29%">
    <path d="M8,16c-4.4,0-8-3.6-8-8s3.6-8,8-8s8,3.6,8,8S12.4,16,8,16z M8,2.3C4.9,2.3,2.3,4.9,2.3,8s2.6,5.7,5.7,5.7 s5.7-2.6,5.7-5.7S11.1,2.3,8,2.3z M8,12.9c-0.8,0-1.4-0.7-1.4-1.4C6.6,10.7,7.2,10,8,10c0.8,0,1.4,0.7,1.4,1.4 C9.4,12.2,8.8,12.9,8,12.9z M9.1,3.4l-0.3,6H7.1l-0.3-6H9.1z"></path>
</svg>
                        </span>
                    </span>
                    <span>What detail of record should be persisted?</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

Persisting the transactional FHIR resources such as `MedicationRequest` and `MedicationDispense` would give access to detailed records. However for the most common use case of querying for current medication, such records would be too detailed. The shared record could consider converting these on-the-fly to `MedicationStatement` resources when querying for current medication. Equally valid would be for the provider systems to create `MedicationStatement` resources from the source data and persist those in the shared record.

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Key Design Consideration
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="42%" height="42%" x="29%" y="29%">
    <path d="M8,16c-4.4,0-8-3.6-8-8s3.6-8,8-8s8,3.6,8,8S12.4,16,8,16z M8,2.3C4.9,2.3,2.3,4.9,2.3,8s2.6,5.7,5.7,5.7 s5.7-2.6,5.7-5.7S11.1,2.3,8,2.3z M8,12.9c-0.8,0-1.4-0.7-1.4-1.4C6.6,10.7,7.2,10,8,10c0.8,0,1.4,0.7,1.4,1.4 C9.4,12.2,8.8,12.9,8,12.9z M9.1,3.4l-0.3,6H7.1l-0.3-6H9.1z"></path>
</svg>
                        </span>
                    </span>
                    <span>A copy of the record is persisted within the shared record, so all provider systems need to implement update and delete processes.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

When a clinical system shares a record, and it is persisted, if that record is updated or deleted within the clinical system, it also needs to be updated or deleted within the shared record. This adds complexity compared to the federated architecture.

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Key Design Consideration
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet" aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="42%" height="42%" x="29%" y="29%">
    <path d="M8,16c-4.4,0-8-3.6-8-8s3.6-8,8-8s8,3.6,8,8S12.4,16,8,16z M8,2.3C4.9,2.3,2.3,4.9,2.3,8s2.6,5.7,5.7,5.7 s5.7-2.6,5.7-5.7S11.1,2.3,8,2.3z M8,12.9c-0.8,0-1.4-0.7-1.4-1.4C6.6,10.7,7.2,10,8,10c0.8,0,1.4,0.7,1.4,1.4 C9.4,12.2,8.8,12.9,8,12.9z M9.1,3.4l-0.3,6H7.1l-0.3-6H9.1z"></path>
</svg>
                        </span>
                    </span>
                    <span>Complex update processes when the provider system IS NOT your clinical system related to ownership and permissions.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

For example, an allergy record posted by one system but needs to be updated by another clinician from another care setting, using a different system.

Do all provider systems and users of those systems in the ecosystem have ownership and permission to update any part of the shared record?

Does only the source provider system and/or source clinician have ownership and permission to update the record that they posted to the shared record?

Should records never be physically updated but instead added and logically linked as superseded?

Are parallel processes, manual or integrated, required to enabling one clinician to request a change to a record owned by another clinican within the shared record?

---