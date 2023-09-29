## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">

<b>Note</b> - This clinical area differs from others in that whilst other clinical areas represent a standard attribution of data in the GP clinical systems. This area is to represent those other areas where there is inconsistent attribution across clinical concepts such as procedures, family history, measurements and many more. As these boundaries are not consistent, we have decided to represent them in a single clinical area. We understand that this is unlikely to be the manner in which a Consumer wants to represent this data.

It is expected that Consumers will either use this data along with other clinical areas to create aggregated journal type views or use subsets of this data. Or by Identifying categories of coding that meets a specific need for the application, for example representing end of life information.

As a general recommendation, we do not expect this to be useful to the patient / citizen by just presenting this as full clinical area in isolation.
</div>

Patient Facing Services incorporates the GP Connect data model, this contains guidelines on how Providers need to populate each of the FHIR resources. It is advised to read the data model first, to understand how this is being populated by GP clinical systems. 

The relevant profiles in the data model are as follows:

- Observation - [CareConnect-GPC-Observation-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current)

However, not all clinical information stored on GP systems may be safe to display for the end user (patients / citizens). This guide is intended to help Consumers understand what is clinically safe and useful to display via PFS from the GP Connect data model. Please see the PFS recommendations below.

---
