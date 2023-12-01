## {{page-title}}

Used for linking Patients with other patients, e.g. in the case of proband and consultand within duo and trio testing. 

For instances where clinical/demographic information for the related person are required, a Patient resource for the related person SHOULD be included, with the Patient.link field referencing the RelatedPerson. Elements duplicated across both the Patient and RelatedPerson SHOULD in this case be captured within the Patient resource only. The RelatedPerson resource then references the proband through the RelatedPerson.patient field. 

Further use cases surrounding the use of RelatedPerson are pending further Duo/Trio scenarios.


| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson) | [UKCore]() | trial-use |

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
- <a href="#relationship">relationship</a>

<a name="patient"></a>
#### patient
SHALL be provided. This SHOULD be a reference to the Patient resource or the identifier, NHS number, for the patient.
```json
"patient": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9999999999"
        }
    },
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