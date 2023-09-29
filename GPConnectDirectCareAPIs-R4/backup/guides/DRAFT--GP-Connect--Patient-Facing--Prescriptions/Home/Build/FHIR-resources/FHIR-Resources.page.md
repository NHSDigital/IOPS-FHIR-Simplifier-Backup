## {{page-title}}

### Resource library

<table data-responsive>
    <thead>
        <tr>
            <th>Action</th>
            <th>Resources</th>
            <th>Further information</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Creating a prescription request</td>
            <td>{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-Task}}</td>
            <td>For this action, use a UKCore-Task that has a focus of a UKCore-MedicationRequest with intent of plan.</td>
        </tr>
        <tr>
            <td>Cancelling a prescription request</td>
            <td>No resource is used</td>
            <td>To cancel a prescription request a JSON Patch is used.</td>
        </tr>
        <tr>
            <td>Viewing medication</td>
            <td>FHIR R4 Bundle containing: 
             {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationStatement}}
             where each is based on a: {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationRequest}} with intent of plan.</td>
            <td>When viewing a Medication the information will be returned in a Searchset bundle containing MedicationStatements where each must have a reference to a MedicationRequest in the basedOn element.</td>
        </tr>
        <tr>
            <td>View prescription reorder requests</td>
            <td>FHIR R4 Bundle containing: {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-Task}}</td>
            <td>When viewing prescription reorder requests a bundle containing Task resource's are returned.</td>
        </tr>
    </tbody>
</table>

<br></br>


### FHIR resources used when viewing medications
A patient must be able to view their current medication to see which medications are available to reorder.

Medications will be returned in a `MedicationStatement` resource. 

#### Request body
* no FHIR Resource will be sent in the request payload

#### Response
* the response will return a [FHIR Bundle](https://www.hl7.org/fhir/bundle.html) populated with: [FHIR MedicationStatement](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-MedicationStatement?version=1.0.0) (based on [FHIR MedicationRequest](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-MedicationRequest?version=1.0.0))

At this point the display within the `BasedOn` element of the `MedicationStatement` will show whether they are acute or repeat long term therapy. For example:

```json
      "basedOn" : [ {
        "reference" : "MedicationRequest/0f450c33-67b2-4ca3-b0f9-fea75ccdcd44",
        "display" : "Acute prescription request for Amoxicillin 250mg capsules."
      } ]
```

At this point the `basedOn` reference of the `MedicationRequest` can be used to query the `MedicationRequest` endpoint in order to get further information on the patient's medication.

### FHIR resources used when viewing a specific MedicationRequest 

Once the `MedicationStatement's` have been returned each `MedicationStatement` will be basedOn a specific `MedicationRequest` with intent of `plan`.

These can be used to obtain further information about the patient's prescription.

For example:

* confirming `courseOfTherapyType`
  * this will be under `display` in the basedOn element however the actual value can be found under `courseOfTherapyType` within the referenced `MedicationRequest`

* obtaining medication review dates
  * medication review dates will be displayed in the [Extension UK Core Medication Repeat Information](https://simplifier.net/packages/fhir.r4.ukcore.stu1/0.5.1/files/597130) within the referenced `MedicationRequest` under `authorisationExpiryDate`
  * this same extension will also display the number of issues under `numberOfPrescriptionsIssued`

#### Request body

* no FHIR resource will be sent in the request payload

#### Response 

* the response will return a singular [FHIR MedicationRequest](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-MedicationRequest?version=1.0.0)

### FHIR resources when viewing previous prescription issue details
It is also possible to obtain previous prescription issue details in the form of `MedicationRequest`s. 

#### Request body
* no FHIR resource will be sent in the request payload - instead within the path the NHS number must be used as a parameter

#### Response 
* the response will return a searchset [FHIR Bundle](https://www.hl7.org/fhir/bundle.html) populated with: [FHIR MedicationRequest](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-MedicationRequest?version=1.0.0)

This response will return all previous `MedicationRequest`s related to a patient. An extra optional parameter of `authoredon` can also be used to provide a cut-off in terms of dates.

## FHIR resources used in creating a prescription request

To create a new prescription, a `Task` must be used with a focus on a prior `MedicationRequest`. 

##### Request body
- [FHIR UKCore Task](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Task?version=current) with focus on a [FHIR UKCore MedicationRequest](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-MedicationRequest?version=1.0.0)

The payload should hit the prescription request endpoint with this request body. An example of the payload can be found on the [GP Connect Patient Facing Prescriptions FHIR API specification](https://digital.nhs.uk/developer/api-catalogue/gp-connect-patient-facing-prescriptions-fhir) under the POST `/FHIR/R4/Task/` endpoint.

### FHIR resources used when viewing active prescription reorder requests

A patient could wish to view their active and previous prescription reorder requests in order to see the current status.

#### Request body
* no FHIR resource is used in the request payload

#### Response 
* the response will return a searchset [FHIR Bundle](https://www.hl7.org/fhir/bundle.html) populated with: [FHIR Task](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Task?version=0.5.0)

Within this, the patient will be able to see all of their prior requests and each status.

If a patient identifier is passed it will return more than one `Task` resources within the bundle and if just the `id` is used only one resource will be returned within the bundle.

The `MedicationRequest` reference returned in the focus can be used to obtain further information about the prescription.

For example:

* obtaining information about the `Medication` itself
  * this will be under `medicationCodeableConcept`

* confirming `courseOfTherapyType`
  * this will be under `display` in the basedOn element - however, the actual value can be found under `courseOfTherapyType` within the referenced `MedicationRequest`

* obtaining medication review dates
  * medication review dates will be displayed in the [Extension UK Core Medication Repeat Information](https://simplifier.net/packages/fhir.r4.ukcore.stu1/0.5.1/files/597130) within the referenced `MedicationRequest` under `authorisationExpiryDate`
  * this same extension will also display the number of issues under `numberOfPrescriptionsIssued`


### FHIR resources used in cancelling a prescription request
A patient could send a cancellation to an unactioned prescription request. This means while the Task object has a status of `requested` and no further state.

#### Request body
* to cancel a prescription no FHIR resource is sent within the request payload (instead a JSON Patch is sent) 

##### The JSON patch must always look like:
```json
  [{
    "op": "replace",
    "path": "/status",
    "value": "cancelled"
  }]
```
#### Response
* the response will return the [FHIR UK Core Task](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Task?version=0.5.0) object which now displays the updated status of `cancelled` and the `lastModified` will no represent the current time

### FHIR resources returned in error responses ##

If an error occurs during processing of the request in any of the above API interactions, then the provider system will return an HTTP error code along with an OperationOutcome resource in the response payload. See {{pagelink:Home/Design/Errors-and-issues.page.md}}.

#### Response ####

- [FHIR OperationOutcome](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-OperationOutcome?version=0.5.0)
