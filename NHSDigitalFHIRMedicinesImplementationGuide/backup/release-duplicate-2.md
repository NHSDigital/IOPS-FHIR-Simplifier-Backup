## release


| Name  | Url |
|--
| Task-release | [https://fhir.nhs.uk/OperationDefinition/Task-release-message](https://simplifier.net/guide/DigitalMedicines/task-release) | 


<div class="nhsd-!t-margin-bottom-6">
  <ul class="nav nav-tabs" role="tablist">
        <li role="presentation"  class="active">
            <a href="#Description" role="tab" data-toggle="tab">Description</a>
        </li>
        <li role="presentation">
            <a href="#JSON" role="tab" data-toggle="tab">JSON</a>
        </li>
         <li role="presentation">
            <a href="#XML" role="tab" data-toggle="tab">XML</a>
        </li>
         <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
  </ul>
  <div class="tab-content snippet">
    <div id="Description" role="tabpanel" class="tab-pane active">
{{render:https://fhir.nhs.uk/OperationDefinition/Task-release-message}}
    </div>
    <div id="JSON" role="tabpanel" class="tab-pane">
{{json:https://fhir.nhs.uk/OperationDefinition/Task-release-message}}
    </div>
    <div id="XML" role="tabpanel" class="tab-pane">
 {{xml:https://fhir.nhs.uk/OperationDefinition/Task-release-message}}
    </div>
     <div id="Examples" role="tabpanel" class="tab-pane">

- {{pagelink:NominatedPharmacyReleaseRequest}}
- {{pagelink:PatientPrescriptionReleaseRequest}}

    </div>
  </div>
</div>

### group-identifier and owner

One of these values **MUST** be populated. 

- `group-identifier` is used to download a single prescription. This is called a *Patient Release Request*. This group identifier is either retrieved via the `Task API` {{pagelink:PrescriptionTrackerAPI.md}}
 or is presented to the pharmacy to the pharmacy by the patient (on paper or patient App).
- `owner` is used to download prescriptions where the pharmacy is the nominated pharmacy and have not been downloaded before. This is called a *Nominated Pharmacy Release*

Patient Release Request

```json
        {
            "name": "group-identifier",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-number",
                "value": "82D996-C81010-11DB12"
            }
        },
```

Nominated Pharmacy Release Request 

```json
        {
            "name": "owner",
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                "value": "VNE51"
            }
        }
```

### accept  

The only value to be used is `accepted`. This is for consistency with {{pagelink:NHSDigital-Task}} and for future use.

```json
        {
            "name": "status",
            "valueCode": "accepted"
        },
```

### agent

This is the provenance behind the request and is <a href="https://simplifier.net/guide/nhsdigital/NHSDigital-PractitionerRole">NHSDigital-PractitionerRole</a> resource. The resource should be populated using the guidance for this profile. Strict compliance to the profile is not enforced.

For attended request this should match CIS2 details being used. For unattended requests, a practitioner is still required, this should be a nominated member of the pharmacy and the data reflects their CIS2 identity.

The value of the `telecom` field should be the contact number a prescriber will use to contact the pharmacy.


<br/>

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="25%">PractitionerRole</th>
     <th data-no-sort width="25%">Patient Release Request (attended)</th>
     <th data-no-sort width="25%">Nominated Pharmacy Release Request (attended)</th>
      <th data-no-sort width="25%">Nominated Pharmacy Release Request (unattended)</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
        identifier
    </td>
    <td>
    </td>
     <td>
    </td>
    <td>
&checkmark;
    </td>
   </tr>
   <tr>
    <td>
        practitioner (professional code)
    </td>
    <td>
    &checkmark;
    </td>
     <td>
     &checkmark;
    </td>
    <td>
&checkmark;
    </td>
   </tr>
    <tr>
    <td>
        organization (ODS code)
    </td>
    <td>
    
    </td>
     <td>
     &checkmark; (if different to owner)
    </td>
    <td>
 &checkmark; (if different to owner)
    </td>
   </tr>
      <tr>
    <td>
       telecom
    </td>
    <td>
    &checkmark;
    </td>
     <td>
     &checkmark;
    </td>
    <td>
&checkmark;
    </td>
   </tr>
   </tbody>
</table>

```json
        {
            "name": "agent",
            "resource": {
                "resourceType": "PractitionerRole",
                "identifier":  [
                    {
                        "system": "https://fhir.nhs.uk/Id/sds-role-profile-id",
                        "value": "555086415105"
                    }
                ],
                "practitioner": {
                    "identifier": {
                        "system": "https://fhir.hl7.org.uk/Id/gmc-number",
                        "value": "C1231234"
                    },
                    "display": "Jackie Clark"
                },
                "organization": {
                    "identifier": {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "RHM"
                    },
                    "display": "UNIVERSITY HOSPITAL SOUTHAMPTON NHS FOUNDATION TRUST"
                },
                "telecom":  [
                    {
                        "system": "phone",
                        "value": "02380798431",
                        "use": "work"
                    }
                ]
            }
        }
```


