## {{page-title}}

PractitionerRole resources SHOULD be used where information about both a practitioner and their role within a specific organization is required, e.g. as the ServiceRequest.requestor.

References to Practitioner and Organization resources SHOULD only be made via identifier, rather than appending Practitioner and Organization resources to test order bundles. Issues with referencing via identifier SHOULD be reported to the NHS England Genomics Unit for investigation.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/PractitionerRole}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-LucyHale}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-GeneSmithENT-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-HazelSmithRenal-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole'
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
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#practitioner">practitioner</a>
- <a href="#organization">organization</a>
- <a href="#specialty">specialty</a>
- <a href="#telecom">telecom</a>

<a name="practitioner"></a>
#### practitioner
Users SHOULD reference practitioners using an appropriate naming system within the NHS (defined within the [NHS England IG](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Practitioner.guide.md?version=current#identifier). Display name MAY be included to aid readability and verification of included identifiers.
```json
 "practitioner": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/sds-user-id",
            "value": "9999999999"
        },
        "display": "Dr. Gene Smith"
    },
```

<a name="organization"></a>
#### organization
Users SHOULD reference organizations using an ODS code. Display name MAY be included to aid readability and verification of included identifiers.
```json
 "organization": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "RGT01"
        },
        "display": "Addenbrooke's Hospital"
    },
```

<a name="specialty"></a>
#### specialty
The specialty field SHOULD be used to record department for the requesting clinician, issues with the use of this field, including issues with the [bound UK Core ValueSet](https://fhir.hl7.org.uk/CodeSystem/UKCore-PracticeSettingCode) not representing certain departments SHOULD be reported to the NHS England Genomics Unit
```json
"specialty":  [
        {
            "coding":  [
                {
                    "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-PracticeSettingCode",
                    "code": "120",
                    "display": "Ear Nose and Throat"
                }
            ]
        }
    ],
```

<a name="telecom"></a>
#### telecom
The telecom field SHOULD be used to record contact details for the practitioner. For central mailboxes, e.g. those used for providing reports back to the requester, these SHOULD be marked with an appropriate 'contactpoint-comment' extension. 
```json
"telecom":  [
        {
            "system": "phone",
            "value": "01223586638"
        },
        {
            "system": "email",
            "value": "gene.smith@nhs.net"
        },
        {
            "system": "email",
            "value": "Add-tr.entsecretaries@nhs.net",
            "extension":  [
                {
                    "url": "http://hl7.org/fhir/StructureDefinition/contactpoint-comment",
                    "valueString": "reporting"
                }
            ]
        }
    ]
```