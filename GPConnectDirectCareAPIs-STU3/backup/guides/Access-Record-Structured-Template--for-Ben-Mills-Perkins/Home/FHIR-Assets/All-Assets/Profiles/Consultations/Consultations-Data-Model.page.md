## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<p><b>Note</b> - <u>Draft</u>  Consultations are <u>not</u> considered clinically safe to share with patients / citizens via PFS. They are intended just as drafts, not all of the information captured is ready to be shared. 

The GP clinical system is required to withhold Consultation in a draft state. We require Consumers to not display draft Consultations.</p>
</div>

---

Patient Facing Services incorporates the GP Connect data model, this contains guidelines on how Providers need to populate each of the FHIR resources. It is advised to read the data model first, to understand how the is being populated by GP clinical systems. 

However, not all clinical information stored on GP systems may be safe to display for the end user (patients / citizens). This guide is intended to help Consumers understand what is clinically safe and useful to display via PFS from the GP Connect data model.

The information conveyed in the Consultations profile is about the structure and not about the overall content for Consultations. For more information on [representing the different clinical areas](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development.html#representing-the-different-clinical-areas), click on the link provided.

A [consultation](https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_consultation_guidance.html#what-is-a-consultation) is the structure within which source systems group one or more clinical record entries which occurred at the same time and for the same or similar purpose attributed to or asserted by the same actor. For more information surrounding. 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b> - There are two models the clinical content can be returned for <a href=" https://gpconnect-1-5-0.netlify.app/accessrecord_structured_development_consultation_guidance.html#consultation-notes "> consultation notes </a>.
Be aware as you may receive from different payloads from GP foundation suppliers. 
</div>

---