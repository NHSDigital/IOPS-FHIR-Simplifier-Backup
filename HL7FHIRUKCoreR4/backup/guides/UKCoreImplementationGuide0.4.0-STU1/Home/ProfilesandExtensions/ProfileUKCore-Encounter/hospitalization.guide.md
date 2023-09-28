## <code>{{page-title}}</code>

Details about the admission to a healthcare service. There are a number of child elements that are used and these are detailed below:

- `hospitalization.preAdmissionIdentifier`	Pre-admission identifier
- `hospitalization.origin`	The location/organization from which the patient came before admission using a Reference to the Location or Organization. The resource being referenced should conform to one of the following: 

-  {{pagelink:Profile-Location-9738cf88-9ba3-4fc6-8efb-58b9583498f2}}
-  {{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}
	
- `hospitalization.admitSource` a CodeableConcept	to indicate from where patient was admitted (physician referral, transfer)
- `hospitalization.reAdmission` The type of hospital re-admission that has occurred (if any). If the value is absent, then this is not identified as a readmission
- `hospitalization.dietPreference` Diet preferences reported by the patient
- `hospitalization.specialCourtesy`	Special courtesies (VIP, board member)
- `hospitalization.specialArrangement` Wheelchair, translator, stretcher, etc.
- `hospitalization.dischargeDisposition` Category or kind of location after discharge



---
