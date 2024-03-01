## {{page-title}}

For detailing any Condition related information about the proband/consultands within a test order.

It is expected that the information used to populate this resource SHOULD be sourced from the requesters EHR system. As such, there is no limit on the amount of detail that can be provided, though at a minimum the code and subject fields SHOULD be populated.

It is also highly preferred if the verificationStatus, onsetDateTime, recordedDate, recorded and abatementDateTime are populated if applicable/known.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Condition}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Condition-PancreaticCancer}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Condition-HearingLoss-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Condition-BreastCancer-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Condition-Hepatosplenomegaly-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Condition-LungTumor-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
            <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Condition</td><td>Patient Clinical Presentation, Diabetic complications</td><td>PRB</td></tr>
                    <tr><td>Condition.bodySite</td><td>Has multiple primary tumours, Count of tumours, Site of tumour (many), Paraganglioma location, Abnormal infection history site, Abnormal infection history site organism</td><td>Multiple PRB segments (bodySite for condition not in scope for HL7v2)</td></tr>
                    <tr><td>Condition.verificationStatus</td><td>Known/suspected disease</td><td>PRB-13</td></tr>
                    <tr><td>Condition.recordedDate</td><td>Date of diagnosis, Diagnosis during pregnancy</td><td>PRB-7</td></tr>
                    <tr><td>Condition.clinicalStatus</td><td>Disease status, Is patient in treatment free remission, Is diabetes in remission</td><td>PRB-14</td></tr>
                    <tr><td>Condition.code</td><td>Phenotypic details (Many), Solid tumour type, Liquid tumour type, Laterality of hearing loss, Fetal maternal screening genotype, Fetal paternal screening genotype, Thyroid gland state, Pituitary tumour type, Pancreatic tumour type, Phaeochromocytoma, Progeroid features, Severity of hearing loss, Retinal degeneration, Hepatic vs neurological presentation, Suspected inborn error type(s)</td><td>Additional PRB segments (PRB-3)</td></tr>
                    <tr><td>Condition.onsetDateTime</td><td>Date of disease onset, Duration of hyperinsulism (when compared to abatementDateTime</td><td>PRB-16</td></tr>
                    <tr><td>Condition.evidence.detail( reference( FamilyMemberHistory, Media ) )</td><td>Pedigree details/diagram, Disease penetrance</td><td>N/A not in scope for HL7v2, could be added as additional PRB segments related to relatives</td></tr>
                    <tr><td>Condition.evidence.code</td><td>Symptoms at onset</td><td>OBX segments attached to PRB</td></tr>
                    <tr><td>Condition.note</td><td>Date of diabetes remission</td><td>NTE segment attached to PRB</td></tr>
            </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Condition' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#code">code</a>
- <a href="#subject">subject</a>
- <a href="#note">note</a>

<a name="code"></a>
#### code
SNOMED CT coding is preferred, though alternative codings MAY be provided subject to review of the Coding system by the NHS England Genomics Unit.
```json
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "95820000",
                "display": "Bilateral hearing loss"
            }
        ]
    },
```

<a name="subject"></a>
#### subject
Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="note"></a>
#### note
For recording additional information regarding the condition where this does not fit into the structured fields or cannot be structured due to the way this information has been recorded in source systems.
```json
"note":  [
        {
            "text": "hearing loss since childhood (example)"
        }
    ]
```