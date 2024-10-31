## {{page-title}}

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b>


- The implementation guidance is for most standard use cases of presenting elements in Consumer applications (envisaged to be implemented for mobile interface). It does not prohibit other specific use cases, but that appropriate assessment is encouraged.

- Support from the programme team will be available to Consumers with alternative use cases to assist them with understanding the available data and applicability to alternative presentation. This is to provide appropriate information from which Consumers can make their own hazard evaluations and develop their own clinical safety case.

- The implementation guidance is currently in a draft stage. It will continually be refined over time through user research and understanding of further use cases.

- The implementation guidance is not intended to replace or serve as a substitute for any audit or professional orders. It is advised to consult NHS Digital for advice concerning any use cases or other matters before making any decisions.
</div>

<div class="alert alert-info nhsd-t-body" role="alert">
<i class="fa fa-info-circle"></i> <b>Note:</b> Before moving to the profiles, it is worth noting how each element is separated (Located here - {{pagelink:Home/Introduction/How-to-use-the-implementation-guide/Data-model-labels-used-within-this-guidance.page.md}}). 
</div>

This capability uses the CareConnect profiles intertwined within each clinical area below. Each area will give advice on what is safe and useful to display for patient / citizen viewing.

- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Allergies}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Medications}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Immunisations}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Consultations}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Problems}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Investigations}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Referrals}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Documents}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Diary-entries}}
- {{pagelink:Home/FHIR-Assets/All-Assets/Profiles/Uncategorised-data}}

<br> </br>

Provision of each clinical area is controlled by the practice. The practice can restrict provision of each clinical area. These restrictions can either be applied at practice level i.e. for all patients or to an individual patient. Restriction applied on individual patient takes precedence. More on information can be found on {{pagelink:Home/Design/Redactions}}.

Requesting clinical areas or data items inside clinical areas will depend on configuration set by the practice. In case requested data item is restricted by the practice, either for all patients or current patient, no data will be retrieved.
