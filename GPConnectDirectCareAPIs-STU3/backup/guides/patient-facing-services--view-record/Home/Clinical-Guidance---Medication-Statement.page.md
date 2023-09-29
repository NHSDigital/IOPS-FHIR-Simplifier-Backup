## {{page-title}}

<span class="mro-circle avoid" title=""></span> Not recommended

The status resource is likely to have no meaning to the end user, it is not advised to use this resource for Patient Facing Service (PFS) consumption. This will cause more confusion than assistance to the user. The status field has nothing to do with the patient taking the drug, this is a GP admin status and for internal consumption only.

## What is the status resource for?
Scenario - The GP prescribes a course of medication. At the end of each course, they may arrange a blood test. The clinical staff issuing the drugs will then know when it’s the end of the course (with 'Status - Complete') and arrange for the patient to come in for a blood test. A prescription is complete when it has come to the end of an authorisation or review date. If a patient were to see this, they may stop the medication entirely. They may not go to their GP practice to get a reauthorised action as intended.
________________________________________
effective
 Recommended
Patient Facing - View Record guidance
It is recommended to use the effective date resource (Period (start,end)). Note - The start date is not necessarily when the patient has started the medication / drug. It is when the dosage has started.
For example, when identifying how long a patient has been on x drug, it is not the x date given, since the patient can be on another / higher dose of x drug. (This is only when the patient has started the particular dosage of the drug.)
________________________________________
note
 Recommended
Patient Facing - View Record guidance
It is recommended to use note (patient notes) for PFS consumption. This is not to be confused with dispensary notes (pharmacy notes).
FHIR resource fields:
•	dosage.patientinstruction - patient note viewing (added when the drug is created, e.g. when repeat medications are created or amended)
•	dosageinstruction.text - is where the dosage instruction will be. NOT to be confused by dosage.patientinstruction. This is usually for pharmacists.
