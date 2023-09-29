---
topic: Introduction
---
## Introduction
This Implementation Guide and the HL7<sup>&reg;</sup> FHIR<sup>&reg;</sup> artefacts that it references define a specification to enable the exchange of pathology laboratory test request and test result data. Pathology tests are used in many aspects of patient care to support the diagnosis, treatment, monitoring and prevention of disease.

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

### FHIR Versions
The specification supports FHIR versions STU3 and R4. Most of the narrative content of the specification applies to both versions of FHIR with any differences noted accordingly. Version specific FHIR assets (profiles, extensions, examples etc.) are referenced and/or included where appropriate.

<div markdown="span" class="alert alert-nhse" role="alert">
<i class="fa fa-exclamation-circle"></i> Unless your implementation is constrained to use FHIR STU3, it is strongly recommended that FHIR R4 is adopted.
</div>

### Scope
The following are **in scope** for this specification:
* the initial focus of the specification is on the ability to support pathology test reporting however aspects of test requesting are included to provide wider context
* the clinical payload that is supported by this specification covers the following pathology disciplines: 
    * blood sciences - clinical biochemistry (also known as chemical pathology), haematology, immunology and transfusion medicine
    * microbiology - bacteriology, virology and serology

The following are currently **out of scope** for this specification:
* the sharing of pathology results relating to national screening programmes
* point of care testing

### Specification Structure
The remainder of the specification is structured as follows:

<table class="regular">
    <thead>
        <tr>
            <th width="10%">Section</th>
            <th width="90%">Description</th>
        </tr
    </thead>
    <tbody>
        <tr>
            <td>FHIR Assets</td>
            <td>A detailed definition of the FHIR resources referenced by this specification.</td>
        </tr>
        <tr>
            <td>Design</td>
            <td>An overview of the key pathology related business processes, user stories and information model supported by this specification, together with a mapping to the corresponding FHIR profiles.</td>
        </tr>   
        <tr>
            <td>Build</td>
            <td>The technical framework used to implement the FHIR resources referenced by this specification.</td>
        </tr>   
        <tr>
            <td>Examples</td>
            <td>A set of example FHIR messages, covering a range of pathology report types and specialities.</td>
        </tr>
    </tbody>
</table>
