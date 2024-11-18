## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - <u>Draft</u> Consultations are <u>not</u> considered clinically safe to share with patients/citizens via PFS. They are intended just as drafts, not all of the information captured is ready to be shared. 

The GP clinical system is required to withhold Consultations in a draft state. We require consumers to not display draft Consultations.</p>
</div>

---

Patient Facing Services incorporates the GP Connect data model. This contains guidelines on how providers need to populate each of the FHIR resources. It is advised to read the data model first, to understand how this is being populated by GP clinical systems. 

The information conveyed in the Consultations is about the structure and not about the overall content for Consultations. For more information on [representing the different clinical areas](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development.html#representing-the-different-clinical-areas), click on the link provided.

The relevant profiles in the data model are as follows:

* List - [CareConnect-GPC-List-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current)

* Encounter - [CareConnect-GPC-Encounter-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Encounter-1?version=current)


However, not all clinical information stored on GP systems may be safe to display for the end user (patients/citizens). This guide is intended to help consumers understand what is clinically safe and useful to display via PFS from the GP Connect data model. Please see the PFS recommendations below.

A [consultation](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_consultation_guidance.html#what-is-a-consultation) is the structure within which source systems group one or more clinical record entries which occurred at the same time and for the same or similar purpose attributed to or asserted by the same actor.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b> - There are two models the clinical content can be returned for <a href=" https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_consultation_guidance.html#consultation-notes "> consultation notes </a>.
Be aware as you may receive from different payloads from GP Foundation suppliers. 
</div>

---