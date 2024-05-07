## {{page-title}}

It is the responsibility of the consuming system to decide what data to request from the provider systems. When determining how wide to make the search criteria, the consumer system must consider the following guidelines:

- Always apply the [Caldicott Principles](https://www.igt.hscic.gov.uk/Caldicott2Principles.aspx)
- The first API query on a patient should aim to retrieve the amount of data required to support the majority of queries that their clinician/user will make whilst avoiding the retrieval of large quantities of unnecessary data
- Where a follow-up query is required it should aim to retrieve sufficient data to support any other queries that their clinician/user will make
- The consumer system should aim to avoid scenarios where more than two queries are required on the same patient as part of the same local interaction with a clinician/user. This does NOT preclude the consumer system from making further queries where necessary to support patient care.
- It is acceptable for the consumer system to request and retrieve a large proportion of the patient’s record from the provider system and filter out the unnecessary data before presenting it to their clinicians/users where the consumer organisation:
    
    - has determined it is necessary to support patient care
    - has met all of the GP Connect information governance (IG) requirements including data sharing agreements, confidentiality and auditing

The details on how this is implemented in an API can be found in the [API Definition - Retrieve a patient's structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html).

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
	<i class="fa fa-exclamation-triangle"></i> <b>To do:</b> Update link to API when available in API catalogue.
</div>