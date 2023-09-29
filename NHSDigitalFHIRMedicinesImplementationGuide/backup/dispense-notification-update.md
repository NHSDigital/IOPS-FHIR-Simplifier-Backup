## dispense-notification-update

This message definition describes the rules for a **Dispense Notification Update** interactions used in a FHIR Messaging exchange.  

<div class="nhsd-t-col-xs-12 nhsd-t-col-s-8">
    <div class="nhsd-o-card-list">
        <div class="nhsd-t-grid nhsd-!t-no-gutters">
            <div class="nhsd-t-row nhsd-o-card-list__items ">
                <div class="nhsd-t-col-12 nhsd-!t-no-gutters">
                    <article class="nhsd-m-card">
                        <a href="https://simplifier.net/guide/NHSDigital/FHIRMessaging" class="nhsd-a-box-link"
                            aria-label="Access the EPS prescription tracker">
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
| {{link:https://fhir.nhs.uk/CodeSystem/message-event}} | dispense-notification-update |



|Category|
|--
| notification |

<br>

### MessageHeader

The FHIR Message Bundle **MUST** contain one MessageHeader resource conforming to [NHSDigital-MessageHeader](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles//NHSDigital-MessageHeader.guide.md)

The structure on this message is exactly the same as {{pagelink:dispense-notification}} 
with the extension [Extension-replacementOf](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MessageHeader.guide.md#replacementOf) 
 mandatory, this points to the `Bundle.identifier` of the updated `dispense-notification` Message.

<br>

### Focus

|Profile|Min|Max|Notes|
|--
|  {{pagelink:NHSDigital-MedicationDispense.md}} | 1 | 4 | |
| [NHSDigital-Patient](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Patient.guide.md) | 0 | 1 | A traced NHS Number identifier **MUST** be present, untraced NHS Numbers are not permitted. This can be conveyed in two ways, as identifier reference in the subject element of the `MedicationDispense` resource or as an identifier in a Patient resource. If a NHS Number identifier is referenced in the `MedicationDispense` resources then a `Patient` resource **SHOULD NOT** be present in the Bundle.  |
| NHSDigital-Practitioner | 0 | 0 | **MUST NOT** be present in the Bundle. References to Practitioner **MUST** use identifier refernces, acceptable identifiers are listed in the [NHSDigital-Practitioner](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Practitioner.guide.md) profile  |
| NHSDigital-PractitionerRole | 0 | 0 | **MUST NOT** be present in the Bundle. References to PractitionerRole **MUST** use identifier refernces, acceptable identifiers are listed in the  [NHSDigital-PractitionerRole](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-PractitionerRole.guide.md) profile |
| NHSDigital-Organization | 0 | 0 | **MUST NOT** be present in the Bundle. References to Practitioner **MUST** use identifier refernces (ODS/ANANA Codes), acceptable identifiers are listed in the [NHSDigital-Organization](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Organization.guide.md) profile |

</div>
<div id="Examples" role="tabpanel" class="tab-pane">

- {{pagelink:3rddispenseevent-update}}

</div>
<div id="XML" role="tabpanel" class="tab-pane">
  {{xml:https://fhir.nhs.uk/MessageDefinition/dispense-notification-update}}
</div>
<div id="JSON" role="tabpanel" class="tab-pane">
  {{json:https://fhir.nhs.uk/MessageDefinition/dispense-notification-update}}
</div>
</div>
</div>