## {{page-title}}

Patient Facing Services incorporates the GP Connect data model, this contains guidelines on how Providers need to populate each of the FHIR resources. It is advised to read the data model first, to understand how this is being populated by GP clinical systems. 

The relevant profiles in the data model are as follows:

- ReferralRequest - [CareConnect-GPC-ReferralRequest-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-ReferralRequest-1?version=current)

However, not all clinical information stored on GP systems may be safe to display for the end user (patients / citizens). This guide is intended to help Consumers understand what is clinically safe and useful to display via PFS from the GP Connect data model. Please see the PFS recommendations below.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Note</b> - We will only send outbound Referrals under this clinical area.
</div>

---