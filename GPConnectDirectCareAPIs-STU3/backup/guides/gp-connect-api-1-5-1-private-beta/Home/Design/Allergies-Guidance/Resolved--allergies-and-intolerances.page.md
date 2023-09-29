## {{page-title}}

On some systems it is possible to explicitly mark an allergy or intolerance as resolved or ended, such that it still appears in the patient record but is no longer active and no longer interacts with prescribing decision support. This inactivation may be achieved by explicit entry of an end date or a user action that alters the status of the allergy or intolerance.

Allergies and intolerances which have been explicitly resolved <strong>MUST</strong> only be returned in response to resource queries which have the *includeResolvedAllergies* parameter set to true (see [Retrieve a patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html)).

When the provider is sending resolved allergies, it <strong>MUST</strong> send them in a separate <code class="highlighter-rouge">List</code> to the active allergies as contained resources in that <code class="highlighter-rouge">List</code>. The <code class="highlighter-rouge">List</code> <strong>MUST</strong> have the title ‘Ended allergies’ and resolved allergy resources <strong>MUST</strong> be assigned a <code class="highlighter-rouge">clinicalStatus</code> of <code class="highlighter-rouge">resolved</code>. A title of ‘Allergies and adverse reactions’ <strong>MUST</strong> be used for the <code class="highlighter-rouge">List</code> containing the active <code class="highlighter-rouge">AllergyIntolerance</code> resources. This list <strong>MUST</strong> be returned when any resolved allergies are returned as part of a consultations or problems query and the primary resolved allergies list <strong>MUST</strong> be used to create any references needed.

Consuming systems <strong>MUST</strong> ensure that resolved allergies are not treated as active - that is, they <strong>MUST NOT</strong> interact with prescribing decision support or be misinterpreted by users as being active.

Where the consuming system does not natively support a resolved allergy concept, suppliers <strong>MUST</strong> seek appropriate clinical safety advice on the handling of the resolved allergy concept.
