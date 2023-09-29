## {{page-title}}

There are 2 parameters that can be specified while retrieving medications. A search from date and a boolean that can be set to ‘false’ in order to exclude medication issues.

As a default, the medication issues are always included in the bundle that is returned. If the consumer specifically wants to retrieve the medication items without any of the issues, then this <strong>MUST</strong> be specified in the request - in this case only the authorisations will be returned. That is, the <code class="highlighter-rouge">MedicationStatement</code> and <code class="highlighter-rouge">MedicationRequest</code> with <code class="highlighter-rouge">intent</code> set to <code class="highlighter-rouge">plan</code> for each medication item.

Below is a further detail about how the search criteria should be applied:

- Search for all Medications and Medical Devices that were active on or after the specified date
    - The consumer system requests all items from a start date
    - The provider system returns all authorisations (MedicationStatement and              MedicationRequest with intent set to ‘plan’) whose effective period end date         is null or is on or after the start date
    - Where no date is supplied by the consumer, all medications and medical devices       are returned
- Do not include all the prescriptions issued under the returned medication/medical device authorisations
    - The consumer system requests not to include prescription issues</li>
    - For each of the returned medication/medical device item, the provider system         only includes the authorisations
    
Technical details relating to the search criteria are available on the [Retrieve a patient’s structured record page](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html).
