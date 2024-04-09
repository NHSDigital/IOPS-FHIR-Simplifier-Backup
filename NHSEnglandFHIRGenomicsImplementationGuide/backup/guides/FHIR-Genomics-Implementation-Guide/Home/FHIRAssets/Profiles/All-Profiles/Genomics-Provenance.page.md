## {{page-title}}

The Genomics Provenance SHOULD be provided alongside updates to controlled documents such as ServiceRequests and DiagnosticReports by integrated systems on any update operation to ensure auditability for any changes to resources.

The draft profile for the UK Core Provenance is provided below for completeness.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Provenance](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Provenance&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

<br>

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
        <li role="presentation">
            <a href="#Mappings" role="tab" data-toggle="tab">Mappings</a>
        </li>
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Provenance, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Provenance}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Provenance, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Provenance, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                        {{pagelink:Provenance-NonWGSTestOrderFormCancellation-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Provenance-NonWGSTestOrderFormUpdated-SolidTumor-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Provenance-NonWGSTestOrderForm-FetalScenario-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Provenance-ServiceRequestUpdate-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Provenance-WGSTestOrderForm-DirectToLab-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Provenance-WGSTestOrderForm-TrioTestingProbandFather-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='http://hl7.org/fhir/StructureDefinition/Provenance'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='http://hl7.org/fhir/StructureDefinition/Provenance' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#target">target</a>
- <a href="#recorded">recorded</a>
- <a href="#reason">reason</a>
- <a href="#agent">agent</a>
- <a href="#signature">signature</a>

<a name="target"></a>
#### target
SHALL be provided. This SHOULD be a reference to the resource on the central GMS system that was updated.
```json
"target":  [
        {
            "reference": "ServiceRequest/ServiceRequest-SavedTestOrderUpdated-Example"
        }
    ],
```

<a name="recorded"></a>
#### recorded
SHALL be provided, the date/time when the update took place.
```json
"recorded": "2023-08-10T11:10:00Z",
```

<a name="reason"></a>
#### reason
The reason why the update took place. If the codes provided by HL7 are not granular enough, or additional notes need to be recorded detailing the reasoning behind a change, this SHOULD be added as text to 'reason.text'.
```json
"reason":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/v3-ActReason",
                    "code": "TREAT",
                    "display": "treatment"
                }
            ],
            "text": "Test inappropriate for patient"
        }
    ],
```

<a name="agent"></a>
#### agent
The user which performed the change, as identified through CIS2 authentication token.
```json
"agent":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "http://terminology.hl7.org/CodeSystem/provenance-participant-type",
                        "code": "author",
                        "display": "Author"
                    }
                ]
            },
            "who": {
                "reference": "PractitionerRole/PractitionerRole-TestClinicalScientist-Example",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/sds-user-id",
                    "value": "9999999997"
                }
            }
        }
    ],
```

<a name="signature"></a>
#### signature
Signed, encrypted copy of the document, for validation that the document has not been tampered with (the requirement to include this field has noot yet been validated).
```json
 "signature":  [
        {
            "type":  [
                {
                    "system": "urn:iso-astm:E1762-95:2013",
                    "code": "1.2.840.10065.1.12.1.15",
                    "display": "Addendum Signature"
                }
            ],
            "when": "2023-08-10T11:10:00Z",
            "who": {
                "reference": "PractitionerRole/PractitionerRole-TestClinicalScientist-Example",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/sds-user-id",
                    "value": "9999999997"
                }
            },
            "data": "DQo8U2lnbm...F0dXJlPg0K"
        }
    ]
```