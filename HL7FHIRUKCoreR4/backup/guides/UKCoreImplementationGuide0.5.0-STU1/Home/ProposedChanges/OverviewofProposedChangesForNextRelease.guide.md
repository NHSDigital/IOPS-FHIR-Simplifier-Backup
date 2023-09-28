## {{page-title}}
This section documents proposed changes to be applied to the UK Core for the next release. These are highlighted to allow reviewers to comment on the proposed changes. Solutions for the issues which lead to these proposed changes may have been discussed on the C&TA sprint calls but can still be challenged by any reviewer.

<table id="assets">
<tr>
<th width="5%">Number</th>
<th width="50%">Issue</th>
<th width="45%">Proposal</th>
</tr>

<tr>
<td>{{pagelink:Issue1-050}}</td>
<td>The current binding for the Appointment.specialty, HealthcareService.specialty, Schedule.specialty and Slot.specialty elements is to the FHIR standard "PracticeSettingCodeValueSet" with a "preferred" binding strength in each case.

Comments have previously been made in Sprint 1 that a UK Core ValueSet should be considered for the PractitionerRole.specialty element, and further comments supporting that position have been made against the release 0.1.0 HL7UK ballot.

The ballot comment is due to be discussed at weekly reconciliation meetings by members of the HL7UK board and others.
</td>
<td>Any UK Core decision regarding the ValueSet binding for PractitionerRole.specialty agreed by HL7UK will be applied to the Appointment.specialty, HealthcareService.specialty, Schedule.specialty and Slot.specialty elements.<br/><br/>Update 12/05/2022: Any changes agreed by HL7UK will be made in a later UK Core release.</td>
</tr>

<tr>
<td>{{pagelink:Issue2-050}}</td>
<td>The current binding for the HealthcareService.communication element is to the FHIR standard CommonLanguages ValueSet. A comment has been made against the release 0.1.0 HL7UK ballot suggesting that consideration should be given to aligning the ValueSet binding for the Practitioner.communication and RelatedPerson.communication.language elements to the same ValueSet as with Patient.communication, which is to the UKCore-HumanLanguage ValueSet.</td>
<td>Any UK Core decision regarding the ValueSet binding for Practitioner.communication and RelatedPerson.communication.language agreed by HL7UK will be applied to the HealthcareService.communication element.</td>
</tr>

<tr>
<td>{{pagelink:Issue3-050}}</td>
<td>The current binding for the Appointment.appointmentType element is to the FHIR standard v2.0276 (Appointment Reason Codes) ValueSet. The CodeSystem in this ValueSet seems to mix a number of axes of concept (e.g. kind of consultation, urgency of appointment etc), yet only single instance of the Appointment.appointmentType element is allowed.

Given the restriction to just a single instance of this data, one additional concept that may have a use in the UK is "urgent follow-up".
</td>
<td>Create a UKCore-AppointmentReasonCode Code System consisting of a single "Urgent follow-up" concept.

Create a UKCore-AppointmentReasonCode ValueSet consisting of the entirety of the standard v2.0276 and UKCore-AppointmentReasonCode CodeSystems.

Change the binding of Appointment.appointmentType to the new UKCore-AppointmentReasonCode ValueSet with an "extensible" binding strength.
</td>
</tr>

<tr>
<td>{{pagelink:Issue4-050}}</td>
<td>The current binding for the ServiceRequest.code element is to the FHIR standard "Procedure Codes (SNOMED CT)" ValueSet (https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/83651), which refers to the &lt;&lt;71388002 (Procedure) SNOMED CT hierarchy.

Elements in other UK Core profiles where the &lt;&lt;71388002 (Procedure) SNOMED CT hierarchy is used have a binding to the UKCore-ProcedureCode ValueSet ({{pagelink:ValueSetUKCore-ProcedureCode}}), which refers to both the &lt;&lt;71388002 (Procedure) and &lt;&lt;129125009 (Procedure with explicit context) SNOMED CT hierarchies.
</td>
<td>Change the binding for the ServiceRequest.code element to be the UKCore-ProcedureCode ValueSet.

Include guidance to not use the "referral by [person/service] / referral to [person/service]" type concepts if the data is covered by other elements.

Include guidance to explain the SNOMED Expression Constraint Language (ECL) used in the ValueSet definition.

Use the "preferred" binding strength.

Some Sprint 5 Call 3 discussion points:

-	Adding concepts to the ValueSet which include context depends to some extent on whether the lifecycle of the ServiceRequest resource is covered by other elements within the resource (e.g. status, intent, doNotPerform).
-	It is understood that the Procedure hierarchy should cover all things that are likely to be requested e.g. enrolment on a care plan, referral for physiotherapy.
-	As the ServiceRequest resource is intended to be used for general referrals, there could be duplication of context carried within the .code element as well as other elements but this is not considered an issue.
-	The hierarchy with explicit context will include "referral by [person/service]" and "referral to [person/service]" concepts there is potentially overlap with further elements of the ServiceRequest resource. If any such concepts are not appropriate for the .code element then it would be expected that systems would recognise this rather than it being appropriate to explicitly exclude parts of this hierarchy within a ValueSet definition.</td>
</tr>

<tr>
<td>{{pagelink:Issue5-050}}</td>
<td>The current binding for the ServiceRequest.orderDetail element is to the FHIR standard
ServiceRequestOrderDetailsCodes ValueSet. This consists of a small number of example SNOMED CT concepts that might be used in relation to a patient ventilation order.

The use of text might be considered more appropriate for the type of data that the definition describes.

Currently there is no BARS use case for this element.
</td>
<td>Guidance will be created to state that this element should be used with caution as there is no specific UK use case identified for it.</td>
</tr>

<tr>
<td>{{pagelink:Issue6-050}}</td>
<td>The current binding for the ServiceRequest.reasonCode element is to the FHIR standard
 ProcedureReasonCodes ValueSet, consisting of the &lt;&lt;404684003 (Clinical finding) and &lt;&lt;71388002 (Procedure) hierarchies.

Clinicians often use investigation results as a reason for a referral. Similarly with events. Whilst it is possible to convey some of these kinds of information via a reference to another resource with that data using the reasonReference element, it may suit some implementers to be able to carry the same data within the reasonCode element instead, and therefore the ValueSet should explicitly identify further sets of concepts to support this.
</td>
<td>Create a UKCore-ServiceRequestReasonCode ValueSet that consists of the same two SNOMED CT hierarchies as within the FHIR standard ProcedureReasonCodes ValueSet and additionally the following three SNOMED CT hierarchies:
&lt;&lt;272379006 Event (event)
&lt;&lt;363787002 Observable entity (observable entity)
&lt;&lt;243796009 Situation with explicit context (situation)

Change the binding for ServiceRequest.reasonCode to the new UKCore-ServiceRequestReasonCode ValueSet with an "extensible" binding strength.
</td>
</tr>

<tr>
<td>{{pagelink:Issue7-050}}</td>
<td>Multiple existing UK Core profiles which contain a bodySite element have had their binding changed to the UKCore-BodySite ValueSet. This ValueSet differs from the current binding for ServiceRequest.bodySite to the FHIR standard SNOMEDCTBodyStructures ValueSet by not including the top level code (i.e. is defined with &lt;442083009 (Anatomical or acquired body site (body structure) rather than &lt;&lt;442083009).</td>
<td>For consistency within the UK Core change the binding for ServiceRequest.bodySite to the UKCore-BodySite ValueSet, with an "extensible" binding strength.</td>
</tr>

<tr>
<td>{{pagelink:Issue8-050}}</td>
<td>Whilst the Task profile was included within the scope of UK Core Clinical &amp; Technical Assurance Sprint 5, and may be used extensively in the future in relation to bookings and referrals, it has not been used by the BaRS programme in its First of Type payloads.</td>
<td>As there is currently no specific use case for the Task profile, this profile will continue to exist in the UK Core as a "draft" profile but it will not be promoted to an "active" status as part of Sprint 5. Pages for and references to the Task profile will be removed from the Implementation Guide.</td>
</tr>

<tr>
<td>{{pagelink:Issue9-050}}</td>
<td>For both Questionnaire.code and Questionnaire.item.code there is an example binding to a FHIR standard ValueSet with a definition of the whole of LOINC. LOINC is generally not used in the UK.
</td>
<td>Create a UKCore-SNOMEDCT ValueSet consisting of the whole of SNOMED CT.

Change the binding of Questionnaire.code to the new UKCore-SNOMEDCT ValueSet. This reflects a more preferred default CodeSystem for the UK Core than LOINC but may require further discussion in the future.

For the Questionnaire.item.code element, SNOMED CT is not a suitable default CodeSystem. In the absence of any specific CodeSystem requirements at this level, the proposal is to remove the current FHIR standard binding and leave this element unbound.<br/><br/>Update 12/05/2022:<br/>- The ValueSet used for binding to the Questionnaire.code element has been called UKCore-QuestionnaireQuestionCodes.<br/>- No change to the binding of the Questionnaire.item.code element has been made as it has not been possible to revert to unbound where a binding has already been specified in the FHIR standard profile.
</td>
</tr>

<tr>
<td>{{pagelink:Issue10-050}}</td>
<td>The UKCore-ServiceRequestMethod extension was created for Sprint 5 based on the Care Connect ReferralMethod extension. There is no identified use case for this extension.
</td>
<td>Retire or remove the UKCore-ServiceRequestMethod extension from the UK Core.
</td>
</tr>

</table>