---
topic: Profile-UKCore-RelatedPerson
issue: UKCore-RelatedPerson
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson
expand: yes
---

# {{variable:issue}}

Used for linking Patients with other participants of a test order, e.g. in the case of proband and consultand within duo and trio testing. 

For instances where clinical/demographic information for the related person are required, a Patient resource for the related person (consultand) SHOULD be included, with the Patient.link field referencing the RelatedPerson resource for the same individual. Elements duplicated across both the Patient and RelatedPerson for the same individual SHOULD in this case be captured within the Patient resource only. The RelatedPerson resource then references the proband Patient resource through the RelatedPerson.patient field. 

A diagram illustrating the links between resources is provided below (Duo Scenario):

<br>

<plantuml>
@startuml
!pragma ratio 0.3
scale 1100 width
entity SR as "Test Request" <<ServiceRequest>>
entity P1 as "Proband" <<Patient>>
'entity S1 as "Sample from Proband" <<Specimen>>
'entity S2 as "Sample from Consultand A" <<Specimen>>
together {
  entity RP as "Relationship of Consultand A to Proband" <<RelatedPerson>>
  entity P2 as "Consultand A" <<Patient>>
  entity C2 as "RoD Consultand A" <<Consent>>
}
together {
  entity FMH as "Pedigree Person B" <<FamilyMemberHistory>> {
    Not a participant in the test request
  }
  entity C1 as "RoD Proband" <<Consent>>
}
SR -d-> P1 : ServiceRequest.subject
together {
  SR -d-> C1 : ServiceRequest.supportingInfo
  SR -d-> FMH : ServiceRequest.supportingInfo
  SR -d-> RP : ServiceRequest.supportingInfo
  SR -d-> P2 : ServiceRequest.supportingInfo
  SR -d-> C2 : ServiceRequest.supportingInfo
}
C1 -d-> P1 : Consent.patient
FMH -d-> P1 : FamilyMemberHistory.patient
'S1 -d-> P1 : Specimen.subject
'S1 -u-> SR : Specimen.request
RP -r-> P1 : RelatedPerson.patient
P2 -r-> RP : Patient.link
'S2 -d-> P2 : Specimen.subject
'S2 -u-> SR : Specimen.request
C2 -d-> P2 : Consent.patient
'S1 -l[hidden]-> C1
'S1 -l[hidden]-> FMH
'RP -u[hidden]-> FMH
@enduml
</plantuml>

<br>
<br>
Further use cases surrounding the use of RelatedPerson are pending further Duo/Trio scenarios.

<br>


| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank">https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson</a> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}


<div id="Examples" class="tabcontent">
            <br>
            <ul>
                    <li>
                    {{pagelink:RelatedPerson-AliceSmithamProbandMother-Example}}
                    </li>
                    <li>
                    {{pagelink:RelatedPerson-AnitaLambertsDeceasedPatient-Example}}
                    </li>
                    <li>
                    {{pagelink:RelatedPerson-JamesLawrenceProbandFather-Example}}
                    </li>
                    <li>
                    {{pagelink:RelatedPerson-RyanneBoulder-Example}}
                    </li>
                    <li>
                    {{pagelink:RelatedPerson-RyanneBoulderPartner-Example}}
                    </li>
                    <li>
                    {{pagelink:RelatedPerson-MichaelaJones}}
                    </li>
            </ul>
        </div>

<div id="Mappings" class="tabcontent">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>RelatedPerson.relationship</td><td>Patient - Relationship to proband, Previous genomic report - Patient's relationship to requesting patient</td><td>NK1-3</td></tr>
                </table>
</div>

<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>
<h3 id='non-fql-header'> Additional Guidance </h3>


- <a href="#patient">patient</a>
- <a href="#identifier">identifier</a>
- <a href="#relationship">relationship</a>

<a name="patient"></a>
<h4 class='additional-Guidance-Submenu'> patient </h4>
SHALL be provided. This SHOULD be a reference to the Patient resource and/or the identifier, e.g. NHS number, for the patient constituting the target of the relationship.  This can be visualised using the nomenclature: 

```json
{Source (identifier)} is the {Relationship type (relationship)} of {Target (patient)}
'Ryanne Boulder' is the 'natural mother' of 'Fetus of Ryanne Boulder'
```

In this case the fetal identifier should be used in the patient element.

```json
"patient": {
    "reference": "Patient/Patient-FoetusOfRyanneBoulder-Example",
    "identifier": {
      "system": "urn:oid:2.16.840.1.113883.2.1.3.2.4.18.24",
      "value": "FT-RWT13521",
      "assigner": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "RAX"
        }
      }
    }
  },
```

<a name="identifier"></a>
<h4 class='additional-Guidance-Submenu'> identifier </h4>
SHALL be provided. This SHOULD be NHS number or local identifier (if NHS number is unavailable e.g. for non UK residents) for the source of the relationship. This can be visualised using the nomenclature: 

```
{Source (identifier)} is the {Relationship type (relationship)} of {Target (patient)}
'Ryanne Boulder' is the 'natural mother' of 'Fetus of Ryanne Boulder'
```

In this case the Ryanne Boulder's identifier should be used for the RelatedPerson.identifier.

If a local identifier is used, an assigner SHALL be provided.
The RelatedPerson.identifier field SHALL match the identifier used for a FamilyMemberHistory or Patient resource if these resources are about the same person.

```json
   "identifier": [
      {
        "system": "https://fhir.nhs.uk/Id/nhs-number",
        "value": "9999999999"
      }
    ],
```

<a name="relationship"></a>
<h4 class='additional-Guidance-Submenu'> relationship </h4>
SHOULD use the UK Core bound ValueSet and SHOULD be present in all instances of RelatedPerson wherever possible.

```json
"relationship":  [
        {
            "coding":  [
                {
                    "system": "http://terminology.hl7.org/CodeSystem/v3-RoleCode",
                    "code": "SIS",
                    "display": "sister"
                }
            ]
        }
    ]
```

---