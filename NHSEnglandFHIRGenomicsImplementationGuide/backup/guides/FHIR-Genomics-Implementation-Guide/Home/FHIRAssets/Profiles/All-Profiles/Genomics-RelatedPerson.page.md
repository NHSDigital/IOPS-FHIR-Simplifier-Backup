## {{page-title}}

Used for linking Patients with other participants of a test order, e.g. in the case of proband and consultand within duo and trio testing. 

For instances where clinical/demographic information for the related person are required, a Patient resource for the related person (consultand) SHOULD be included, with the Patient.link field referencing the RelatedPerson resource for the same individual. Elements duplicated across both the Patient and RelatedPerson for the same individual SHOULD in this case be captured within the Patient resource only. The RelatedPerson resource then references the proband Patient resource through the RelatedPerson.patient field. 

A diagram illustrating the links between resources is provided below (Duo Scenario):

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

Further use cases surrounding the use of RelatedPerson are pending further Duo/Trio scenarios.


| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/RelatedPerson}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-AliceSmithamProbandMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-AnitaLambertsDeceasedPatient-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-JamesLawrenceProbandFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-RyanneBoulder-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-RyanneBoulderPartner-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:RelatedPerson-MichaelaJones}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>RelatedPerson.relationship</td><td>Patient - Relationship to proband, Previous genomic report - Patient's relationship to requesting patient</td><td>NK1-3</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#patient">patient</a>
- <a href="#identifier">identifier</a>
- <a href="#relationship">relationship</a>

<a name="patient"></a>
#### patient
SHALL be provided. This SHOULD be a reference to the Patient resource or the identifier, e.g. NHS number, for the patient constituting the target of the relationship.  This can be visualised using the nomenclature: 

```
{Source (identifier)} is the {Relationship type (relationship)} of {Target (patient)}
'Ryanne Boulder' is the 'natural mother' of 'Fetus of Ryanne Boulder'
```

In this case the fetal identifier should be used in the patient element.
```json
"patient": {
    "system": "urn:oid:2.16.840.1.113883.2.1.3.2.4.18.24",
    "value": "FT-RWT13521",
    "assigner": {
      "identifier": {
        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
        "value": "RAX"
      }
    }
  },
```

<a name="identifier"></a>
#### identifier
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
#### relationship
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