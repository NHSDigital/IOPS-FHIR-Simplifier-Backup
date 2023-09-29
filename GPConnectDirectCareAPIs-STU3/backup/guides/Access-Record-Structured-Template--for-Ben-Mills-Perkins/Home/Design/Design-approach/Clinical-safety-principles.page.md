## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: High-level design principles related to the clinical safety of the system
</div>

### GP Connect FoT clinical safety principles
The following principles and underlying detailed requirements are currently undergoing review by the NHS Digital Clinical Safety team, so may be subject to change.

Clinical safety is about promoting, and helping embed, clinically safer working practice methods and proactive risk management for patient safety enabled by IT, with consistent application across the NHS.

</br>

### Information standards
This is underpinned by the information standards for clinical risk management, providing a framework for national healthcare initiatives from the Department of Health, NHS England, the Care Quality Commission and other national health organisations and a mechanism for introducing requirements to which the NHS, those with whom it commissions services, and its IT system suppliers, must conform.

</br>

### Commissioning organisations
Commissioning organisations for GP Connect must have a clinical safety framework compliant with Information Standard:

- [(SCCI0160: Clinical Risk Management: its Application in the Deployment and Use of Health IT Systems)](https://webarchive.nationalarchives.gov.uk/ukgwa/20180328134124/http://content.digital.nhs.uk/isce/publication/SCCI0160)

- and are responsible for assuring that deployment and implementation of consumer applications using the GP Connect APIs comply with this framework.

</br>

### Consumer and provider systems
Consumer and provider systems using the GP Connect API must comply with the requirements of the SCCI0129 standard, promoting and ensuring the effective application of clinical risk management by suppliers developing and maintaining health IT systems:

- [(SCCI0129: Clinical Risk Management: its Application in the Manufacture of Health IT Systems)](https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dcb0129-clinical-risk-management-its-application-in-the-manufacture-of-health-it-systems)

- The GP principal providers must also carry through to any GP Connect functionality the clinical safety requirements of the GPSoC framework.

</br>

### Assurance and deployment
Confirmation of compliance with the clinical safety standards as above will be specified as part of the GP Connect Target Operating Model (TOM) against which the consumer supplier will need to assure. The TOM is managed and administered by the NHS Digital Solutions Assurance team.

Commissioning clinical safety approval of the consumer system forms part of the NHS Digital requirements for deployment into live operation.

Provider systems must also demonstrate standards compliance as part of the NHS Digital assurance processes.

</br>

### Demographic cross checking
Consumer systems must compare the returned structured patient demographic data (supplied by the provider system as structured data) against the demographic data held in the consumer system. If differences exist, the consumer system must show an alert/warning and provide details of which fields/values are different between the two systems.

---

</br>