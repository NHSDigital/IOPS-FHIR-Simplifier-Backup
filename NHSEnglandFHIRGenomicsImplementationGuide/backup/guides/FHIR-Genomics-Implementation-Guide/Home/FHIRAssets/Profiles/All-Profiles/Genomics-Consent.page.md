---
topic: Profile-Genomics-Consent
issue: Genomics-Consent
subject: http://hl7.org/fhir/StructureDefinition/Consent
expand: yes
---

# {{variable:issue}}

Only expected to be used for wrapping Record of Discussion resources within the WGS pathway. Consent for testing is implied through submission of a test to the Genomic Order Management service.

Only a minimal amount of mandatory information needs to be populated. 

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/Consent](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Consent&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <br />
            <ul>
            <li> {{pagelink:Consent-RoD-PheobeSmitham-Example}} </li>
            <li>  {{pagelink:Consent-RoD-PheobeSmithamFather-Example}} </li>
            <li> {{pagelink:Consent-RoD-PheobeSmithamMother-Example}} </li>
            <li> {{pagelink:Consent-RoD-PheobeSmithamYoungPersonAssentForm-Example}} </li>
            <li>  {{pagelink:Consent-RoDYoungPersonAssentFormAvailable-Example}} </li>
            <li> {{pagelink:Consent-RoDAvailable-Example}} </li>
            <li> {{pagelink:Consent-RoDToFollow-Example}} </li>
            <li> {{pagelink:Consent-RoD-PheobeSmithamAttachmentURL-Example}} </li>
            <li> {{pagelink:Consent-RoD-PheobeSmithamAttachmentData-Example}}</li>
            </ul>
    
        </div>

<div id="Mappings" class="tabcontent">
<br>
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Consent.sourceAttachment</td><td>RoD - Record of discussion form - copy attached</td><td>CON-19 (for OML, included in RoD, referenced from NTE-3)</td></tr>
                    <tr><td>Consent.status</td><td>RoD - Patient conversation taken place, ROD form to follow</td><td>Inferred through CON-19 value (for OML, included in RoD, referenced from NTE-3)</td></tr>
                </table>
        </div>


<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#status">status</a>
- <a href="#scope">scope</a>
- <a href="#category">category</a>
- <a href="#source">source\[x\]</a>
- <a href="#policy">policy</a>
- <a href="#provision">provision</a>

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
SHALL be present. Fixed code of 'proposed' where consent discussion has taken place but RoD form has not been provided alongside test order. 'draft' if discussion has not yet taken place and 'active' for completed RoD, regardless of whether the patient has consented to information sharing (responses to specific consent statements SHOULD be recorded in the RoD itself).

```json
"status": "proposed",
```

<a name="scope"></a>
<h4 class='additional-Guidance-Submenu'> scope </h4>
For WGS RoD this SHALL be fixed to the below code:

```json
"scope": {
        "coding":  [
            {
                "system": "http://terminology.hl7.org/CodeSystem/consentscope",
                "code": "research",
                "display": "Research"
            }
        ]
    },
```

<a name="category"></a>
<h4 class='additional-Guidance-Submenu'> category </h4>
For WGS RoD this SHALL be fixed to the below code:

```json
"category":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/consentcategorycodes",
                    "code": "research",
                    "display": "Research Information Access"
                }
            ]
        }
    ],
```

<a name="source"></a>
<h4 class='additional-Guidance-Submenu'> source[x] </h4>
SHALL be present for RoD entities. The Source element MAY either be a pointer to the location of the PDF version of the RoD, either hosted by the source/client system, accessed via NRL or embedded within the message payload, base64 encoded (using sourceAttachment), or a reference to a QuestionnaireResponse resource (using sourceReference), if this has been collected in a structured format, using the {{pagelink:Questionnaire-Genomic-Testing}} RoD template.

```json
"sourceReference": {
        "reference": "QuestionnaireResponse/QuestionnaireResponse-RoD-Example"
    },
```

<a name="policy"></a>
<h4 class='additional-Guidance-Submenu'> policy </h4>
For WGS RoD this SHALL be fixed to the below uris:

```json
"policy":  [
        {
            "authority": "https://www.england.nhs.uk",
            "uri": "https://www.england.nhs.uk/publication/nhs-genomic-medicine-service-record-of-discussion-form"
        }
    ]
```

<a name="provision"></a>
<h4 class='additional-Guidance-Submenu'> provision </h4>
Used to reference the ServiceRequest the Consent applies to. SHALL be present where the consent only applies to a specific test.

```json
"provision": {
        "data": [
            {
                "meaning": "instance",
                "reference": { 
                    "reference":  "ServiceRequest/ServiceRequest-WGSTestOrderForm-Example"
                }
            }
        ]
    }
```
---