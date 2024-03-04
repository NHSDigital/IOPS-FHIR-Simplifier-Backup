## Introduction

**Important:** This is version 0.3.0. For the version history see {{pagelink:ReleaseNotes}}

This specification is currently defined as in "Discovery" and as such is provided for consultation and discussion. This project is being developed using an agile approach so iterative updates to content will be added on a regular basis. It is anticipated that the message specification and implementation guidance will be updated further following First of Type (FoT) implementation.

For further information please contact: [england.contactus@nhs.net](mailto:england.contactus@nhs.net)

The **FHIR Genomics IG** Specification defines a set of draft HL7 FHIR R4 profiles to support the exchange of genetic testing requests and results. **This release focuses on supporting improvements to the test ordering process for non-WGS and WGS genomic testing pathways identified to support piloting of a technical implementation to improve digital interoperability. Guidance on the content of results is restricted to return of a PDF using DiagnosticReport at this early stage, future releases will expand on structured genetic resulting data.**

This Specification supports the ability to request genomic testing and receive results in NHS primary and secondary care settings. The scope of this guide is NHS England, though the rules and constraints defined are expected to apply to UK-wide Genomic Testing. 

This Implementation Guide provides additional guidance, rules and constraints which extends the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current), currently STU2, to allow exchange of structured electronic test requests and responses. It is anticipated that the messaging specification and implementation guidance will be updated following First of Type (FoT) implementation.

Potential future releases may include support for:

- Other genetic pathways
- Structured reporting of results
- Pharmacogenomic data items
- Secondary use

---
## Scope

{{render:diagrams-scope}}

The scope of the interoperability project driving the FHIR specification is to enable electronic test requesting for all genomic tests (based on the Master Data Set (MDS)) to the receiving lab. The MDS has been built on an analysis of the data fields required by both the requester and lab, to accept and progress the test request. The MDS also reflects the NHS genomic medicine service Patient Level Contract Management (PLCM) dataset requirements (on-going process). 

The scope is based on the transfer and consumption of data between organisational boundaries as defined in the National Genomic Testing Process (NGTP). The scope of the interoperability project will also encompass delivery of test and sample status updates between organisations. 

The intention is to deliver a central broker component, which will coordinate the electronic comms required of each in-scope service mentioned. In addition, the broker would be made available to support automated test order routing from the requester to the receiving lab and allow manual routing between labs. 

{{render:diagrams-routing}}

In the future, support for the distribution of structured reports will be made available. However, in the first instance, the scope of authorised reports once issued, will remain binary (PDF), with the aim to move towards structured reporting available to consuming systems (EPRs/other pathology LIMS) as a follow-on development.

---
## Implementation Guide Overview

### {{pagelink:Home/Design}}

This section details the decisions and rationale behind the design of the Genomic Medicine Service.

{{pagelink:Home/Design/Designoverview.page.md}} provides an overview of the current state of the Genomic Testing Process and how this has been translated to an electronic process. 

{{pagelink:Home/Design/Current-State-vs-Future-State.page.md}} describes the intended future state of electronic test order messaging and updates.

{{pagelink:Home/Design/Interactions.page.md}} describes how these processes can translate to FHIR Workflow.

{{pagelink:Home/Design/Clinicalheadings}} provides guidance on how the Master Data Set for Genomics can be translated into both FHIR and HL7v2 elements.

{{pagelink:Home/Design/Clinical-Scenarios}} provides worked examples based on end to end test ordering processes in specific scenarios.

Other pages within this section provide further guidance around integration patterns and national services used to support the Genomic Testing process.

<br>

### {{pagelink:Home/Build}}

This section provides guidance on how to build valid FHIR payloads for interaction with the central Genomic Medicine Service.

{{pagelink:Home/Build/How-to-construct-Message-Bundles}} provides guidance on the makeup of the main transactions, creation of a test order and submission of a report.

{{pagelink:Home/Build/Alternative-Flows.page.md}} details how certain scenarios impact the interaction patterns.

{{pagelink:Home/Build/Authentication}} details how the API will be secured and how authorization is assessed.

Other Pages within this section provide further guidance around interactions with the API such as error handling.

<br>

### {{pagelink:Home/FHIRAssets}}

This section provides the FHIR conformance assets for interacting with the proposed Genomic Medicine Service.

{{pagelink:Home/FHIRAssets/Profiles}} details the UK Core profiles relevant for genomics, as well as specific guidance on how to populate pertinent elements.

{{pagelink:Home/FHIRAssets/CapabilityStatements}} details the intended functions supported by the central service, as well as the profiles each resource type should conform to.

Other pages within this section detail additional assets for use in Genomics.

<br>

### {{pagelink:Home/Examples}}

This section lists examples created to illustrate how to populate resources in certain clinical contexts, arranged by resource type. These examples are still in development, if further examples are required to support local use cases, or issues with examples are identified, please email [interoperabilityteam@nhs.net](mailto:interoperabilityteam@nhs.net).

---

## Related Guides

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- UK Core -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/ukcoreversionhistory/home?version=current" class="nhsd-a-box-link " aria-label="UK Core Version History">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">UK Core</h1>
                                    <p class="nhsd-t-body-s">UK Core FHIR Guidance</p>
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
            <!-- API Catalogue -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://digital.nhs.uk/developer/api-catalogue" class="nhsd-a-box-link " aria-label="View the NHS Digital API Catalogue">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS Digital API Catalogue</h1>
                                    <p class="nhsd-t-body-s">APIs which use the NHS Digital Implementation Guide</p>
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
           
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1?version=current" class="nhsd-a-box-link " aria-label="View the NHS England Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS England IG</h1>
                                    <p class="nhsd-t-body-s">NHS England Implementation Guide</p>
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
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/pathology-fhir-implementation-guide?version=0.1" class="nhsd-a-box-link " aria-label="Read the NHS Digital Pathology Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Pathology FHIR IG</h1>
                                    <p class="nhsd-t-body-s">NHS England Pathology FHIR Implementation Guide</p>
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
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://hl7.org/fhir/uv/genomics-reporting/index.html" class="nhsd-a-box-link " aria-label="Read the HL7 Genomic Reporting Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">Genomic Reporting IG</h1>
                                    <p class="nhsd-t-body-s">HL7 Clinical Genomics Working Group Genomic Reporting Implementation Guide STU2</p>
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

---

<h3 id="licence-heading">Licence</h3>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="Licence"><i class="fas fa-gavel"></i> Licensing and Publisher</h4>
<ul>
<li>
Copyright© 2023+ NHS England Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by NHS England Interoperability Team.
</ul>
</div>