<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body"><i class="fa fa-exclamation-triangle"></i><b>Version:</b>This is the <b>current 0.x (DSTU2) version</b> of GP Connect API for building the <b>Access Record HTML</b> capability only. For other capabilities and specifications, please visit the link below.</div>

[GP Connect specifications page](https://developer.nhs.uk/gp-connect-specification-versions)

## {{page-title}}

Introduction to the GP Connect Access Record HTML capability.

##HTML view

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fas fa-exclamation-circle text-primary"></i> <b>Information</b> For Direct Patient Care purposes only, the Primary Care record contains a wealth of useful information which can improve patient safety and efficiency if it is made interoperable across health care settings (subject to IG and Clinical Safety requirements which consumers MUST meet and confirm compliance with during assurance).
<br>
<br>
Access Record HTML is delivering the capability to view a patient record and <b>MUST</b> be used in real time for read only.
<br>
<br>
Please refer to the FAQ at the link below for details of what constitutes direct patient care.
</div>

[NHS Digital - FAQ on legal access to personal confidential data - Definitions questions - How is Direct Patient Care defined?](http://content.digital.nhs.uk/article/3638/Personal-data-access-FAQs) 

### Purpose
In an unstructured and pre-rendered format (HTML), this capability will provide health professionals with access to a patient’s primary care record by requesting sections or headings. Where appropriate, a date range can be defined to filter the retrieval of larger sections. These views can be incorporated directly into Electronic Patient Record systems.

The content displayed in the HTML views has then been used as a common baseline of available data to guide the structured and coded ‘Access Record’ approach.

Significant effort has already been made to unify the HTML section views from all four principal suppliers but it is expected that this will be an iterative process during development, UAT and FoT.

### Scope

The information sections in scope for care record access are:
1. [Summary](accessrecord_view_summary.html)
2. [Encounters](accessrecord_view_encounters.html)
3. [Clinical items](accessrecord_view_clinical_items.html)
4. [Problems and issues](accessrecord_view_problems.html)
5. [Allergies and adverse reactions](accessrecord_view_allergies.html)
6. [Medications](accessrecord_view_medications.html)
7. [Referrals](accessrecord_view_referrals.html)
8. [Observations](accessrecord_view_observations.html)
9. [Immunisations](accessrecord_view_immunisations.html)
10. [Administrative items*](accessrecord_view_administrative_items.html)

**[Links above will need updating to simplifier]**

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fas fa-exclamation-circle text-primary"></i> <b>Note:</b> sections of the patient care record (marked above with a *) may not initially be available from all primary care record Principal systems.</div>

### Use cases

- extended access GP practices can view all of the patient’s primary care views even when the record is held on a different GP system
- other care settings (e.g. 111, Physio, Community, Emergency, Acute/Secondary, Social) can view the patient’s GP record (those held by the patient’s recorded GP practice) to better inform care decisions they may be making for a patient

### Profiled FHIR resources
Please refer to the [AccessRecord HTML FHIR Resources](https://developer.nhs.uk/apis/gpconnect-0-7-4/datalibraryaccessRecord.html) page for details of the FHIR profiles utilised for the Access Record HTML operation.

**[The link above needs updating with simplifier page]**

### Spine Interactions
The Access Record HTML capability message set includes the following set of Spine interactions:
    InteractionID     

|Operation| InteractionID|
|-
|[Get Care Record](accessrecord_use_case_retrieve_a_care_record_section.html)|`urn:nhs:names:services:gpconnect:fhir:operation:gpc.getcarerecord`

**[The link above needs updating with simplifier page]**

