---
topic: Profile-UKCore-Patient
issue: UKCore-Patient
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient
expand: yes
---

## StructureDefinition {{variable:issue}}

The focal resource for recording who a test order and genomic report are for.

It is expected that client's will need to post Patient resources to the central GMS as some demographic information specific to Genomics will not have been captured within other systems such as PDS.

**For patients included within PDS, it is expected source systems SHOULD only send genomic specific information not recorded against PDS, e.g. birthSex, genomic specific identifiers and a link to the PDS record, as well as the NHS number identifier. (NOTE: examples provided for patient resources are fully expanded to illustrate how information should be structured but any infomation already recorded by PDS SHOULD NOT be duplicated within the genomic order management services). Querying patient demographic information, will be supported using the search parameters provided by the Genomic Order Management Service, whch will pass through parameters to PDS where demographics are stored against this system. Client systems will then be required to follow the PDS link within the Genomics-Patient record to retrieve the PDS patient.**

**It is a requirement on source systems that patient NHS numbers are traced and verified with PDS, if the patient is registered with PDS, before creation of patient resources on the Genomic Order Management broker** 

**For patients not included on PDS, e.g. private/overseas patients or fetal records, the requester SHOULD send all information necessary to facilitate testing and interpretation of the request. Where this patient is later registered on PDS, identified through assignment of an NHS number, demographic details SHALL be stripped from the genomic record to avoid data duplication.**

Alternatively, systems MAY opt to include pointers to the Patient resource on their local system, though the mechanism preferred by the NHS England Genomics Unit has yet to be decided.

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank">https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient </a> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Patient-AnitaLambertsDeceasedPatient-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-AnitaLambertsMotherDeceasedPatient-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-DemeizaSeo-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-FayMutlow-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-FoetusOfRyanneBoulder-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-JamesMetcalfe-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-KayBurbridge-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-MeirLiebermanPDS-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-LindsaySorrellPDS-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-LindsaySorrell-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-MeirLieberman-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-PatrickSammy-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-PheobeSmitham-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-PheobeSmithamFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-PheobeSmithamMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-RyanneBoulder-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-RyanneBoulderPartner-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-SalimaPomfrets-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-TimMclullichs-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-ZelmaHadjkiss-Example}}
                    </td>
                </tr>
            </table>
        </div>
  
        <div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Patient.identifier</td><td>Patient - NHS number, Patient - Local identifier, Patient - Pedigree/Family Identifier, Fetus - Local identifier, Previous genomic report - Patient's NHS number, Previous genomic report - Patient's alternative identifier, Previous genomic report - Patient's clinical genetics number, Previous genomic report - Patient's pedigree number</td><td>PID-3</td></tr>
                    <tr><td>Patient.extension:nhsNumberUnavailableReason</td><td>Patient - Reason for unavailable NHS number, Patient - Withheld identity reason</td><td>N/A, could use PID-32 as surrogate</td></tr>
                    <tr><td>Patient.name.prefix</td><td>Patient - Title</td><td>PID-5.5</td></tr>
                    <tr><td>Patient.name.given</td><td>Patient - First name, Previous genomic report - Patient's first name</td><td>PID-5.2</td></tr>
                    <tr><td>Patient.name.family</td><td>Patient - Surname, Previous genomic report - Patient's surname</td><td>PID-5.1</td></tr>
                    <tr><td>Patient.birthDate</td><td>Patient - Date of birth, PLCM activity - Patient age at activity date, Previous genomic report - Patient's date of birth</td><td>PID-7, Age derived from the difference between PID-7 and TQ1-7 for the relevant activity</td></tr>
                    <tr><td>Patient.address</td><td>Patient - Address, Previous genomic report - Patient's address</td><td>PID-11</td></tr>
                    <tr><td>Patient.address.postalCode</td><td>Patient - Postcode, Previous genomic report - Patient's post code</td><td>PID-11.5</td></tr>
                    <tr><td>Patient.address.country</td><td>Patient - Country, Previous genomic report - Patient's country</td><td>PID-11.6</td></tr>
                    <tr><td>Patient.deceasedBoolean</td><td>Patient - Life status at time of request</td><td>PID-30</td></tr>
                    <tr><td>Patient.deceasedDateTime</td><td>Patient - Date of death</td><td>PID-29</td></tr>
                    <tr><td>Patient.extension:EthnicCategory</td><td>Patient - Ethnicity</td><td>PID-22</td></tr>
                    <tr><td>Patient.extension:birthSex</td><td>Patient - Sex assigned at birth</td><td>PID-8</td></tr>
                    <tr><td>Patient.extension:patient-genderIdentity</td><td>Patient - Gender Identity</td><td>N/A - not part of the HL7v2 standard, though PID-8 or an OBX segment could be used</td></tr>
                    <tr><td>Patient.generalPractitioner</td><td>Patient - GP Practice ODS Code, Patient - GP full name, Patient - GP GMC number</td><td>PD1-4</td></tr>
                    <tr><td>Patient.gender</td><td>Fetus - Observed sex</td><td>PID-8</td></tr>
                </table>
</div>


<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>
<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#extension:UKCore-birthSex">extension:UKCore-birthSex</a>
- <a href="#identifier">identifier</a>
- <a href="#generalPractitioner">generalPractitioner</a>
- <a href="#link">link</a>

<a name="extension:UKCore-birthSex"></a>
<h4 class='additional-Guidance-Submenu'> extension:UKCore-birthSex </h4>
Extension used for recording the phenotypic sex of the patient, as recorded at birth.
```json
    {
      "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-BirthSex",
      "valueCodeableConcept": {
        "coding": [
          {
            "system": "http://terminology.hl7.org/CodeSystem/v3-AdministrativeGender",
            "code": "M",
            "display": "Male"
          }
        ]
      }
    }
  ```

<a name="identifier"></a>
<h4 class='additional-Guidance-Submenu'> identifier </h4>
SHALL be present for Patients within the Genomic Order Management ecosystem. It is preferred that all patients with an NHS number have this included within the Patient resource upon submission of a test order. Patient who do not have an NHS number SHOULD have a temporary one registered/assigned with PDS. 

For patient records where the NHS number has been traced from PDS, the trace status SHOULD be provided within the NHS Number identifier slice.

Additional identifiers SHOULD include an appropriate naming system scheme which clearly identifies the assigner (to disambiguate the identifier from other resources where these are not nationally unique). Alternatively, the OID for local identifier MAY be used, with the 'assigner' organization explicitly referenced.

```json
"identifier":  [
        {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307946",
            "extension":  [
                {
                    "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberVerificationStatus",
                    "valueCodeableConcept": {
                        "coding":  [
                            {
                                "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-NHSNumberVerificationStatusEngland",
                                "version": "2.2.0",
                                "code": "01",
                                "display": "Number present and verified"
                            }
                        ]
                    }
                }
            ]
        },
        {
            "system": "urn:oid:2.16.840.1.113883.2.1.3.2.4.18.24",
            "value": "RWT14789",
            "assigner": {
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                    "value": "RAX01"
                }
            }
        }
    ],
```

<a name="generalPractitioner"></a>
<h4 class='additional-Guidance-Submenu'> generalPractitioner </h4>
Where patients are registered with a General Practitioner within the UK, both the ODS code for the practice and GMP number for the practitioner SHOULD be provided, where known, as separate objects within the generalPractitioner array.

```json
"generalPractitioner":  [
        {
            "identifier": {
                "system": "https://fhir.hl7.org.uk/Id/gmp-number",
                "value": "G9999999"
            },
            "display": "Dr. Aero Smith"
        },
        {
            "identifier": {
                "system": "https://fhir.hl7.org.uk/Id/ODS-code",
                "value": "AP123"
            },
            "display": "anywhere place"
        }
    ],
```

<a name="link"></a>
<h4 class='additional-Guidance-Submenu'> link </h4>
For patient records where additional information exists elsewhere, for example, within PDS or the source system EHR, this MAY be referenced through the link field, specifying the url through which the related patient information can be accessed.

```json
"link":  [
        {
            "other": {
                "reference": "https://api.service.nhs.uk/personal-demographics/FHIR/R4/Patient/9449307946"
            },
            "type": "seealso"
        }
    ]
```

---
