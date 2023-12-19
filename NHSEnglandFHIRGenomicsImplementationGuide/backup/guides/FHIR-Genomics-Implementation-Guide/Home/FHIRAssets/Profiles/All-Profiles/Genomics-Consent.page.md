## {{page-title}}

Only expected to be used for wrapping Record of Discussion resources within the WGS pathway.

Only a minimal amount of mandatory information needs to be populated. 

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Consent}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Consent-MichaelJonesConsent}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Consent-MichaelJonesConsent-Minimal}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Consent-RoDAvailable-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Consent-RoDToFollow-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
    </div>
</div>


### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#status">status</a>
- <a href="#scope">scope</a>
- <a href="#category">category</a>
- <a href="#source">source\[x\]</a>
- <a href="#policy">policy</a>

<a name="status"></a>
#### status
Fixed code of 'proposed' where consent discussion has taken place but RoD form has not been provided alongside test order. 'draft' if discussion has not yet taken place and 'active' for completed RoD, regardless of whether the patient has consented to information sharing (responses to specific consent statements SHOULD be recorded in the RoD itself).
```json
"status": "proposed",
```

<a name="scope"></a>
#### scope
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
#### category
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
#### source\[x\]
The Source element MAY either be a pointer to the location of the PDF version of the RoD, either hosted by the source/client system, accessed via NRL or embedded within the message payload, base64 encoded (using sourceAttachment), or a reference to a QuestionnaireResponse resource (using sourceReference), if this has been collected in a structured format, using the {{pagelink:Questionnaire-Genomic-Testing}} RoD template.
```json
"sourceReference": {
        "reference": "QuestionnaireResponse/QuestionnaireResponse-RoD-Example"
    },
```

<a name="policy"></a>
#### policy
For WGS RoD this SHALL be fixed to the below uris:
```json
"policy":  [
        {
            "authority": "https://www.england.nhs.uk",
            "uri": "https://www.england.nhs.uk/publication/nhs-genomic-medicine-service-record-of-discussion-form"
        }
    ]
```