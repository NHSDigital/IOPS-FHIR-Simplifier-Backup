## {{page-title}}

As noted above, inbound referrals are to be returned using observation resources as per this guidance. The following additions / exceptions apply to the population of elements, otherwise populate as per the {{pagelink:Home/Design/Uncategorised-data-guidance }}.

- Where known, the referrer details **MUST**| be returned using the performer element
- The performer element **MAY** be absent, for example if the referrer is not recorded
- Self referrals **MUST** be identified by including the text "Self referral" in the comment element

Additional fields capturing details of the referral in the source system **SHOULD** be returned in the component

- Populate `Component.code.text` with the data label
- Populate `Component.value` with the data item code / text


Any document(s) linked to the referral **MUST** be returned in [DocumentReference](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DocumentReference-1?version=current) resource(s) containing reference(s) to the related referral.

---