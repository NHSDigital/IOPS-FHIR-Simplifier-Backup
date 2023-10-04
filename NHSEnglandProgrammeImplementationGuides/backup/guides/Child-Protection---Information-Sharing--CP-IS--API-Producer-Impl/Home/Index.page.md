## What is CP-IS?

## Child Protection - Information Sharing Implementation Guide

This specification provides guidance for implementing Child Protection information exchange between NHS Spine and healthcare IT systems in scheduled and unscheduled care settings.

At this stage of development, only the following HL7v3 care communications will be converted to FHIR-based message exchanges:-

- QUPC_MT000006GB01 CP-IS NHS Query
- REPC_MT000007GB01 CP-IS NHS Query response

This guide specifies the API requirements for API Consumer applications - healthcare applications that consume information provided by the national CP-IS API service.

## Introduction

The Child Protection Information Sharing (CP-IS) initiative aims to share information between NHS clinicians and Local Authority social care practitioners relating to children with either Child Protection, Looked After or Unborn Child care plans. 

Relevant data is uploaded to NHS Spine by a Local Authority system where it can be queried by NHS clinicians/practitioners. A response is returned to the practitioner showing any plans in existence for the specified NHS number and also the details of any device or person who has previously submitted a query against that NHS number. Further details of the [API design](https://simplifier.net/guide/ChildProtection/Designoverview) are available.

### Use cases

Current uses are:-

- A clinician treating a child during an unscheduled care episode submits a query to CP-IS to see if any child protection information exists.The querying clinician is a registered "smartcard" user.

CP-IS has been extended to scheduled care settings:

- A clinician seeing a child/pregnant woman for scheduled care wishes to know if the child has a care plan, in order to provide contextual care for that person, without alerting the social worker.
- A clinician wishes to be able to alert a social care practitioner, if a child/pregnant woman on a plan misses a scheduled appointment, so that the practitioner can take appropriate action.

Details of further benefits and <a href="https://digital.nhs.uk/services/child-protection-information-sharing-project/benefits-of-child-protection-information-sharing" class="external">case studies</a> are available.

### API Producer/Consumer

Our Implementation guides use the terms API Consumer and API Producer, in line with NHS England's API Management team, to identify Client and Server applications integrating across an API. This is a common pattern for national interfaces.

An API Consumer, typically a healthcare worker-facing application or ‘point-of-care’ application, connects via an API (Application Programming Interface)to request and receive information in ‘real time’. In CP-IS, API Consumers are healthcare applications wanting to integrate with Spine to provide Child protection information.

An API Producer develops and exposes an API that delivers the relevant information on request. Within CP-IS, the API Producer is Spine.

### Child Protection - Information Sharing (CP-IS) API Producer Implementation Guidance

This guide provides the specification and Implementation guidance for the API Producer application - i.e. the NHS Spine CP-IS Server.

### Related Guides

Current HL7v3 implementations are for both scheduled ('silent read') and unscheduled care settings. [<a href="https://digital.nhs.uk/services/child-protection-information-sharing-project/cp-is-domain-message-specification" class="external">HL7 V3 message specification</a>].  


<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- UK Core --> 
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/uk-core-implementation-guide?version=1.0.0" class="nhsd-a-box-link "
                        aria-label="Read the UK Core Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">UK Core FHIR Guidance</h1>
                                    <p class="nhsd-t-body-s">This guide is to be used as the base for implementing FHIR in the UK.</p>
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
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- PDS --> 
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir" class="nhsd-a-box-link "
                        aria-label="Read the PDS Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">PDS FHIR Guidance</h1>
                                    <p class="nhsd-t-body-s">This guide is to be used as the base for verifying an NHS number</p>
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