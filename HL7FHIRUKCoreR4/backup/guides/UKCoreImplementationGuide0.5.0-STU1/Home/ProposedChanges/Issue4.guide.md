## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
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

</table>