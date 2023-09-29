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
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation}} 
    </div>
  </div>
</div>

### extension:medicationRepeatInformation

<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
      <td>Extension</td>
      <td>required</td>
      <td>0:1</td>
      </tr>
    </tbody>
</table>

This extension must be present for `continuous` and `continuous-repeat-dispensing` therapy types.

##### medicationRepeatInformation.authorisationExpiryDate
Only populate for a `MedicationRequest` with an intent = plan. For a `MedicationRequest` with an intent = order this is not populated.

##### medicationRepeatInformation.numberOfPrescriptionsIssued
Running total of number of issues made against a repeat authorisation.

MUST be zero, if not yet issued.

#### Example
```json
"extension": [
  {
       "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-MedicationRepeatInformation",
       "extension": [
           {
               "url": "numberOfRepeatPrescriptionsIssued",
               "valueUnsignedInt": 3
           },
           {
               "url": "authorisationExpiryDate",
               "valueDateTime": "2022-08-07"
           }
       ]
   }
]
```
