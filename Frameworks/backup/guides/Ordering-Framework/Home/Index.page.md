# {{page-title}} 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b> The content on these pages have not been approved or adopted by NHS England.</div>

This Frameworks IG describes common repeating patterns that occur during a Patient Care Journey/Pathway and how HL7 FHIR can be used to automate them. 

This also serves has a HOW TO use Health Interoperability Standards such as HL7 v2 and FHIR.

### Conformance (Data Standards) 

The frameworks use the following data standards:

- [ISO13606 Electronic Health Record Communication](http://www.en13606.org/). See also [openEHR](https://openehr.org/)
- [ISO13940 Concepts for the continuity of care](https://contsys.org/page/default)
- [HL7 FHIR R4 UK Core](https://simplifier.net/guide/uk-core-implementation-guide?)
  - [NHS England Supplement](https://simplifier.net/guide/nhs-england-implementation-guide-stu1)

Note: UK Core should be used as a guide when using other data standards. For example, the IHE XDS Document metadata model should follow **UKCore-DocumentReference** and also HL7 v2 OBX segments should follow **UKCore-Observation**

### Health Interoperability Standards

| Standard | Notes | Status |
|--
| [HL7 FHIR](https://hl7.org/fhir/R4/overview.html) | Current version is R4 | active |
| HL7 v2 | For NHS England see [ADT](https://raw.githubusercontent.com/NHSDigital/IOPS-Frameworks/main/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf) | active |
| [DICOM](https://www.dicomstandard.org/) | Digital Imaging and Communications in Medicine | active |
| HL7 v3 | For NHS England (NPfIT) see [Message Implementation Manual](https://digital.nhs.uk/developer/guides-and-documentation/message-implementation-manuals) | deprecated |
| [IHE](https://profiles.ihe.net/ITI/TF/index.html) | Technical Frameworks | to be defined |  

Other technical standards (e.g. openEHR) will be referenced within the approppiate framework.

### Frameworks

Frameworks link {{pagelink:Home/Care-Process}}, which are often [clinical pathways](https://en.wikipedia.org/wiki/Clinical_pathway), to technical implementation patterns as described in
[NHS England Interoperability Handbook](https://www.england.nhs.uk/wp-content/uploads/2017/03/interoperabilty-handbk.pdf)  

{{render:diagrams-StandardsLayers}}

### Capabilities

| Capability | Description | Framework | IHE Technical Framework |
|--
| Health and Care Record Retrieval | The Health and Care Record Retrieval capability provides a centralised capability to support the retrieval of health care information from multiple locations. The capability orchestrates other services to locate, authorise and retrieve data. | {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents/Federated-Document-API.page.md}} and {{pagelink:Home/Technical-Framework/Query-API/Federated-Query-API.page.md}} | [ Cross-Community Access (XCA)](https://profiles.ihe.net/ITI/TF/Volume1/ch-18.html) |
| Professional Authentication | Professional Authentication provides a single identity for all professional users accessing data and systems. | {{pagelink:Home/Technical-Framework/Security-and-Privacy}} | [Internet User Authorization (IUA)](https://profiles.ihe.net/ITI/IUA/index.html) |
| Data Management | The Data Management capability provides services to support the access and management of terminology, metadata, data models and reference data. | {{pagelink:Home/Technical-Framework/Terminology-and-Conformance}} | [Sharing Valuesets, Codes, and Maps (SVCM)](https://profiles.ihe.net/ITI/SVCM/index.html) |
| Record Location | Record Location supports the storage and management of pointers to system APIs that provide specific types of information. Pointers may point to patient specific data for use in direct care or aggregated collections of data for secondary uses. | {{pagelink:Home/Technical-Framework/Shared-Clinical-Documents}} <br/> and {{pagelink:Home/Technical-Framework/Query-API}} | [Cross-Enterprise Document Sharing (XDS.b)](https://profiles.ihe.net/ITI/TF/Volume1/ch-10.html) <br/> [Mobile Health Document Sharing (MHDS)](https://profiles.ihe.net/ITI/MHDS/index.html) <br/> [Query for Existing Data mobile (QEDm)](https://build.fhir.org/ig/IHE/QEDm/branches/master/index.html) |
| Endpoint Management | The Endpoint Management capability provides centralised storage, reference, and management of local and national service endpoints. It allows services which need to store the address of servers to use logical rather than physical references. It allows a centralised and shared validation of cyber-security checks and monitoring of valid service endpoints. | {{pagelink:Home/Technical-Framework/Health-Administration}} | [Mobile Care Services Discovery (mCSD)](https://profiles.ihe.net/ITI/mCSD/index.html) |
| Organisation Management | Organisation Management provides a searchable directory of organisation details including a unique identifier for each. | {{pagelink:Home/Technical-Framework/Health-Administration}}  | [Mobile Care Services Discovery (mCSD)](https://profiles.ihe.net/ITI/mCSD/index.html) |
| Demographics Management | The Demographics Capability supports the storage and management of a single master copy of a Patients demographics details and their assigned national identifier. | {{pagelink:Home/Technical-Framework/Health-Administration}} | [Patient Administration Management (PAM)](https://profiles.ihe.net/ITI/TF/Volume1/ch-14.html) |
| System Audit | System Audit provides a central capability for all national services to securely store access audits and logging. It provides a central point to provide a system wide view of data access. | {{pagelink:Home/Technical-Framework/Security-and-Privacy}} | [Basic Audit Log Patterns (BALP)](https://profiles.ihe.net/ITI/BALP/index.html) |
| Care Plan Management | National Care Plan Management provides the capability for professionals to store, share and collaborate on a single care plan for a patient. | {{pagelink:Home/Technical-Framework/Care-Plan-Management}} | [Dynamic Care Team Management (DCTM)](https://wiki.ihe.net/index.php/Dynamic_Care_Team_Management_(DCTM)) and [Dynamic Care Planning (DCP)](https://wiki.ihe.net/index.php/Dynamic_Care_Planning_(DCP)) |

### NHS Interperability Handbook, Technical Frameworks and Implementation Standards 

Many of the frameworks will have direct relationship to `Integrating the Healthcare Enterprise (IHE)` Technical Frameworks. 

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- Workflow -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/England-Frameworks/Home/Technical-Framework/Workflow" class="nhsd-a-box-link " aria-label="Workflow">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Workflow</h1>
                                    <p class="nhsd-t-body-s">How HL7 FHIR can be used to automate Care Coordination and Communication at all stages of a Patients Journey/Pathway. This will often align to existing fax/email interactions.</p>
                                     <p class="nhsd-t-body-s">FHIR Workflow, IHE Scheduled Workflow (SWF) and HL7 v2 Admission Discharge and Transfers (ADT) </p>
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
            <!-- Query API -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/England-Frameworks/Home/Technical-Framework/Query-API" class="nhsd-a-box-link " aria-label="Query API">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Query API</h1>
                                    <p class="nhsd-t-body-s">How HL7 FHIR can be used to provide read only open API access to patient data stored in existing patient repositories. This API is designed to be used by patient or practitioners at any stage of a patient journey/pathway</p>
                                     <p class="nhsd-t-body-s">IHE Query for Existing Data (QED) and HL7 UK Core FHIR Access</p>
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
           <!-- Structured Data Capture -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/England-Frameworks/Home/Technical-Framework/Structured-Data-Capture" class="nhsd-a-box-link " aria-label="Structured Data Capture">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Structured Data Capture</h1>
                                    <p class="nhsd-t-body-s">Patient pathways and journeys include a high number of data entry applications and forms. Structured Data Capture describes how HL7 FHIR can be used to automatically populate these forms with existing data, provide common form definintions and share completed forms.</p>
                                    <p class="nhsd-t-body-s">IHE and FHIR Structured Data Capture (SDC) and openEHR Archetypes/Templates.</p>
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
            <!-- Health Administrtion -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/England-Frameworks/Home/Technical-Framework/Health-Administration" class="nhsd-a-box-link " aria-label="Read the NHS England Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Health Administration</h1>
                                    <p class="nhsd-t-body-s">HL7 v2 Admission Discharge and Transfers (ADT), IHE Patient Demographic Queries (PDQ), Patient Identifier Cross-referencing (PIX) and Patient Master Identity Registry (PMIR)</p>
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
       
            <!-- Care Documents -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/England-Frameworks/Home/Technical-Framework/Shared-Clinical-Documents" class="nhsd-a-box-link " aria-label="Shared Clinical Documents">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Shared Clinical Documents</h1>
                                    <p class="nhsd-t-body-s">How HL7 FHIR can be used to enable sharing of patient health and social care documents across a patient's journey/pathway</p>
                                    <p class="nhsd-t-body-s">IHE Cross-Enterprise Document Sharing (XDS and MHD)</p>
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
