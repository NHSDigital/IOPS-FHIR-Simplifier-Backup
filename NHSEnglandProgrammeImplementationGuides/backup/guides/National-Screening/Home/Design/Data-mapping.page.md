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
    <td>Type: Identifier.<br>Unique ID to identify an episode.</td>
</tr>
<tr>
    <td>episode_date</td>
    <td>0..1</td>
    <td>UKCoreEncounter.period (Start)</td>
    <td>Type: Period.<br>Date an episode was created.</td>
</tr>
<tr>
    <td>end_code</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled</td>
    <td>Type: CodeableConcept.<br>Captures the reason why an episode is closed.</td>
</tr>
<tr>
    <td>end_code_last_updated</td>
    <td>1..1</td>
    <td>UKCoreEncounter.statusHistory.period</td>
    <td>Type: Period.<br>Date when screening  episode end code was last updated.</td>
</tr>
<tr>
    <td>reason_closed_code</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled</td>
    <td>Type: CodeableConcept.<br>The reason closed code indicates the reason that lead to the closing of the episode in NBSS</td>
</tr>
<tr>
    <td>end_code_description</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute: End_code</td>
</tr>
<tr>
    <td>reason_closed_code_description</td>
    <td>0..1</td>
    <td>UKCoreEncounter.extension:reasonCancelled.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute reason_closed_code</td>
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
    <td>UKCoreAppointment.status</td>
    <td>Type: Code.<br>Whether an appointment was made for a subject to be screened </td>
</tr>
<tr>
    <td>date_of_foa</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant.<br>The first offered appointment date to a participant.</td>
</tr>
<tr>
    <td>early_recall_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant.<br>The date on which the participant is recalled early for routine screening. This is the early recall date that related to this episode</td>
</tr>
<tr>
    <td>next_test_due_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant.<br>Date when screening subject is due for next test.</td>
</tr>
<tr>
    <td>latest_invitation_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant.<br>The most recent screening invitation date sent out to a participant.</td>
</tr>
<tr>
    <td>higher_risk_next_test_due_date</td>
    <td>0..1</td>
    <td>UKCoreAppointment.start (date)</td>
    <td>Type: Instant.<br>The HR NTDD of someone who is in the HR program - when they're next due to be screened.</td>
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
    <td>Type: dateTime.<br>The date on which a participant underwent screening.</td>
</tr>
<tr>
    <td>end_point</td>
    <td>0..1</td>
    <td>UKCoreProcedure.outcome</td>
    <td>Type: CodeableConcept.text.<br>An endpoint is the summary of Procedure Outcomes, obtained when the episode is closed. </td>
</tr>
<tr>
    <td>date_irradiated</td>
    <td>0..1</td>
    <td>UKCoreProcedure.performedDateTime</td>
    <td>Type: dateTime.<br>Date on which subject has received radiological procedure during a mammogram,Relates to higher risk women</td>
</tr>
<tr>
    <td>screening_programme_name</td>
    <td>0..1</td>
    <td>UKCoreProcedure.code</td>
    <td>Type: CodeableConcept.<br>This is the name given to a screening program. For ex: Breast screening program</td>
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
    <td>Type: Extension(CodeableConcept).<br>Indicates the type of screening episode that a subject has underwent. e.g. call / recall / high risk / GP referred / self referral</td>
</tr>
<tr>
    <td>call_recall_status_authorised_by</td>
    <td>0..1</td>
    <td>UKCoreServiceRequest.extension:sourceOfServiceRequest</td>
    <td>Type: Extension(CodeableConcept).<br>Indicates the entity which has authorized the recall of a screening participant.
</tr>
<tr>
    <td>episode_type_description</td>
    <td>0..1</td>
    <td>UKCoreServiceRequest.priority.extension:priorityReason.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute: Episode_type</td>
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
    <td>Type: CodeableConcept.<br>The final action codes specify the actions or events that should occur after the closure of an episode.</td>
</tr>
<tr>
    <td>final_action_code_description</td>
    <td>0..1</td>
    <td>UKCoreCarePlan.category.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute: Final_action_code</td>
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
    <td>Type: Reference(Organization).<br>Organisation code for Breast Screening Office. </td>
</tr>
<tr>
    <td>bso_batch_id</td>
    <td>0..*</td>
    <td>Group.identifier</td>
    <td>Type: Identifier.<br>This is a batch number assigned on NBSS. It is prefixed with the BSO code.</td>
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
    <td>Type: Identifier.<br>The unique identifier for a person within the NHS.</td>
</tr>
<tr>
    <td>gp_practice_code</td>
    <td>0..*</td>
    <td>UKCorePatient.generalPractitioner</td>
    <td>Type: Reference(Organization).<br>Unique identifier for each GP Practice.</td>
</tr>
<tr>
    <td>preferred_language</td>
    <td>1..1</td>
    <td>UKCorePatient.communication.language</td>
    <td>Type: CodeableConcept.<br>A participant's preferred language of communication.</td>
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
    <td>Type: CodeableConcept.<br>Normal or ceased (ceased if the subject is no longer attending screening)</td>
</tr>
<tr>
    <td>removal_reason</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept.<br>Reason for screening subject's removal from the GP</td>
</tr>
<tr>
    <td>removal_date</td>
    <td>0..1</td>
    <td>UKCoreFlag.period.end</td>
    <td>Type: Period.<br>Date when screening subject was removed from the GP</td>
</tr>
<tr>
    <td>reason_for_ceasing_code</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept.<br>This is a standardised reason why woman has been ceased from screening.</td>
</tr>
<tr>
    <td>is_higher_risk</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept.<br>Indicates whether a screening subject is a higher risk or not.</td>
</tr>
<tr>
    <td>higher_risk_referral_reason_code</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept.<br>The reason code assigned to a higher risk subject.</td>
</tr>
<tr>
    <td>higher_risk_referral_reason_code_description</td>
    <td>0..1</td>
    <td>UKCoreFlag.code.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute: higher_risk_referral_reason_code</td>
</tr>
<tr>
    <td>is_higher_risk_active</td>
    <td>0..1</td>
    <td>UKCoreFlag.period.end</td>
    <td>Type: Period.<br>The high risk is active for the subject or not.</td>
</tr>
<tr>
    <td>ntdd_calculation_method</td>
    <td>1..1</td>
    <td>UKCoreFlag.code</td>
    <td>Type: CodeableConcept.<br>Whether a woman's NTDD should be calculated in the normal, routine way, or if she's in a trial and it needs calculating differently.</td>
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
    <td>Type: CodeableConcept.<br>Captures the information related to Gene for high risk subjects,Relates to higher risk women</td>
</tr>
<tr>
    <td>gene_code_description</td>
    <td>0..1</td>
    <td>UKCoreObservation.value.valueCodeableConcept.coding.display</td>
    <td>Type: String.<br>This is the description for the data attribute: gene_code</td>
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
    <td>Type: String.<br>This is the description for the data attribute: </td>
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
    <td>Type: Instant.<br>This is date time when a record is inserted into these tables</td>
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
    <td>Type: Instant.<br>This is change_db_date_time captured from the source system BS-select. This indicates the last time the record changed in the source system.</td>
</tr>
<tr>
    <td>record_update_date_time</td>
    <td>0..1</td>
    <td>resource.meta.lastUpdated</td>
    <td>Type: Instant.<br>This is the date time when a record is updated in these tables.</td>
</tr>
<tbody>
</table>