## {{page-title}}

Prescription tracking will follow the status model shown below. This requires the practitioner to be EPS enabled. Statuses within the green area are in scope for the Prescriptions Management API. 

For paper prescriptions tracking will end once the prescription has been printed.


{{render:state_model_pm.png}}


**Requested**

Repeat prescription order has been created and submitted to practitioner systems but processing has not been started.
    
**Approved**

Repeat prescription order has been reviewed by a practitioner and passed through the system to EPS for processing/ printed ready for collection by the patient.

**Rejected**

Repeat prescription order has been reviewed by a practitioner and will not be processed further. When this selection is made by a practitioner they should be required to provide a rejection reason so the patient has context for this decision. This note is included within the 'status reason' free text field to ensure the full context of the response from the practitioner can be included in any response.