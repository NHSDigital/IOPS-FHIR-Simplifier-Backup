## {{page-title}}

= Any combination of the above.

Where provider systems are not able (yet) to implement a query API onto their records, but can POST data and have this persisted by the shared record.

Where provider systems can expose a query API, those records can be shared in real-time as per the federated architecture.

Where patients have chosen to use a patient-centric record, provider and consumer systems read and write to that record.

Provider systems can use the shared record as their single and only record, using data both persisted within the shared record, or made available via federated query from provider systems and/or patient-centric records.

{{render: ics-hybrid-architecture}}{:img-responsive}

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
                    <span>Represents the real-world picture of provider systems. Some share data via bulk extracts, some support real-time query interfaces amd some push data based on business event triggers.
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-green">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <path d="M16,3.5L5.5,14L0,8.5L1.5,7l4,4l9-9L16,3.5z"></path>
                            </svg>
                        </span>
                    </span>
                    <span>The likely transition architecture during the adoption of patient-centric stores as these will take time to mature, be understood and be accepted by the general public.
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
                    <span>The combined design considerations, and hence the combined complexity of all architectures.</span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

