## {{page-title}}

For collecting relevant Family Member History to aid interpretation of Genomic results.

The Genomics FamilyMemberHistory is currently pending Clinical and Technical Assurance of the base UKCore resource. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The draft profile for the UKCore-FamilyMemberHistory is provided below for completeness.

<br>
The CareConnect profile will be uplifted to the R4 UKCore in a future release
<br>

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/FamilyMemberHistory}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                        {{pagelink:FamilyMemberHistory-NonConsanguinousUnion-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                        {{pagelink:FamilyMemberHistory-NonConsanguinousUnionProband-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                        {{pagelink:FamilyMemberHistory-NonConsanguinousUnionProbandFather-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                        {{pagelink:FamilyMemberHistory-NonConsanguinousUnionProbandMother-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                        {{pagelink:FamilyMemberHistory-NonConsanguinousUnionRyanneBoulder-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>FamilyMemberHistory</td><td>Pedigree details/diagram, Disease penetrance</td><td>N/A not in scope for HL7v2, could be added as additional PRB segments related to relatives</td></tr>
                    <tr><td>FamilyMemberHistory.extension:family-member-history-genetics-observation</td><td>Patient - Is from consanguinous union</td><td>OBX-5 with appropriate SNOMED/READ/LOINC code</td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#extension:genetics-observation">extension:genetics-observation</a>
- <a href="#status">status</a>
- <a href="#patient">patient</a>
- <a href="#relationship">relationship</a>

<a name="extension:genetics-observation"></a>
#### extension:genetics-observation
An extension on the FamilyMemberHistory resource to include Observations relevant to Genomic testing/interpretation, such as proband consanguinuity. 
```json
"extension":  [
        {
            "url": "http://hl7.org/fhir/StructureDefinition/family-member-history-genetics-observation",
            "valueReference": {
                "reference": "Observation/Observation-NonConsanguinousUnion-Example"
            }
        }
    ],
```

<a name="status"></a>
#### status
Used to mark the completeness of a given family member's clinical history. If the history of a family member is expected but no history could be obtained, this  element SHOULD be filled with 'health-unknown'.

Assertions regarding absence of relevant history SHOULD follow guidance within the [HL7 FHIR R4 FamilyMemberHistory resource](http://hl7.org/fhir/R4/familymemberhistory.html#9.4.2.4).
```json
"status": "completed",
```

<a name="patient"></a>
#### patient
Reference to the associated proband Patient for which this family history is being obtained. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="relationship"></a>
#### relationship
Relationship between the person the FamilyMemberHistory references and the proband Patient. Clinical histories for each family member are expected to be recorded in separate FamilyMemberHistory resources. If multiple resources are required, both FamilyMemberHistory and related clinical artifacts such as Condition/Observation resources, these MAY be contained within a List resource to improve readability.
```json
"relationship": {
        "coding":  [
            {
                "system": "http://terminology.hl7.org/CodeSystem/v3-RoleCode",
                "code": "PRN",
                "display": "parent"
            }
        ]
    }
```