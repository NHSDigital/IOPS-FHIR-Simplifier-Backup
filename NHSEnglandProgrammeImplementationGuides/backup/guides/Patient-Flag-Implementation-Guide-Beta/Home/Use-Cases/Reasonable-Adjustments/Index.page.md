## {{page-title}}

This page shows the functional use cases provided by the Reasonable Adjustments implementation within the PatientFlag API:

query to determine if a patient has a Reasonable Adjustments
 * either as part of general PatientFlag query that returns all PatientFlags
 * or query for just reasonable adjustments for the patient and return all associated Condition and Flag resources for all the recorded reasonable adjustments)

create a Reasonable Adjustment for a patient
 * create a PatientFlag (with no associated resources)
 * create a PatientFlag and associated Condition and Flag resources to detail all the reasonable adjustments for the patient
 * create additional reasonable adjustment Condition and Flag resources under an existing PatientFlag
 
delete reasonable adjustments for a patient
 * remove all reasonable adjustments by deleting the reasonable adjustment PatientFlag
 * remove individual reasonable adjustments by deleting relevant Conditions and Flags
