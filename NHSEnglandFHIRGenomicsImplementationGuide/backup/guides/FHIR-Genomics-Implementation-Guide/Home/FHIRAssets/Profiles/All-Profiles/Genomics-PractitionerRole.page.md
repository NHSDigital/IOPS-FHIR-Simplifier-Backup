---
topic: Profile-UKCore-PractitionerRole
issue: UKCore-Practitioner
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole
expand: yes
---

PractitionerRole resources SHOULD be used where information about both a practitioner and their role within a specific organization is required, e.g. as the ServiceRequest.requestor.

References to Practitioner and Organization resources SHOULD only be made via identifier, rather than appending Practitioner and Organization resources to test order bundles. Issues with referencing via identifier SHOULD be reported to the NHS England Genomics Unit for investigation.

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole</a>(https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank"> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

        <div id="Examples" class="tabcontent">
            <br />
           <ul>

                    <li>
                    {{pagelink:PractitionerRole-AnnaLaneKingstonPathology-Example}}
                    </li>
                
                
                    <li>
                    {{pagelink:PractitionerRole-EugeneSmith-Example}}
                    </li>
                
                    <li>
                    {{pagelink:PractitionerRole-EugeneSmithLeedsSTH-Example}}
                    </li>
              
                    <li>
                    {{pagelink:PractitionerRole-GeneSmithENT-Example}}
                    </li>
                
                    <li>
                    {{pagelink:PractitionerRole-HazelSmithKingstonPathology-Example}}
                    </li>
                
                    <li>
                    {{pagelink:PractitionerRole-HazelSmithPathology-Example}}
                    </li>
              
                    <li>
                    {{pagelink:PractitionerRole-HazelSmithRenal-Example}}
                    </li>
               
                    <li>
                    {{pagelink:PractitionerRole-JamesTaylorKingstonPathology-Example}}
                    </li>
                
                    <li>
                    {{pagelink:PractitionerRole-LoisLane-Example}}
                    </li>
              
                    <li>
                    {{pagelink:PractitionerRole-LoisLaneKingstonClinicalGenetics-Example}}
                    </li>
              
                    <li>
                    {{pagelink:PractitionerRole-LucyHale-Example}}
                    </li>
               
                    <li>
                    {{pagelink:PractitionerRole-MarySmith-Example}}
                    </li>
             
                    <li>
                    {{pagelink:PractitionerRole-OscarShields-Example}}
                    </li>
                </ul>
        </div>
   
        <div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>PractitionerRole.practitioner</td><td>Requestor - Full name, Requestor - Professional registration number, Requestor - Professional registration number type, Additional contact - Full name, Additional contact - Professional registration number, Additional contact - Professional registration number type, Patient - GP full name, Patient - GP GMC number, Previous genomic report - Report performer full name, Previous genomic report - Original requester full name, Previous non genomic report - Report performer full name, Previous non genomic report - Original requester full name</td><td>ORC-12, ORC-12.1, ORC-12.9, PD1-4.2 and PD1-4.3, PD1-4.1, OBX-16, ORC-12</td></tr>
                    <tr><td>PractitionerRole.code</td><td>Requestor - Job Title, Additional contact - Job Title</td><td>CTD-1</td></tr>
                    <tr><td>PractitionerRole.specialty</td><td>Requestor - Current Specialty, Requestor - Department name, Additional contact - Current Specialty, Additional contact - Department name</td><td>Additional CTD-1 segments</td></tr>
                    <tr><td>PractitionerRole.telecom</td><td>Requestor - Phone, Requestor - Email address, Requestor - Genomic report delivery method, Requestor - Central email for address and reporting (many), Additional contact - Phone, Additional contact - Email address, Additional contact - Genomic report delivery method, Additional contact - Central email for address and reporting (many)</td><td>ORC-14</td></tr>
                    <tr><td>PractitionerRole.organization</td><td>Requestor - Organization name, Requestor - Organization address, Requestor - Organization ODS code, Additional contact - Organization name, address and ODS code, Additional contact - Organization address, Additional contact - Organization ODS code, Patient - GP Practice ODS Code, Previous genomic report - Report performer organisation ODS code, Previous genomic report - Original requester organisation ODS code, Previous non genomic report - Report performer organisation ODS code, Previous non genomic report - Original requester organisation ODS code</td><td>ORC-21, ORC-22, ORC-21.10, OBX-23.10</td></tr>
                    <tr><td>PractitionerRole.healthcareService</td><td>PLCM activity - ODS code of the laboratory site delivering requested test, PLCM activity - Commissioned service category code</td><td>Additional CTD-1 segments</td></tr>
                </table>
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
SHALL be present. Users SHOULD reference practitioners using an appropriate naming system within the NHS (defined within the [NHS England IG](https://simplifier.net/guide/NHSDigital/Home/FHIRAssets/AllAssets/Profiles/NHSDigital-Practitioner.guide.md?version=current#identifier). Display name MAY be included to aid readability and verification of included identifiers.
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
SHALL be present. Users SHOULD reference organizations using an ODS code. Display name MAY be included to aid readability and verification of included identifiers. Requester ODS codes SHOULD use the lowest level site code rather than trust code (most granular code available) where possible, to aid contact retrieval.
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