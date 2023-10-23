---
topic: Home
---

## Home

<div markdown="span" class="alert alert-nhse" role="alert">
<b>IMPORTANT:</b> This Implementation Guide is currently in Draft and SHOULD NOT be used for development or active implementation without consulting the NHS England Pathology Standards and Implementation team. For further information please contact: <a href="mailto:pathology.standardsandimplementation@nhs.net">pathology.standardsandimplementation@nhs.net</a></div>

### Specification Overview

This Implementation Guide and the HL7<sup>&reg;</sup> FHIR<sup>&reg;</sup> R4 artefacts that it references define a specification to enable the exchange of pathology laboratory data.

This is version 0.1.2. For the version history see {{pagelink:ReleaseNotes}}.

The specification has been created by [NHS England]( https://simplifier.net/organization/NHSDIgital) and forms part of the [NHS England Pathology Project]( https://simplifier.net/pathology). The profiles that this specification references are derived from the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current), currently STU2.

### Pathology Overview

Pathology tests are used in many aspects of patient care to support the diagnosis, treatment, monitoring and prevention of disease.

Pathology comprises a wide range of specialities. The key specialities can be grouped as follows:

* blood sciences – this includes clinical biochemistry (also known as chemical pathology), haematology, immunology and transfusion medicine
* microbiology – this includes bacteriology, virology and serology
* cellular pathology – this includes cytology and histopathology
* genetics – this includes clinical cytogenetics and molecular genetics

Most pathology tests are performed by pathology laboratories. These include hospital-based laboratories and specialist reference laboratories (which are often based regionally or nationally). Note: the terms 'pathology laboratory' and 'laboratory' are used interchangeably throughout this specification. 

An increasing number of pathology tests are performed outside of laboratories. These include tests that that may be performed at a point of care (usually by a Health Care Professional in a care setting such as a GP practice or in a hospital ward) or by a patient or their carer at home. The current focus of this specification is on laboratory-based tests rather than those undertaken at point of care.

### Pathology Standards
This specification has been developed by the Pathology Standards and Implementation team within NHS England. The team has also developed a SNOMED CT<sup>&reg;</sup> based set of pathology laboratory test request and test result codes (previously known as the Unified Test List or UTL).

These products will initially be used to replace the [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) messaging specification and [Pathology Bounded Code List](https://isd.digital.nhs.uk/trud3/user/guest/group/0/pack/38) (PBCL). These are currently used to define the structure and clinical coding of test reports that flow between laboratories and GP practices.

Further information relating to the work of the Pathology Standards and Implementation team can be found [here](https://digital.nhs.uk/services/pathology-standards-and-implementation).
