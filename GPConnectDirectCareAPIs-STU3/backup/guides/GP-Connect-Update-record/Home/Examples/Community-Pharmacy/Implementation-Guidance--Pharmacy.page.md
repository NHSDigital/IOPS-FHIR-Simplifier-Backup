## {{page-title}}

The data items presented to the GP patient record from the pharmacy system, are based on the [pharmacy dataset](https://theprsb.org/communitypharmacyupdate2023/) and mapped to the following presentation types:

* Encounter <br>
* Observation <br>
* Medication Statement<br>

*See [dataset profiles](https://simplifier.net/guide/GP-Connect-Update-record/Home/FHIR-Assets/Profiles.page.md?version=current) for more information*

### Perspectives of dataset
The pharmacy dataset and the items presented to the the GP service may **not** align as it may not be necessary to present all the pharmacy dataset fields to the GP system. 

## Notifications
The GP service will not receive notifications regarding any updates being received from the pharmacy system.  The pharmacy service has recorded information that has updated a GP patient record and it is deemed necessary to notify the GP service the pharmacy service will need to contact the GP service outside of the update record process. For anything that needs an action (eg there may be some outcomes of a blood pressure check that require a follow up) then **this will need to be handled through a SOP (Standard Operating Procedures).**

### A note on consent
The current policy for consent from a pharmacy perspective is that all data will be recorded on the pharmacy system as required (apart from contraception). Where a patient is treated / prescribed medication through the pharmacy, where the patient/citizen has consented to this.  The data items referred to in this specification will then be sent to the GP systems (Apart from contraception).<br>

For consultations realting to contraception, the patient is asked if they are happy for anyone else to know about the information related to their contraception consultation.  Where the patient has advised that they do not wish anyone else to know about this information, then the information is not added to their GP record.


