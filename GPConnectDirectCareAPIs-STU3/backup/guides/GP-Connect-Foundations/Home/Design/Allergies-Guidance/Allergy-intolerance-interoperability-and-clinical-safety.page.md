## {{page-title}}

It is recognised that allergy/intolerance information may not be fully interoperable between participating systems. Where allergy/intolerance information is not fully understood by a receiving system then it is the responsibility of the receiver to mitigate any risks arising and make related workflows as safe as possible.

Where allergy/intolerance information is integrated into the consuming system patient record then allergy/intolerance information <strong>MUST</strong> be degraded where the coded allergy/intolerance information is not fully understood by the consumer. In the context of drug allergies, an allergy/intolerance is only understood if the coded causative agent triggers equivalent prescribing decision support to that triggered on the producing system.

Degradation can be handled by coding the record entries resulting from the processed allergy as (<code class="highlighter-rouge">196461000000101</code>, Transfer-degraded drug allergy) and preserving the original term for the received code as text.

Where the processing of drug allergy <code class="highlighter-rouge">AllergyIntolerance</code> resources results in degradation or the FHIR resource being processed is already coded as a degrade drug allergy code (<code class="highlighter-rouge">196461000000101</code>, Transfer-degraded drug allergy) then the consuming system <strong>MUST</strong> prevent prescribing while degraded drug allergies are present in the patient record and inform users attempting prescribing actions that prescribing is prevented due to the presence of degraded drug allergies.

In other contexts, task-based workflows have been utilised to assist users on consuming systems to process degraded drug allergies by re-coding them to concepts understood by the consuming system.

*When considering the implementation of use cases involving allergy/intolerance interoperability suppliers <strong>MUST</strong> perform an appropriate clinical safety assessment and obtain the necessary clinical safety approvals for the processing performed by their system.*