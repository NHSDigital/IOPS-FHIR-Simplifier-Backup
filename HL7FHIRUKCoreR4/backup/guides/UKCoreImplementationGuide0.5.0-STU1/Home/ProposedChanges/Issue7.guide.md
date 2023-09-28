## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>Multiple existing UK Core profiles which contain a bodySite element have had their binding changed to the UKCore-BodySite ValueSet. This ValueSet differs from the current binding for ServiceRequest.bodySite to the FHIR standard SNOMEDCTBodyStructures ValueSet by not including the top level code (i.e. is defined with &lt;442083009 (Anatomical or acquired body site (body structure) rather than &lt;&lt;442083009).</td>
<td>For consistency within the UK Core change the binding for ServiceRequest.bodySite to the UKCore-BodySite ValueSet, with an "extensible" binding strength.</td>
</tr>

</table>