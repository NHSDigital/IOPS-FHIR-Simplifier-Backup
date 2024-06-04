## {{page-title}}

GP clinical systems may capture details of circumstances where an immunisation has not been given but there was an intention to. This version of the specification supports inclusion of intended vaccinations which were not given as defined by Digital Child Health. For details of the requirements see [National Events Management Service - Vaccinations](https://developer.nhs.uk/apis/ems-beta/vaccinations_1.html) or versions as subsequently published. If the GP clinical system holds a coded record of an intended, not given vaccination which is either outside of the scope of the ‘not done’ situation codes or the required code is not available, then the coded information should be included in an uncategorised data response.

Consumers should be aware that the presence of a vaccination not given record is only in relation to an intended vaccination event on a given day - that is, it is not stating the vaccination has definitely never been given.

<p>Consumers should be aware that the presence of a vaccination not given record is only in relation to an intended vaccination event on a given day - that is, it is not stating the vaccination has definitely never been given.</p>

<h3 id="populating-elements-for-an-immunisation-not-given">Populating elements for an immunisation not given</h3>

Specific rules are applied to the population of some of the elements where the record is for an intended immunisation which was not given.
A few of these are highlighted here.

The provider **MUST** populate elements as described below when sending details of immunisations not given within the immunisation resource.

- <code>extension[vaccinationProcedure]</code> <strong>MUST</strong> be the SNOMED CT ‘not done’ situation code for the vaccination which was intended but did not happen
- <code>notGiven</code> <strong>MUST</strong> be <code>true</code>
-  <code>explanation.reasonNotGiven</code> <strong>SHOULD</strong> be included with the appropriate code for the reason the vaccination did not happen

See  [immunization](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Immunization-1?version=current) for full details of the elements.

<h3 id="consumer-handling-of-immunisations-not-given">Consumer handling of immunisations not given</h3>

Consumer systems are to determine whether to request details of immunisations not given.
A consumer system which requires not given immunisations **MUST** request this by specifying the part parameter.
The default is to return given immunisations only.

<p>Where a consumer system has requested immunisations not given, it <strong>MUST</strong> ensure that the not given data remains clearly distinct from given vaccinations. The consumer <strong>MAY</strong> need to handle <code>explanation.reasonNotGiven</code> alongside the “not done” code to provide the classified reason the vaccination was not given.</p>