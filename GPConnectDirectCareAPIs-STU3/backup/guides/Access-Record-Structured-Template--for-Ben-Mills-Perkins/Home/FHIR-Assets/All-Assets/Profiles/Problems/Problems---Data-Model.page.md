## {{page-title}}

Patient Facing Services incorporates the GP Connect data model, this contains guidelines on how Providers need to populate each of the FHIR resources. It is advised to read the data model first, to understand how the is being populated by GP clinical systems. 

However, not all clinical information stored on GP systems may be safe to display for the end user (patients / citizens). This guide is intended to help Consumers understand what is clinically safe and useful to display via PFS from the GP Connect data model.

The relevant profiles in the data model are as follows:

- Problem - [CareConnect-GPC-ProblemHeader-Condition-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ProblemHeader-Condition-1?version=current)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b> - This profile provides the ‘problem header’ that identifies a record of a problem item in a patient GP record. Problems are associated to other Problems e.g., a cough can be a problem which evolves into pneumonia. Problems will often also be associated to other information in the patient record such as and not limited to tests run relating to the problem, medications prescribed for the problem, observations taken in managing the problem and referrals to other care settings for problem management. If the Consumer wants to show the full history related to a problem, the resource described here will provider pointers to that information. However, Consumers will need to be able to handle the other information types as described in the other clinical areas to fully represent that additional detail.
</div>

---