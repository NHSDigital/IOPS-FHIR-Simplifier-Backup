## {{page-title}}

The above section addresses circumstances where an immunisation is not given at the point of intending to give the vaccine.
GP Systems may capture other coded information relating to vaccinations other than the administration of the vaccine in an immunisations feature / module / categorisation.
This may be information regarding consent, dissent, invitations for vaccination, etc.
Where provider categorise such coded information as immunisation data, then it **MUST** only return it against an immunisation request.
GP Connect includes the parameter <code class="highlighter-rouge">includeStatus</code> to enable the consumer to specify the inclusion / exclusion of this information.
See [Retrieve a patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html) for full details of the parameter use.

Such coded records <strong>MUST</strong> be included with the immunisation bundle using an <code>observation</code> resource, as defined for <a href="accessrecord_structured_development_observation_uncategoriseddata.html">[uncategorised data](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Observation-1?version=current).

Records returned against an immunisation request under the scope of this definition <strong>MUST</strong> be

- excluded from the records returned for an uncategorised data request
- included in the immunisations <code class="highlighter-rouge">List</code>

Consumers shoud note than GP Systems differ with respect to additional information categorised as immunisations, therefore the same coded data may be returned against an immunisation or uncategorised data request by different provider systems.

<h3 id="ended-records">Ended records</h3>

<p>Where a GP clinical system allows a consent or dissent to be ended, then the <code>observation.effective</code> element <strong>MUST</strong> be populated with a <code>Period</code> including the relevant start and end dates.</p>

<p>This does not apply if the consent or dissent has been ended as “entered in error”, in which case the record <strong>MUST NOT</strong> be included.</p>

<h3 id="multiple-records">Multiple records</h3>

<p>If a patient record has multiple records of consent for a single type of vaccination, for example a dissent and a consent, then all records <strong>MUST</strong> be included.</p>

<h3 id="degraded-records">Degraded records</h3>

<p>Any records which the GP clinical systems classifies as an immunisation consent or dissent, but which do not appear in the hierarchies above <strong>MUST</strong> also be included.
Where there is an appropriate code which is outside of the stated hierarchy, then that <strong>MAY</strong> be used.
Where there is no identifiably appropriate SNOMED CT code for the consent or dissent, then the transfer degraded code <strong>MUST</strong> be used with a text element populated with the original text.</p>

ConceptId - `196411000000103`
DescriptionId - `294691000000115`
Description - `Transfer-degraded record entry`