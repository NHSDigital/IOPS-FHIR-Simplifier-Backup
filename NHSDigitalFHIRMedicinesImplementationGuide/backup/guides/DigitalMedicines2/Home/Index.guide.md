# Home

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><b> Important:</b>This is version 2.8.11-prerelease. For a full list of available versions, see the <a href="https://simplifier.net/guide/NHSDigital-Medicines/Home/Introduction/Directory">directory</a> of published versions </div>

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> We would like your feedback</h4>
Please complete this short feedback form <a href="https://forms.office.com/e/4eE3dDACDS">here </a>to help the Interoperability Standards Team produce 
specifications that meet your requirements 
</div>

This Implementation Guide is the **NHS Digital FHIR Medicines Implementation Guide** extension to the core [NHS Digital FHIR Implementation Guide](https://simplifier.net/guide/nhsdigital) which is derived from the [UK Core Implementation Guide V2](https://simplifier.net/guide/hl7fhirukcorer4release1/home).

This guide is to be used across NHS Digital FHIR R4 API's when implementing Medicines. It should be used in conjunction with the [Dose Syntax Implementation Guide](https://simplifier.net/guide/ukcoreimplementationguideformedicines/Home) which specifies the requirement for structured dose syntax in FHIR (R4).

<br>

### EPS 

The guide is core to the FHIR EPS API. An design overview for FHIR EPS can be found here:

- Design ({{pagelink:index-duplicate-49}})

Detailed EPS API documentation can be found here:

- [Electronic Prescription Service (FHIR) API](https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir)

---

<br>

### Resource Index

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="33%">Medications</th>
     <th data-no-sort width="33%">Workflow</th>
     <th data-no-sort width="33%">Billing</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:NHSDigital-MedicationDispense-duplicate-3}} 
    </td>
    <td>
   {{pagelink:NHSDigital-Task-duplicate-2}}
    </td>
     <td>
{{pagelink:NHSDigital-Claim-duplicate-4}}
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:NHSDigital-MedicationRequest-duplicate-3}} 
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
     <a href="https://simplifier.net/guide/UKCoreDevelopment2/ProfileUKCore-Medication">UKCore-Medication</a>
    </td>
    <td>
    </td>
     <td>
    </td>
   </tr>
   </tbody>
</table>

---

<br>

### Related NHS Digital Guides

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- NHS Digital Patient Administration --> 
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/NHSDigital" class="nhsd-a-box-link "
                        aria-label="Read the NHS Digital Base Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">NHS Digital Base</h1>
                                    <p class="nhsd-t-body-s">This guide is to be used as the base standard for implementing FHIR API's in NHS Digital.</p>
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

<br>

### Related Guides

<div class="nhsd-o-card-list">
    <div class="nhsd-t-grid">
        <div class="nhsd-t-row nhsd-o-card-list__items ">
         <!-- UK Core --> 
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/hl7fhirukcorer4release1/home" class="nhsd-a-box-link "
                        aria-label="Read the EPS Guidance">
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
            <!-- UK Core Medicines Guidance -->
            <div class="nhsd-t-col-xs-12 nhsd-t-col-s-4">
                <article class="nhsd-m-card">
                    <a href="https://simplifier.net/guide/ukcoreimplementationguideformedicines/home" class="nhsd-a-box-link "
                        aria-label="Read the UK Core Medicines Guidance">
                        <div class="nhsd-a-box nhsd-a-box--bg-light-grey">
                            <div class="nhsd-m-card__content_container">
                                <div class="nhsd-m-card__content-box">
                                    <h1 class="nhsd-t-heading-s">UK Core Medicines </h1>
                                    <p class="nhsd-t-body-s">This guide is provides additional guidance when implementing Medicines using FHIR in the UK.</p>
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

<br>

### FHIR RESTful API

FHIR is described as a [RESTful](https://www.hl7.org/fhir/http.html) specification based on common industry level use of the term REST. A set of **recommend** RESTful interactions are described in the *SearchParameters* section of the {{pagelink:CapabilityStatement-duplicate-3}}

---

<br>

### FHIR Messaging (Events)

FHIR Resources can be used in a traditional [messaging](https://www.hl7.org/fhir/messaging.html) context, much like HL7 v2. A set of **recommend** messaging interactions are listed below.


<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="33%">Prescription Messages</th>
     <th data-no-sort width="33%">Dispense Messages</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:prescription-order-duplicate-2}}
    </td>
    <td>
{{pagelink:dispense-notification-duplicate-3}}
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:prescription-order-update-duplicate-2}}
    </td>
    <td>
{{pagelink:dispense-notification-update-duplicate-2}}
    </td>
   </tr>
    <tr>
    <td>
{{pagelink:prescription-order-response-duplicate-2}}
    </td>
    <td>
    </td>
   </tr>
   </tbody>
</table>

---

<br>

<div class="nhsd-t-col-xs-12 nhsd-t-col-s-8">
    <div class="nhsd-o-card-list">
        <div class="nhsd-t-grid nhsd-!t-no-gutters">
            <div class="nhsd-t-row nhsd-o-card-list__items ">
                <div class="nhsd-t-col-12 nhsd-!t-no-gutters">
                    <article class="nhsd-m-card">
                        <a href="https://simplifier.net/guide/nhsdigital/Home/Guidance/FHIRMessaging-duplicate-3" class="nhsd-a-box-link"
                            aria-label="FHIR Messaging">
                            <div class="nhsd-a-box nhsd-a-box--bg-dark-green">
                                <div class="nhsd-m-card__content_container">
                                    <div class="nhsd-m-card__content-box">
                                        <p class="nhsd-t-heading-s">FHIR Messaging</p>
                                        <p class="nhsd-t-body-s">Learn more about traditional Messaging in a FHIR context</p>
                                    </div>
                                    <div class="nhsd-m-card__button-box">
                                        <span
                                            class="nhsd-a-icon nhsd-a-icon--size-s nhsd-a-icon--col-white nhsd-a-arrow">
                                            <svg xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMidYMid meet"
                                                aria-hidden="true" focusable="false" viewBox="0 0 16 16" width="100%"
                                                height="100%">
                                                <path d="M8.5,15L15,8L8.5,1L7,2.5L11.2,7H1v2h10.2L7,13.5L8.5,15z" />
                                            </svg>
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
</div>

---

<br>

### NHS Digital Developer API Catalouge

In the [NHS API Catalogue](https://digital.nhs.uk/developer/api-catalogue) see the following seections:

| Business Use |
|--
| Prescribing |
| Dispensing |
| Vaccinations |

