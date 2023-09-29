## {{page-title}}

These are the most simple architectures for interoperability between a single prescribing system and a single dispensing system.

<!-- Benefits -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">Potential Benefits
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
                    <span>Simple architecture</span>
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
                    <span>Suitable for a initial implementation or when only two systems need to be interoperable.</span>
                </li>
            </ul>
        </div>
    </div>
</div>

<br />

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">Key Design Consideration
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
                    <span>Which system acts as the Provider and which acts as the Consumer?
                    </span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

### Prescribing and Dispensing systems act as FHIR servers

{{render: api-architecture-both-rx-and-disp-are-fhir-servers-simple}}{:img-resonsive}

<br />

(1) The prescribing system creates the `MedicationRequest` with a valid externally referencable `identifer` and **POST**s to the dipensing system which adds the logical `id` on receipt. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`.

(2) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s to the prescribing system which adds the logical `id` on receipt. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`. 

(3) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`. 

### Dispensing system acts as the FHIR server

{{render: api-architecture-disp-is-fhir-server-simple}}{:img-resonsive}

<br />

(1) The prescribing system creates the `MedicationRequest` with a valid externally referencable `identifer` and **POST**s to the dipensing system which adds the logical `id` on receipt. The `MedicationRequest` is triggered when the `MedicationRequest.status` = `active`.

(2) The prescribing system queries the dispending system via a **GET** using the unique `identifer` from the `MedicationRequest`, i.e. "get the dispensing record for this request". The dispensing system assigns the logical `id`. The GET request may be sent at any time so the dispensing system may choose to expose `MedicationDispense.status` values that represent both in-progress and end-states for the dispensing record.

(3) When the dispensing system returns a `MedicationDispense.status` of `completed`, the prescribing system can set the `MedicationRequest.status` = `completed`. 

### Prescribing system acts as the FHIR server

{{render: api-architecture-rx-is-fhir-server-simple}}{:img-resonsive}

<br />

(1) The prescribing system sends an **event notification** to the pharmacy system when a new `MedicationRequest` is ready for processing. The notification must include the external externally referencable `identifer`. The prescirbing system assigns the logical `id`.

(2) The prescribing system **GET**s the MedicationRequest using the `identifer`. The GET request may be sent at any time so the pharmacy system may choose to expose `MedicationRequest.status` values that represent both in-progress and end-states for the prescribing record.

(3) The dispensing system creates the `MedicationDispense` with a valid externally referencable `identifer` and **POST**s to the prescribing system which adds the logical `id` on receipt. The `MedicationDispense` is triggered when the `MedicationDispense.status` = `completed`.

(4) On receipt, the prescribing system can set the `MedicationRequest.status` = `completed`.  

<!-- Key design consideration -->
<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">Key Design Consideration
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
                    <span>Does not scale for multiple provider and consumer systems with risk of bespoke interfaces.  
                    </span>
                </li>
            </ul>
        </div>
    </div>
</div>
<br/>

Point-to-point messaging interoperability gets very complex when multiple provider and consumer systems are introduced. The number of point-to-point connections needed to integrate a given number of systems increases exponentially as additional systems are added.

To link up two ePMA system plus the hospital pharmacy system will require three point-to-point connections. By adding only two more systems, this changes to 10 connections. With N systems number of connections is N(N-1)/2. With 10 systems, that is 45 separate point-to-point implementations.

Add to that if each system wants subtly difference interfaces the complexity becomes unmanagable. Compare that to using a Shared Record, where the Shared Record sets the standard. All systems implement just one interface, to the Shared Record. 

---
