## {{page-title}}

The <code class="highlighter-rouge">AllergyIntolerance</code> FHIR resource has been developed to address current allergy and intolerance interoperability limitations. As such, it has been designed to enable a future state in which greater levels of allergy and intolerance interoperability are achieved by utilisation of SNOMED CT and NHS dictionary of medicines and devices (dm+d) concepts from the specified allergy and intolerance subset.

The FHIR structure and standard is only an enabler for greater drug allergy interoperability. Drug allergy interoperability is only achieved when drug allergy concepts are understood by receiving systems - that is, they trigger equivalent prescribing decision support. Therefore, the benefits will not be achieved without participating systems being able to consistently process codes from the defined causative agent subset as concepts capable of triggering prescribing decision support in receiving systems.

The system change to converge the coding of causative agents to the specified subset and make the causative agent subset consistently processable (by prescribing decision support modules across participating systems) falls outside the scope of this guidance.

In the interim state it is expected that with the gradual adoption of the FHIR resource and associated terminologies, drug allergy interoperability will continue to be partial.

The <code class="highlighter-rouge">AllergyIntolerance</code> resource adopts common approaches for expressing certainty and severity, increasing interoperability of qualifiers associated with allergies and intolerances.

<p>Greater expressivity around dates (end dates, onset, occurrence) is also supported.</p>

<p>It is recognised that current support for the full range of severity qualifiers is limited and variable across systems, and existing support for the full range of date concepts will also be limited.</p>

<p>It is also recognised that there will be interim challenges in mapping existing allergy and intolerance record structures to the <code class="highlighter-rouge">AllergyIntolerance</code> resource. In some systems, allergy and intolerance information may be a post-coordinated triple of allergy code, reaction/manifestation code and causative agent code. In other systems, a single pre-coordinated code serves to describe the allergy/intolerance concept and the causative agent. In the former case, the <code class="highlighter-rouge">AllergyIntolerance</code> resource may not fully support the three coded concepts and in the latter case, there is currently no distinct identification of causative agent and reaction/manifestation.</p>
