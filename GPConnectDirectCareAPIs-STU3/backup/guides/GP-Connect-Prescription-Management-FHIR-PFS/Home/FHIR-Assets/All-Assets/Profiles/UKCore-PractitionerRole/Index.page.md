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
    <li role="presentation">
        <a href="#example-1" role="tab" data-toggle="tab">Example</a>
      </li>
  </ul>
  </div>

  <!-- Tab panes -->
  <div class="tab-content snippet nhsd-!t-margin-bottom-6">
    <div role="tabpanel" class="tab-pane active" id="profile-1">
        {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole}}
    </div>
    <div role="tabpanel" class="tab-pane" id="dictionary-1">
        {{dict:https://fhir.hl7.org.uk/StructureDefinition/UKCore-PractitionerRole}} 
    </div>
        <div role="tabpanel" class="tab-pane" id="example-1">
        {{json:}} 
    </div>
  </div>
</div>

### Definition
A specific set of Roles/Locations/specialties/services that a practitioner may perform at an organization for a period of time.

### Minimum Viable Content
A minimum viable content that all provider and consumer systems should support is the following elements.

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>Required?</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>meta.profile</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td><span class="fas fa-check-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>active</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>        
        <tr>
            <td>period</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>practitioner</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>organization</td>
            <td><span class="fas fa-check-circle text-success fa-lg"></span></td>
        </tr>
        <tr>
            <td>code</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>specialty</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>location</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        <tr>
            <td>healthcareService</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></td>
        </tr>
        <tr>
            <td>availableTime</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>notAvailable</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>availabilityExceptions</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td><span class="fas fa-times-circle text-danger fa-lg"></span></td>
        </tr>
    </tbody>
</table>

---

### id

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
      <td>identifier</td>
      <td>required</td>
      <td>1:1</td>
      </tr>
    </tbody>
</table>

The logical identifier of the MedicationStatement resource.

#### Example
```json
 "id":"c5bb3d99-f7b5-4582-bbff-6425bdcde0b0" 
```

### practitioner

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
        <td>identifier</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The practitioner to which the role relates as a reference to UKCore-Practitioner.

#### Example
```json
"practitioner" : {
   "display" : "Dr Jane Smith",
   "identifier" : {
     "system" : "https://fhir.hl7.org.uk/Id/gmc-number",
     "value" : "C9876543"
    }
}
```

### organization

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
        <td>identifier</td>
        <td>required</td>
        <td>1:1</td>
      </tr>
    </tbody>
</table>

The organization to which the role relates as a reference to UKCore-Organization.

#### Example
```json
"organization" : {
    "identifier" : {
      "system" : "https://fhir.nhs.uk/Id/ods-organization-code",
      "value" : "L8048"
    }
}
```
