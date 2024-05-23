## {{page-title}}

PractitionerRole resources SHOULD be used where information about both a practitioner and their role within a specific organization is required, e.g. as the ServiceRequest.requestor.

References to Practitioner and Organization resources SHOULD only be made via identifier, rather than appending Practitioner and Organization resources to test order bundles. Issues with referencing via identifier SHOULD be reported to the NHS England Genomics Unit for investigation.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
                    {{pagelink:PractitionerRole-AnnaLaneKingstonPathology-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-EugeneSmith-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-EugeneSmithLeedsSTH-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-GeneSmithENT-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-HazelSmithKingstonPathology-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-HazelSmithPathology-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-HazelSmithRenal-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-JamesTaylorKingstonPathology-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-LoisLane-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-LoisLaneKingstonClinicalGenetics-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-LucyHale-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-MarySmith-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:PractitionerRole-OscarShields-Example}}
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
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>PractitionerRole.practitioner</td><td>Requestor - Full name, Requestor - Professional registration number, Requestor - Professional registration number type, Additional contact - Full name, Additional contact - Professional registration number, Additional contact - Professional registration number type, Patient - GP full name, Patient - GP GMC number, Previous genomic report - Report performer full name, Previous genomic report - Original requester full name, Previous non genomic report - Report performer full name, Previous non genomic report - Original requester full name</td><td>ORC-12, ORC-12.1, ORC-12.9, Additional STF segment (STF-3), possibly referenced from the STF segment for the requester via STF-14, STF-2.1, STF-2.3, PD1-4.2 and PD1-4.3, PD1-4.1, OBX-16, ORC-12</td></tr>
                    <tr><td>PractitionerRole.code</td><td>Requestor - Job Title, Additional contact - Job Title</td><td>STF-18</td></tr>
                    <tr><td>PractitionerRole.specialty</td><td>Requestor - Current Specialty, Requestor - Department name, Additional contact - Current Specialty, Additional contact - Department name</td><td>PRA-5, STF-8</td></tr>
                    <tr><td>PractitionerRole.telecom</td><td>Requestor - Phone, Requestor - Email address, Requestor - Genomic report delivery method, Requestor - Central email for address and reporting (many), Additional contact - Phone, Additional contact - Email address, Additional contact - Genomic report delivery method, Additional contact - Central email for address and reporting (many)</td><td>ORC-14, STF-15, STF-16, STF-10</td></tr>
                    <tr><td>PractitionerRole.organization</td><td>Requestor - Organization name, Requestor - Organization address, Requestor - Organization ODS code, Additional contact - Organization name, address and ODS code, Additional contact - Organization address, Additional contact - Organization ODS code, Patient - GP Practice ODS Code, Previous genomic report - Report performer organisation ODS code, Previous genomic report - Original requester organisation ODS code, Previous non genomic report - Report performer organisation ODS code, Previous non genomic report - Original requester organisation ODS code</td><td>ORC-21, ORC-22, ORC-21.10, STF-9.2, STF-11, STF-9.1, PD1-4.14, OBX-23.10</td></tr>
                    <tr><td>PractitionerRole.healthcareService</td><td>PLCM activity - ODS code of the laboratory site delivering requested test, PLCM activity - Commissioned service category code</td><td>AFF-2.10 associated with performing organization, Derived from STF-8 for requester</td></tr>
                </table>
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
Additionally, where are there multiple Practitioners involved in providing care, the contact details for each Practitioners for that location (or service) SHOULD be specified.
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