# {{page-title}}

This guidance contains information for the use of medicines-related content within the [UK Core](https://simplifier.net/guide/UKCoreVersionHistory/Home) standard. 

The FHIR standard is used as part of interoperability solutions, sharing medicines data between clinical systems and between integrated and shared record systems across the UK health sector.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><strong>Note:</strong> You can navigate between the different sections of this guide using the menu located at the top of each page.</div>

---

## Use Cases

This guidance is applicable for the following use cases. Each is described in more detail within the [Medication Data Use Cases](MedicationsDataUseCases){: .nhsd-a-link } page within the [Design](https://simplifier.net/guide/ukcoreimplementationguideformedicines/Design){: .nhsd-a-link } section.

- Inpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy and intended for administration on a hospital ward.
- Medication requests, for a named patient who is on short-term leave from an inpatient stay (but is not discharged), to be dispensed by the hospital pharmacy and intended for administration at home.
- Discharge medication requests, for a named patient, to be dispensed by the hospital pharmacy and issued on discharge for administration at home.
- Outpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy and intended for administration in the Outpatients department, Accident and Emergency department, or Day unit.
- Outpatient medication requests, for a named patient, to be dispensed by the hospital pharmacy for administration at home.
- Medicines reconciliation on hospital admission and discharge, obtaining and updating current medication with a shared medication record system.
- Internal hospital transfer (to a ward using a different ePMA system).
- Hospital transfer to another hospital (using a different ePMA system).

Which can all be supported by the implementation of [Shared Medication Records](SharedMedicationRecordArchitectures).

---

<div class="nhsd-m-checklist">
    <div class="nhsd-a-box nhsd-a-box--border-grey">
        <span class="nhsd-t-heading-s nhsd-!t-col-white nhsd-m-checklist__header">
            Out of scope for this version
        </span>
        <div class="nhsd-m-checklist__list-container">
            <ul class="nhsd-t-list nhsd-!t-margin-bottom-0">
                <!-- Orders for the supply of ward stock medications. -->
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <polygon
                                    points="13.9,1 8,6.9 2.1,1 1,2.1 6.9,8 1,13.9 2.1,15 8,9.1 13.9,15 15,13.9 9.1,8 15,2.1 " />
                            </svg>
                        </span>
                    </span>
                    <span>Orders for the supply of ward stock medications, opposed to orders for a given patient.</span>
                </li>
                <!-- Medication requests between two Trusts where there is a local shortage of supply. -->
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <polygon
                                    points="13.9,1 8,6.9 2.1,1 1,2.1 6.9,8 1,13.9 2.1,15 8,9.1 13.9,15 15,13.9 9.1,8 15,2.1 " />
                            </svg>
                        </span>
                    </span>
                    <span>Medication requests between two Trusts where there is a local shortage of supply.</span>
                </li>
                <!-- Recording of medicines administration events using the FHIR `MedicationAdministration` resource. -->
                <li class="nhsd-m-checklist__icon-list">
                    <span class="nhsd-m-checklist__icon"><span
                            class="nhsd-a-icon nhsd-a-icon--size-xs nhsd-a-icon--col-red">
                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%" height="100%">
                                <polygon
                                    points="13.9,1 8,6.9 2.1,1 1,2.1 6.9,8 1,13.9 2.1,15 8,9.1 13.9,15 15,13.9 9.1,8 15,2.1 " />
                            </svg>
                        </span>
                    </span>
                    <span>Recording of medicines administration events using the FHIR <code>MedicationAdministration</code> resource.</span>
                </li>
            </ul>
        </div>
    </div>
</div>


---

## Use cases covered in other guides

Refer to the [NHS England Electronic Prescription Service (EPS) FHIR API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir){: .nhsd-a-link } specification for the use cases of:
- Primary Care, Community Care and Urgent and Emergency Care (UEC) medication requests to community pharmacy (aka an `FP10`). 
- Outpatient medication requests to be dispensed by a Community Pharmacy (aka an `FP10HNC`).
- Outpatient medication requests to a contracted Outpatient pharmacy.
- Outpatient medication requests to a Homecare medicines provider.

The above EPS specification is **NOT APPLICABLE** to Scotland or Northern Ireland.
