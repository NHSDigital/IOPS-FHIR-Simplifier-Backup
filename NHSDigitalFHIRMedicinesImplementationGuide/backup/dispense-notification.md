## dispense-notification

This message definition describes the rules for a **Dispense Notification** interactions used in a FHIR Messaging exchange.  

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
| {{link:https://fhir.nhs.uk/CodeSystem/message-event}} | dispense-notification |


|Category|
|--
| notification |

<br>

### MessageHeader

The FHIR Message Bundle **MUST** contain one MessageHeader resource conforming to [NHSDigital-MessageHeader](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-MessageHeader.guide.md)

<br>

### Focus


|Profile|Min|Max|Notes|
|--
|  {{pagelink:NHSDigital-MedicationDispense.md}} | 1 | * | |
| [NHSDigital-Patient](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Patient.guide.md) | 0 | 1 | A traced NHS Number identifier **MUST** be present, untraced NHS Numbers are not permitted. This can be conveyed in two ways, as identifier reference in the subject element of the `MedicationDispense` resource or as an identifier in a Patient resource. If a NHS Number identifier is referenced in the `MedicationDispense` resources then a `Patient` resource **SHOULD NOT** be present in the Bundle.  |

</div>
<div id="Examples" role="tabpanel" class="tab-pane">

- {{pagelink:prescription-dispense-notification.md}} Partial dispensed prescription

- {{pagelink:1stdispenseevent-partial.md }} Example from a sequence of notifications.
- {{pagelink:2nddispenseevent-partial.md }} Example from a sequence of notifications.
- {{pagelink:3rddispenseevent-completed.md }} Example from a sequence of notifications.
- {{pagelink:1stdispenseevent-partialwithPatientResource}} Example from a sequence of notifications with an included FHIR Patient resource.
</div>
<div id="XML" role="tabpanel" class="tab-pane">
  {{xml:https://fhir.nhs.uk/MessageDefinition/pharmacy-dispense}}
</div>
<div id="JSON" role="tabpanel" class="tab-pane">
  {{json:https://fhir.nhs.uk/MessageDefinition/pharmacy-dispense}}
</div>
</div>
</div>