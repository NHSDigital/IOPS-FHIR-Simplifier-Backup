## {{page-title}}

A Shared Record that persists no data but acts as a query proxy. Provider systems each expose a query API onto their patient records. Consumer systems query the shared record, which queries each provider system, amalgamating the results to present a consolidated response back to the consumer system.

{{render: ics-federated-architecture }}{: .img-response}

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
                    <span>Simple, therefore likely to succeed, especially as an initial implementation where provider systems are available to query, e.g. via GPConnect for England General Practice systems.</span>
                </li>
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-green">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <path d="M16,3.5L5.5,14L0,8.5L1.5,7l4,4l9-9L16,3.5z"></path>
                            </svg>
                        </span>
                    </span>
                    <span>Records are stored once, within provider clinical systems, so no complex update or delete processes when the provider system is your clinical system.</span>
                </li>
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-green">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <path d="M16,3.5L5.5,14L0,8.5L1.5,7l4,4l9-9L16,3.5z"></path>
                            </svg>
                        </span>
                    </span>
                    <span>Consumer systems always access the latest/current data.</span>
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
                    <span>Complex update processes when the provider system IS NOT your clinical system.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

For example, if an allergy record shared by a system needs to be updated by another clinician from another care setting. The original record cannot be remotely updated, leaving two options;

1. Implement a parallel process, manual or integrated, enabling one clinician to request a change to a record owned by another clinican who is using a different provider system.
2. An updated record is created by the clinician and made available to the shared record. If the old and new records can be logically linked plus, if possible, marked as superseding, then the shared record can show these records as previous/current. What must be avoided is consumer systems treating these records as separate or duplicate. The specifics of how this could be done using the FHIR standard are being worked through.

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
                    <span>Consumer systems are always accessing the latest/current data, what is the definition of 'current'?</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

A consumer system may query by date, e.g. `effective=ge2020-05-11`, which would return records dated from 11th May 2020. See the [Query for Current Medication](MedicationsDataUseCases#QueryforCurrentMedication) section within this guidance for a definition of 'current medication'.

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
                    <span>Resilience and availability of provider system query APIs.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

If a provider system query API is temporarily unavailable then data from that system will not be accessible. The query response to the consumer system should include information for which provider system(s) were unable to be queried.

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
                    <span>Provider systems may be inconsistent with how they have implemented a standard such as FHIR.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

Aligning to this implementation guidance will help mitigate against this risk. Some provider systems may expose medicines records events using transactional FHIR resources such as `MedicationRequest` and `MedicationDispense`. Some provider systems may expose medicines records as `MedicationStatement` resources, based on the underlying transactional FHIR resources such as `MedicationRequest` and `MedicationDispense`. Some may do both, as is the case for the <a href="https://digital.nhs.uk/developer/api-catalogue/gp-connect-access-record-structured-fhir" class="nhsd-a-link">GPConnect</a> implementation within England, that returns both `MedicationRequest` and `MedicationStatement` resources for the patient's current medication.

---