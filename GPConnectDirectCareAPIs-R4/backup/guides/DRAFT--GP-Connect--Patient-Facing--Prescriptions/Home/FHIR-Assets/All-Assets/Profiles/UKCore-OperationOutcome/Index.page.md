## {{page-title}}

<!--// start of code snippet -->
<div>
    <ul class="nav nav-tabs" role="tablist">
      <li role="presentation" class="active">
        <a href="#profile-1" role="tab" data-toggle="tab">Profile</a>
      </li>
      <li role="presentation">
        <a href="#dictionary-1" role="tab" data-toggle="tab">Dictionary</a>
      </li>
  </ul>

  <!-- Tab panes -->
  <div class="tab-content snippet nhsd-!t-margin-bottom-6">
    <div role="tabpanel" class="tab-pane active" id="profile-1">
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome}} 
    </div>
  </div>
</div>

### Example
```json
{
    "resourceType": "OperationOutcome",
    "id": "UKCore-OperationOutcome-DateError-Example",
    "meta": {
        "profile": [
            "https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome"
    ]},
    "issue":  [
        {
            "severity": "fatal",
            "code": "structure",
            "details": {
                "coding":  [
                    {
                        "system": "http://terminology.hl7.org/CodeSystem/operation-outcome",
                        "code": "MSG_DATE_FORMAT",
                        "display": "The Date value %s is not in the correct format (Xml Date Format required)"
                    }
                ]
            },
            "diagnostics": "Interop.FHIRProcessors.Patient.processbirthDate line 2450",
            "expression":  [
                "Patient.birthDate"
            ]
        }
    ]
}
```