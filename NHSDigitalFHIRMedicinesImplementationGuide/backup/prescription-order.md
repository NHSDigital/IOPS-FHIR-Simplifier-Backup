## prescription-order


This message definition describes the rules for a **Prescription Order** interactions used in a FHIR Messaging exchange.  

<div class="nhsd-t-col-xs-12 nhsd-t-col-s-8">
    <div class="nhsd-o-card-list">
        <div class="nhsd-t-grid nhsd-!t-no-gutters">
            <div class="nhsd-t-row nhsd-o-card-list__items ">
                <div class="nhsd-t-col-12 nhsd-!t-no-gutters">
                    <article class="nhsd-m-card">
                        <a href="https://simplifier.net/guide/NHSDigital/FHIRMessaging" class="nhsd-a-box-link"
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

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Definition" role="tab" data-toggle="tab">Definition</a>
        </li>
        <li role="presentation">
            <a href="#JSON" role="tab" data-toggle="tab">JSON</a>
        </li>
         <li role="presentation">
            <a href="#XML" role="tab" data-toggle="tab">XML</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
    </ul>
    
    <div class="tab-content snippet">
        <div id="Definition" role="tabpanel" class="tab-pane active">

<br>

### Event Coding 

|System|Code|
|--
| {{link:https://fhir.nhs.uk/CodeSystem/message-event}} | prescription-order |

|Category|
|--
| consequence |

<br>


### MessageHeader

The FHIR Message Bundle **MUST** contain one MessageHeader resource conforming to [NHSDigital-MessageHeader](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MessageHeader.guide.md)

<br>

## Focus

|Profile|Min|Max|Notes|
|--
|  {{pagelink:NHSDigital-MedicationRequest.md}} | 1 | 4 ||
|  [NHSDigital-Patient](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Patient.guide.md) | 1 | 1 ||
|  [NHSDigital-PractitionerRole](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-PractitionerRole.guide.md) | 1 | * ||
|  [NHSDigital-CommunicationRequest](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-CommunicationRequest.guide.md) | 0 | * | This is for legacy support of patient messages (e.g. surgery opening times and repeat medication lists) as would appear on printed prescriptions. It is also used in primary care to communicate repeat medication lists. |
| [NHSDigital-Provenance](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Provenance.guide.md) |   0 | 1 | <b>MUST</b> for `$process-message` API. This holds the electronic prescription signature. |
|  [NHSDigital-Location](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Location.guide.md) | 1 | * | Prescription Address|


| Response Required | 
|--
| on-error |

| Allowed Responses | 
|--
| {{pagelink:prescription-order-update}} |

</div>
<div id="Examples" role="tabpanel" class="tab-pane">
<table>
<tr><td>
{{pagelink:PrescriptionOrderHomecarePrepare.md}} homecare example (used with `prepare` endpoint to obtain digital signature
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderHomecareRepeatMedication.md}} homecare repeat medication example with digital signature
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderHomecareusingMedicationresource.md}} homecare example using a Medication resource instead of a CodeableConcept.
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderOutpatientAcuteMedication.md}} Outpatient example with acute medication. 
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderOutpatientMultipleMedications.md}} Outpatient acute four item prescription, including one Schedule 2 controlled drug
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderOutpatientEndorsement.md}} Outpatient example with endorsed acute medication. 
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderCommunityNoNominatedPharmacy.md}} Community repeat dispensing prescription with no nominated pharmacy.
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderCommunityNursePrescriber.md}} Community acute prescription, nurse prescriber with legal authenticator.
</td></tr>
<tr><td>
{{pagelink:PrescriptionOrderGPwithpatientnotes.md}} GP acutue prescription with patient notes and repeat medications list.
</td></tr>
</table>
</div>
        <div id="XML" role="tabpanel" class="tab-pane">
  {{xml:https://fhir.nhs.uk/MessageDefinition/prescription-order}}
        </div>
        <div id="JSON" role="tabpanel" class="tab-pane">
  {{json:https://fhir.nhs.uk/MessageDefinition/prescription-order}}
        </div>
      </div>
      </div>


