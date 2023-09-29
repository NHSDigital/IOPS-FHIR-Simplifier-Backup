## release


| Name  | Url |
|--
| Task-release | [https://fhir.nhs.uk/OperationDefinition/Task-release-message](https://simplifier.net/guide/NHSDigital-Medicines/Home/FHIRAssets/AllAssets/OperationDefinition-duplicate-2/release-duplicate-2.guide.md) | 


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

- {{pagelink:NominatedPharmacyReleaseRequest-duplicate-2}}
- {{pagelink:NominatedPharmacyReleaseRequest-unattended}}
- {{pagelink:PatientPrescriptionReleaseRequest-duplicate-2}}

    </div>
  </div>
</div>

- <a href="#groupidentifier">group-identifier</a>
- <a href="#owner">owner</a>
- <a href="#accept">accept</a>
- <a href="#agent">agent</a>

<a name="groupidentifier"></a>
### group-identifier

`group-identifier` is used to download a single prescription. This is called a *Patient Release Request*. This group identifier (also known as prescription token or the prescription short form id) is either retrieved via the `Task API` {{pagelink:PrescriptionTrackerAPI-duplicate-2}}
 or is presented to the pharmacy to the pharmacy by the patient (on paper or patient App).


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

<a name="owner"></a>
### owner

An Organization resource representing the pharmacy downloading the prescription.

```json
       {
            "name": "owner",
            "resource": {
                "resourceType": "Organization",
                "id": "organization",
                "identifier":  [
                    {
                        "system": "https://fhir.nhs.uk/Id/ods-organization-code",
                        "value": "VNE51"
                    }
                ],
                "address":  [
                    {
                        "city": "West Yorkshire",
                        "use": "work",
                        "line":  [
                            "17 Austhorpe Road",
                            "Crossgates",
                            "Leeds"
                        ],
                        "postalCode": "LS15 8BA"
                    }
                ],
                "active": true,
                "type":  [
                    {
                        "coding":  [
                            {
                                "system": "https://fhir.nhs.uk/CodeSystem/organisation-role",
                                "code": "182",
                                "display": "PHARMACY"
                            }
                        ]
                    }
                ],
                "name": "The Simple Pharmacy",
                "telecom":  [
                    {
                        "system": "phone",
                        "use": "work",
                        "value": "0113 3180277"
                    }
                ]
            }
        }
```

<a name="accept"></a>
### accept  

The only value to be used is `accepted`. This is for consistency with {{pagelink:NHSDigital-Task-duplicate-2}} and for future use.

```json
        {
            "name": "status",
            "valueCode": "accepted"
        },
```

<a name="agent"></a>
### agent

This is a <a href="https://simplifier.net/guide/nhsdigital/NHSDigital-PractitionerRole">NHSDigital-PractitionerRole</a> resource. 

GMC Reference Number **MUST NOT** be used as a Practitioner identifier

<br />

An example of a unattended $release payload.

{{json:Parameters-example-duplicate-4}}

An example of a attended $release payload.

{{json:Parameters-example-duplicate-5}}





