## {{page-title}}

**Integrated Care Boards** (ICBs) within England are responsible for implementing their own [Integrated Care Systems](https://www.england.nhs.uk/integratedcare/what-is-integrated-care/){: .nhsd-a-link }. At the heart of each will be a shared patient record of which medications are key. A view of a patient's current medication is essential information for most patient journeys.

Scotland and Wales are considering more of a national solution for their shared patient records.

There is no single or ideal architecture for a shared medication record, or at least not one that has universal support. This section outlines the following shared record architectures with a suggested maturity roadmap.

1. Persisted Copy Shared Record
2. Persisted Single and Only Shared Record
3. Federated Shared Record
4. Persisted Patient-Centric Shared Record
5. Hybrid Shared Record

In 2024 the Secretary of State for Health and Social Care announced the vision for England for a **Single Patient Record**. Whilst these plans are still in their infancy, this could be implemented as either a 'Persisted Copy Shared Record', a 'Persisted Single and Only Shared Record' or a 'Persisted Patient-Centric Shared Record'.

For most Trust implementations, the role of a Trust Integration Engine (TIE) needs to be understood.

### Role of a Trust Integration Engine (TIE)

Secondary care implementations generally depend on the interactions between multiple provider systems, often from different vendors. The Trust Integration Engine (TIE) enables access to these provider systems through one consistent, secure platform.

Without the TIE as the centrepiece in the architecture, the Trust Patient Administration System (PAS) has to take on the responsibility of integration between provider and consumer systems. This can be complex as the PAS already undertakes a number of responsibilities. 

By implementing the TIE, which is solely involved with the task of integration, the platform becomes more flexible and scalable, and the flow of patient and clinical data more coherent and secure.

Where an implementation uses a Trust Integration Engine (TIE), this would logically sit between the provider/consumer systems and the Shared Record.

{{render: trust-integration-engine}}{:img-responsive}

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
                    <span>Enhance the flow of patient information securely and seamlessly.</span>
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
                    <span>Increase safety of clinical data.</span>
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
                    <span>An integration platform that is more strategic, flexible and scalable.</span>
                </li>
            </ul>
        </div>
    </div>
</div>

<br/>

---
