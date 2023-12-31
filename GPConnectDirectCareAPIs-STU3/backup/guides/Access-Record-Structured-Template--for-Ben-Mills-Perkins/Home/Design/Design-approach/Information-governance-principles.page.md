## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: High-level principles related to information governance (IG) of data within the system for First of Type (FoT)
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: The principles below have been discussed and agreed in workshops with the GP principal providers and NHS Digital IG stakeholders.

The detailed requirements supporting these will be available as part of the provider development, consumer development and assurance documentation published within this specification.

Review and agreement as to IG model changes (to accommodate additional capabilities and use cases) is ongoing and will take into account any potential changes arising from the General Data Protection Regulation (GDPR) and other strategic projects in this arena. The programme privacy impact assessment is currently under review and will be updated accordingly. Specifications may evolve to meet changing health and care standards, legal frameworks and patient reasonable and informed expectation.
</div>

### First of Type (FoT) principles

- provider systems must be compliant with NHS codes of practice and legal obligations, and their existing NHS contractual IG requirements - for example, the foundational requirements for the GP principal systems are covered by the GP Systems of Choice (GPSoC) IG v4 schedule as well as the other common authority requirements

     - requirements additional to these will be documented and included in GP Connect development, assurance and deployment activities and documentation

- the GP Connect APIs are for use in direct patient care settings only

- the responsibility of ensuring that consuming suppliers’ use of the GP Connect APIs is compliant with NHS codes of practice and legal obligations resides with the consuming supplier (not NHS Digital)

- FoT early adopter deployments will represent organisation groupings where the necessary data sharing agreements between data controllers, augmented by data controller-data processor contracts, IG process and policy and fair usage notifications are already in place - for example, existing federation or shared record groups

- organisational data-sharing validation will be implemented as part of the Spine Secure Proxy (SSP) and therefore provider GP Connect go-live must not be dependent on local organisational data-sharing configuration to support this; local organisational data-sharing rules SHALL NOT be applied as part of GP Connect operation and SHALL NOT be changed as a result of GP Connect

- FoT early adopter consuming organisations are N3, IGSoC and IG Toolkit compliant, and meet national requirements for:

    - technical (endpoint) security

    - user authentication

    - user authorisation

- Consuming Organisations must seek permission to view from the Patient for any information supplied via a GP Connect service; in scenarios where the patient is not present.

- the presence of any local patient dissent to share flag within a GP Practice system must be implemented when accessing the patient medical record and cannot be overridden by consent given at the point of care; this flag does not necessarily apply for other capabilities

- functionality to support the application of an exclusion set must be provided; the current Royal College of General Practitioners (RCGP) sensitive dataset for specific conditions (for example, sexual health, HIV and so on) will be applied (excluded) for FoT with any changes arising from national policy to be reflected

- any data marked as private/sealed/locked/practice-designated confidential within the GP Patient record must not be shared outside the practice

- the Access Record HTML view will provide appropriate indication of withheld data

- audit requirements as defined in existing contractual frameworks as well as the NHS Digital assurance target operating model must be met by provider and consumer systems

- demographic cross-checking: consumer systems must compare the returned structured patient demographic data (supplied by the provider system as structured data) against the demographic data held in the consumer system

    - if differences exist then the consumer system must show an alert/warning and provide details of which fields/values are different between the two systems

---

</br>