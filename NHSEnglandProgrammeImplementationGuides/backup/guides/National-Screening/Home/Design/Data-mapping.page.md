## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

<plantuml>
@startuml
Group "1" *-- "many" Patient : has
Patient "1" *-- "many" Encounter : has
Patient "1" *-- "many" Observation : has
Patient "1" *-- "many" Flag : has
CarePlan "1" *-- "1" Encounter : has
Patient "1" *-- "many" Appointment : has
Patient "1" *-- "many" Procedure : has
Patient "1" *-- "many" ServiceRequest : has
@enduml
</plantuml>


### Encounter

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>episode_id</td>
    <td>0..*</td>
    <td>UKCoreEncounter.identifier</td>
    <td>Type: Identifier</td>
</tr>
<tr>
    <td>episode_date</td>
    <td>0..1</td>
    <td>UKCoreEncounter.period (Start)</td>
    <td>Type: Period</td>
</tr>
<tr>
    <td>end_code</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>end_code_last_updated</td>
    <td>1..1</td>
    <td>UKCoreEncounter.statusHistory.period</td>
    <td>Type: Period</td>
</tr>
<tr>
    <td>reason_closed_code</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>end_code_description</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled.coding.display</td>
    <td>Type: String</td>
</tr>
<tr>
    <td>reason_closed_code_description</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled.coding.display</td>
    <td>Type: String</td>
</tr>
</tbody>
</table>

### Appointment

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>appointment_made</td>
    <td>1..1</td>
    <td>UKCoreAppoitment.status</td>
    <td>Type: Code</td>
</tr>
<tr>
    <td>date_of_foa</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>early_recall_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>next_test_due_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>early_recall_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>latest_invitation_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>higher_risk_next_test_due_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant</td>
</tr>
</tbody>
</table>

### Procedure

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>date_of_as</td>
    <td>0..1</td>
    <td>UKCoreProcedure.performedDateTime</td>
    <td>Type: dateTime</td>
</tr>
<tr>
    <td>end_point</td>
    <td>0..1</td>
    <td>UKCoreProcedure.outcome</td>
    <td>Type: CodeableConcept.text</td>
</tr>
<tr>
    <td>date_irradiated</td>
    <td>0..1</td>
    <td>UKCoreProcedure.performedDateTime</td>
    <td>Type: dateTime</td>
</tr>
</tbody>
</table>

### Service Request

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>episode_type</td>
    <td>0..*</td>
    <td>UKCoreServiceRequest.priority.extension:priorityReason</td>
    <td>Type: Extension(CodeableConcept)</td>
</tr>
<tr>
    <td>call_recall_status_authorised_by</td>
    <td>0..1</td>
    <td>UKCoreServiceRequest.extension:sourceOfServiceRequest</td>
    <td>Type: Extension(CodeableConcept)</td>
</tr>
<tr>
    <td>episode_type_description</td>
    <td>0..1</td>
    <td>UKCoreServiceRequest.priority.extension:priorityReason.coding.display</td>
    <td>Type: String</td>
</tr>
</tbody>
</table>

### Care Plan

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>final_action_code</td>
    <td>0..*</td>
    <td>UKCoreCarePlan.category</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>final_action_code_description</td>
    <td>0..1</td>
    <td>UKCoreCarePlan.category.coding.display</td>
    <td>Type: String</td>
</tr>
</tbody>
</table>

### Group

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>bso_organisation_code</td>
    <td>0..1</td>
    <td>Group.managingEntity (Organization)</td>
    <td>Type: Reference(Organization)</td>
</tr>
<tr>
    <td>bso_batch_id</td>
    <td>0..*</td>
    <td>Group.identifier</td>
    <td>Type: Identifier</td>
</tr>
</tbody>
</table>

### Patient

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>nhs_number</td>
    <td>0..1</td>
    <td>UKCorePatient.identifier.nhsNumber</td>
    <td>Type: Identifier</td>
</tr>
<tr>
    <td>gp_practice_code</td>
    <td>0..*</td>
    <td>UKCorePatient.generalPractitioner</td>
    <td>Type: Reference(Organization)</td>
</tr>
<tr>
    <td>preferred_language</td>
    <td>1..1</td>
    <td>UKCorePatient.communication.language</td>
    <td>Type: CodeableConcept</td>
</tr>
</tbody>
</table>

### Flag

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>subject_status_code</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>removal_reason</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>removal_date</td>
    <td>0..1</td>
    <td>UKCoreFlag.period.end</td>
    <td>Type: Period</td>
</tr>
<tr>
    <td>reason_for_ceasing_code</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>is_higher_risk</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>higher_risk_referral_reason_code</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>higher_risk_referral_reason_code_description</td>
    <td>0..1</td>
    <td>UKCoreFlag.code.coding.display</td>
    <td>Type: String</td>
</tr>
<tr>
    <td>is_higher_risk_active</td>
    <td>0..1</td>
    <td>UKCoreFlag.period.end</td>
    <td>Type: Period</td>
</tr>
<tr>
    <td>ntdd_calculation_method</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept</td>
</tr>
<tbody>
</table>

### Observation

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>gene_code</td>
    <td>0..1</td>
    <td>UKCoreObservation.value.valueCodeableConcept</td>
    <td>Type: CodeableConcept</td>
</tr>
<tr>
    <td>gene_code_description</td>
    <td>0..1</td>
    <td>UKCoreObservation.value.valueCodeableConcept.coding.display</td>
    <td>Type: String</td>
</tr>
<tbody>
</table>

### Organization

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>organisation_name</td>
    <td>0..1</td>
    <td>UKCoreOrganization.identifier.value</td>
    <td>Type: String</td>
</tr>
<tbody>
</table>

### Audit Event

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>record_insert_date_time</td>
    <td>1..1</td>
    <td>UKCoreAuditEvent.recorded</td>
    <td>Type: Instant</td>
</tr>
<tbody>
</table>

### Meta [Resource]

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
<tr>
    <td>source_system_processed_date_time</td>
    <td>0..1</td>
    <td>resource.meta.lastUpdated</td>
    <td>Type: Instant</td>
</tr>
<tr>
    <td>record_update_date_time</td>
    <td>0..1</td>
    <td>resource.meta.lastUpdated</td>
    <td>Type: Instant</td>
</tr>
<tbody>
</table>