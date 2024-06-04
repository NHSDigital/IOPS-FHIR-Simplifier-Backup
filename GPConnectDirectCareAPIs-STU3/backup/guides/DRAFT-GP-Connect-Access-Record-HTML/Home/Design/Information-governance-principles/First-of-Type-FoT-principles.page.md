## {{page-title}}

* provider systems must be compliant with NHS codes of practice and legal obligations, and their existing NHS contractual IG requirements - for example, the foundational requirements for the GP principal systems are covered by the GP Systems of Choice (GPSoC) IG v4 schedule as well as the other common authority requirements
    - requirements additional to these will be documented and included in GP           Connect development, assurance and deployment activities and documentation
- the GP Connect APIs are for use in direct patient care settings only

- the responsibility of ensuring that consuming suppliers’ use of the GP Connect   APIs is compliant with NHS codes of practice and legal obligations resides     with the consuming supplier (not NHS Digital)

- FoT early adopter deployments will represent organisation groupings where the necessary data sharing agreements between data controllers, augmented by data controller-data processor contracts, IG process and policy and fair usage notifications are already in place - for example, existing federation or shared record groups

- organisational data-sharing validation will be implemented as part of the Spine Secure Proxy (SSP) and therefore provider GP Connect go-live must not be dependent on local organisational data-sharing configuration to support this; local organisational data-sharing rules SHALL NOT be applied as part of GP Connect operation and SHALL NOT be changed as a result of GP Connect

- FoT early adopter consuming organisations are N3, IGSoC and IG Toolkit compliant, and meet national requirements for:
    - technical (endpoint) security
    - user authentication
    - user authorisation

- Consuming Organisations must seek permission to view from the Patient for any information supplied via a GP Connect service; in scenarios where the patient is not present, for example a referral to an outpatient clinic where it would be reasonable to review the GP record prior to the appointment, access to the record can be made based on a Legitimate Relationship with the patient, subject to Data-Sharing agreement and absence of Provider System Patient Dissent to share indicator

- the presence of any local patient dissent to share flag within a GP Practice system must be implemented when accessing the patient medical record and cannot be overridden by consent given at the point of care; this flag does not necessarily apply for other capabilities   

- functionality to support the application of an exclusion set must be provided; the current Royal College of General Practitioners (RCGP) sensitive dataset for specific conditions (for example, sexual health, HIV and so on) will be applied (excluded) for FoT with any changes arising from national policy to be reflected