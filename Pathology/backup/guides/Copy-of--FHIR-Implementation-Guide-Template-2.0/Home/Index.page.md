---
topic: Home
---

<div markdown="span" class="alert alert-nhse" role="alert">
<b>IMPORTANT:</b> This Implementation Guide is currently in Draft and SHOULD NOT be used for development or active implementation without consulting the NHS England Pathology Standards and Implementation team. For further information please contact: <a href="mailto:pathology.standardsandimplementation@nhs.net">pathology.standardsandimplementation@nhs.net</a></div>

## Pathology FHIR Implementation Guide
### Specification Overview
This Implementation Guide and the HL7<sup>&reg;</sup> FHIR<sup>&reg;</sup> R4 artefacts that it references define a specification to enable the exchange of pathology laboratory data.

The specification has been created by [NHS England]( https://simplifier.net/organization/NHSDIgital) and forms part of the [NHS England Pathology Project]( https://simplifier.net/pathology). The profiles that this specification references are derived from the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current), currently STU2.

For the version history see {{pagelink:ReleaseNotes}}.

### Pathology Overview
Pathology tests and investigations are critical to many aspects of patient care, supporting the diagnosis, treatment, monitoring and prevention of disease. Pathology comprises a broad range of specialities, each of which includes many individual tests. The key specialities can be grouped as follows:

* blood sciences – this includes clinical biochemistry (also known as chemical pathology), haematology, immunology and transfusion medicine
* microbiology – this includes bacteriology, virology and serology
* cellular pathology – this includes cytology and histopathology
* genetics – this includes clinical cytogenetics and molecular genetics

Pathology tests are requested by a variety of care provider organisations in primary care, secondary care and community settings. Within the NHS in England most pathology tests are performed by laboratories based in hospitals. Some pathology laboratories provide specialist and reference pathology testing services, often at a regional level. Over the past few years, laboratories have been forming regional [pathology networks](https://www.england.nhs.uk/pathology-networks/). 

An increasing number of pathology tests are performed outside of laboratories. These include tests that may be performed at a point of care (usually by a Health Care Professional in a care setting such as a GP practice or in a hospital ward) or by a patient or their carer at home.

### Pathology Data Products
This specification has been developed by the [Pathology Standards and Implementation](https://digital.nhs.uk/services/pathology-standards-and-implementation) team within NHS England. The team has also developed a SNOMED CT<sup>&reg;</sup> based catalogue of pathology laboratory test request and test result codes. This catalogue was previously known as the Unified Test List (UTL). The UTL was originally a relatively simple set of codes representing pathology laboratory test requests and results, with each code carrying a SNOMED CT concept identifier. Following extensive modelling and classification work, the UTL has evolved into 'true' SNOMED CT. The content is accessible via two SNOMED CT reference sets:

* [PaLM (Pathology and Laboratory Medicine) procedure simple reference set](https://termbrowser.nhs.uk/?perspective=full&conceptId1=1853561000000109&edition=uk-edition&release=v20230927&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104) - containing laboratory test request codes
* [PaLM (Pathology and Laboratory Medicine) observable entity simple reference set](https://termbrowser.nhs.uk/?perspective=full&conceptId1=1853551000000106&edition=uk-edition&release=v20230927&server=https://termbrowser.nhs.uk/sct-browser-api/snomed&langRefset=999001261000000100,999000691000001104) - containing laboratory test result codes

Together with the Pathology FHIR specification, the PaLM reference sets form a group of related data products. These products will initially be used to replace the [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) messaging specification and [Pathology Bounded Code List](https://isd.digital.nhs.uk/trud3/user/guest/group/0/pack/38) (PBCL). These are currently used to define the structure and clinical coding of test reports that flow between laboratories and GP practices. There is an urgent need to replace the use of PMIP EDIFACT (NHS003) due to the following fundamental limitations:

* it is unable to carry SNOMED CT test result concepts - it can only support Read codes; the final release of Read CTV3 was in April 2018 consequently it has not been possible to create new PBCL Read codes since then 
* it is unable to support complex report structures using fully atomic, coded results - the data elements of complex reports are mainly represented as text with limited clinical coding
* due to the age of the underlying EDIFACT standard, its continued use is a significant barrier to new system suppliers

### Scope
The current scope of the Pathology FHIR specification reflects the priority of replacing PMIP EDIFACT (NHS003) and the PBCL. In summary:

* the initial focus is on the ability to support pathology test reporting for tests that are requested by GP practices in primary care
* the clinical payload that is supported by the specification is aligned with the PaLM reference sets and covers the following pathology disciplines:
    * blood sciences - clinical biochemistry (also known as chemical pathology), haematology, immunology and transfusion medicine
    * microbiology - bacteriology, virology and serology

### Related Guides
Refer to the following related implementation guidance: 

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- UK Core -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu2?version=1.1.3" class="nhsd-a-box-link "
                        aria-label="Read the UK Core Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h3>UK Core FHIR Guidance</h3>
                                    <p>This guide is to be used as the base for implementing FHIR in the UK.</p>
                                </div>
                                <div class="nhsd-m-card__button-box">
                                    <span class="nhsd-a-button nhsd-a-button--invert">
                                        <span class="nhsd-a-button__label">Find out more</span>
                                    </span>
                                </div>
                            </div>
                        </div>
                    </a>
                </article>
            </div>
        </div>
    </div>
</div>
<div markdown="span" class="alert alert-warning" role="alert"><h4 id="Licence"><i class="fas fa-gavel"></i> Licensing and Publisher</h4>
    <ul>
        <li>
Copyright© 2023+ NHS England Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
    <li>
    Developed and authored by NHS England Interoperability Team.
    </ul>
</div>


