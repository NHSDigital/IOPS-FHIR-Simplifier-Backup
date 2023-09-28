## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The current binding for the ServiceRequest.reasonCode element is to the FHIR standard ProcedureReasonCodes ValueSet, consisting of the &lt;&lt;404684003 (Clinical finding) and &lt;&lt;71388002 (Procedure) hierarchies.

Clinicians often use investigation results as a reason for a referral. Similarly with events. Whilst it is possible to convey some of these kinds of information via a reference to another resource with that data using the reasonReference element, it may suit some implementers to be able to carry the same data within the reasonCode element instead, and therefore the ValueSet should explicitly identify further sets of concepts to support this.
</td>
<td>Create a UKCore-ServiceRequestReasonCode ValueSet that consists of the same two SNOMED CT hierarchies as within the FHIR standard ProcedureReasonCodes ValueSet and additionally the following three SNOMED CT hierarchies:

-	&lt;&lt;272379006 Event (event)
-	&lt;&lt;363787002 Observable entity (observable entity)
-	&lt;&lt;243796009 Situation with explicit context (situation)

Change the binding for ServiceRequest.reasonCode to the new UKCore-ServiceRequestReasonCode ValueSet with an "extensible" binding strength.
</td>
</tr>

</table>