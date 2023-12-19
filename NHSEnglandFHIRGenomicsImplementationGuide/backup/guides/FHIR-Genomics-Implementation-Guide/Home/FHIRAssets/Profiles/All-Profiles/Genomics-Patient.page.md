## {{page-title}}

The focal resource for recording who a test order and genomic report are for.

It is expected that client's will need to post Patient resources to the central GMS as some demographic information specific to Genomics will not have been captured within other systems such as PDS.

Alternatively, systems MAY opt to include pointers to the Patient resource on their local system, though the mechanism preferred by the NHS England Genomics Unit has yet to be decided.

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient&scope=fhir.r4.ukcore.stu3.currentbuild@0.0.6-pre-release) | [UKCore]() | trial-use |

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
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Patient}} <br>
            <br />
            {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Patient-MichaelJones}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-LindsaySorrell-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-LindsaySorrellPDS-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-MeirLieberman-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Patient-MeirLiebermanPDS-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient'
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
where baseDefinition='https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```

<br>

### Additional Guidance

- <a href="#identifier">identifier</a>
- <a href="#generalPractitioner">generalPractitioner</a>
- <a href="#link">link</a>

<a name="identifier"></a>
#### identifier
It is preferred that all patients with an NHS number have this included within the Patient resource upon submission of a test order. Patient who do not have an NHS number SHOULD have a temporary one registered/assigned with PDS. 

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
#### generalPractitioner
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
#### link
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
