## {{page-title}}

Created by the central GMS infrastructure on any CRUD event. 

Can be searched on for auditability and obtaining status history for Tasks.

It is not expected or permitted that a client system would update or post AuditEvents to the central service.

The below profile is therefore provided to support parsing for clients if returned through a GET request.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/AuditEvent](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/AuditEvent&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

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
            {{tree:http://hl7.org/fhir/StructureDefinition/AuditEvent, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/AuditEvent}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/AuditEvent, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/AuditEvent, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:AuditEvent-ServiceRequestUpdate-Example}}
                    </td>
                </tr>
                <tr>
                     <td>
                    {{pagelink:AuditEvent-TaskUpdate-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url='http://hl7.org/fhir/StructureDefinition/AuditEvent'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
        </div>
    </div>
</div>

### Constraint Profiles
Profiles indicating preferred element cardinality for use in Genomics, not to be used for validation

@```
from StructureDefinition
where baseDefinition='http://hl7.org/fhir/StructureDefinition/AuditEvent' 
select name, profile: '<a href="https://simplifier.net/resolve?target=simplifier&scope=NHS-Digital-FHIR-Genomics-Implementation-Guide@current&canonical='+ url + '">'+url+'</a>'
```
<br>

### Additional Guidance

- <a href="#action">action</a>
- <a href="#agent">agent</a>
- <a href="#entity">entity</a>

<a name="action"></a>
#### action
Code from base HL7 resource, only C (create), R (read) and U (update) would usually be expected.
```json
"action": "U",
```

<a name="agent"></a>
#### agent
Reference to the PractitionerRole resource which triggered the creation/read/update. Identity determined through CIS2 authentication token.
```json
"agent":  [
        {
            "type": {
                "coding":  [
                    {
                        "system": "http://terminology.hl7.org/CodeSystem/v3-ParticipationType",
                        "code": "AUT",
                        "display": "author (originator)"
                    }
                ]
            },
            "who": {
                "reference": "PractitionerRole/PractitionerRole-TestClinicalScientist-Example",
                "identifier": {
                    "system": "https://fhir.nhs.uk/Id/sds-user-id",
                    "value": "9999999997"
                }
            },
            "name": "Test Clinical Scientist",
            "requestor": true
        }
    ],
```

<a name="entity"></a>
#### entity
Reference to the resource which was affected by the event.
```json
"entity":  [
        {
            "what": {
                "reference": "Task/Task-NonWGSRareDiseaseTestOrderRejected-Example"
            },
            "type": {
                "system": "http://hl7.org/fhir/resource-types",
                "code": "Task",
                "display": "Task"
            },
            "role": {
                "system": "http://terminology.hl7.org/CodeSystem/object-role",
                "code": "20",
                "display": "Job"
            }
        }
    ]
```