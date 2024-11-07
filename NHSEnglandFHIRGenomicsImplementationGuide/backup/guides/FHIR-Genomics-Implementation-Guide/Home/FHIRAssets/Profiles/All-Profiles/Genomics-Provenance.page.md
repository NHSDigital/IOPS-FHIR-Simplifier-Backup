---
topic: Profile-Genomics-Provenance
issue: Genomics-Provenance
subject: http://hl7.org/fhir/StructureDefinition/Provenance
expand: yes
---

# {{variable:issue}}

The Genomics Provenance SHOULD be provided alongside updates to controlled documents such as ServiceRequests and DiagnosticReports by integrated systems on any update operation to ensure auditability for any changes to resources.

It is not expected that updates which do not affect the clinical content of the document will need associated Provenance resources, e.g. addition of local identifiers (**though for the purporses of the Genomic Order Management Alpha, all updates to ServiceRequest and DiagnosticReport resources will be expected to have accompanying Provenance resources**). On material changes to controlled resources, ServiceRequest and DiagnosticReport, users SHOULD use the transaction endpoint on the server to bundle the updated resource and Provenance event into a single transaction.

The HL7 FHIR specification also provides the capability to attach a Provenance resource using a [custom header parameter](https://www.hl7.org/fhir/r4/provenance.html#header). Using this mechanism would allow clients to submit requests to the resource specific PUT enpoints for ServiceRequests and DiagnosticReports, while still aloowing changes to be captured within a Provenance resource using a single interaction. This mechanism will not be supported within the Genomic Order Management Alpha but will be investigated by the NHS England Genomics Unit for implementation in future phases.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Provenance](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Provenance&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}


<div id="Examples" class="tabcontent">
            <br>
<ul>
<li> {{pagelink:Provenance-NonWGSTestOrderFormCancellation-Example}} </li>
<li> {{pagelink:Provenance-NonWGSTestOrderFormUpdated-SolidTumor-Example}}  </li>
<li> {{pagelink:Provenance-NonWGSTestOrderForm-FetalScenario-Example}} </li>
<li> {{pagelink:Provenance-ServiceRequestUpdate-Example}} </li>
<li> {{pagelink:Provenance-WGSTestOrderForm-DirectToLab-Example}} </li>
<li> {{pagelink:Provenance-WGSTestOrderForm-TrioTestingProbandFather-Example}} </li>
</ul>
</div>

<div id="Mappings" class="tabcontent">
<!--
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
-->
</div>

<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#target">target</a>
- <a href="#recorded">recorded</a>
- <a href="#reason">reason</a>
- <a href="#agent">agent</a>
- <a href="#signature">signature</a>

<a name="target"></a>
<h4 class='additional-Guidance-Submenu'> target </h4>
SHALL be provided. This SHOULD be a reference to the resource on the central GMS system that was updated.

```json
"target":  [
        {
            "reference": "ServiceRequest/ServiceRequest-SavedTestOrderUpdated-Example"
        }
    ],
```

<a name="recorded"></a>
<h4 class='additional-Guidance-Submenu'> recorded </h4>
SHALL be provided, the date/time when the update took place.

```json
"recorded": "2023-08-10T11:10:00Z",
```

<a name="reason"></a>
<h4 class='additional-Guidance-Submenu'> reason </h4>
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
<h4 class='additional-Guidance-Submenu'> agent </h4>
SHOULD be provided where actions are user initiated. The user which performed the change, as identified through CIS2 authentication token.

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
<h4 class='additional-Guidance-Submenu'> signature </h4>
Signed, encrypted copy of the document, for validation that the document has not been tampered with (the requirement to include this field has not yet been validated).

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
---