---
topic: Profile-Genomics-AuditEvent
issue: AuditEvent
subject: http://hl7.org/fhir/StructureDefinition/AuditEvent
expand: yes
---


## StructureDefinition {{variable:issue}}

Created by the central GMS infrastructure on any CRUD event. 

Can be searched on for auditability and obtaining status history for Tasks (as an alternative to the Task _history option).

It is not expected or permitted that a client system would update or post AuditEvents to the central service.

AuditEvents are expected to be created for any CRUD events which affect resources on the server. Where resources do not exist on the server, e.g. empty SearchSets or failed POSTs, no AuditEvents will be created. Failed updates may still trigger creation of AuditEvent resources but the outcome.code will record that the event was unsuccessful.

AuditEvents for resources created by the server will record the server identity within the who element.

The below profile is therefore provided to support parsing for clients if returned through a GET request.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/AuditEvent](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/AuditEvent&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |


{{page:Home-FHIRAssets-Profiles-All-Profiles-BaseProfilesTemplatePage}}

        
<div id="Examples" class="tabcontent">
 <br />
<ul>
<li> {{pagelink:AuditEvent-ServiceRequestUpdate-Example}} </li>
<li> {{pagelink:AuditEvent-TaskUpdate-Example}} </li>
</ul>
</div>

<div id="Mappings" class="tabcontent">
<!--
            <br>
            <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
-->
</div>

---

<br>

<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#action">action</a>
- <a href="#agent">agent</a>
- <a href="#entity">entity</a>

<a name="action"></a>
<h4 class='additional-Guidance-Submenu'> action </h4>
SHALL be present. Code from base HL7 resource, only C (create), R (read) and U (update) would usually be expected.

```json
"action": "U",
```

<a name="agent"></a>
<h4 class='additional-Guidance-Submenu'> agent </h4>
SHOULD be present for any user initiated actions. Reference to the user or system that triggered the creation/read/update. Identity SHOULD be determined through the appropriate authentication token within the request header, e.g. CIS2 auth token.

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
<h4 class='additional-Guidance-Submenu'> entity </h4>
SHOULD be present where the resource exists on the server. Reference to the resource which was affected by the event.

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

---