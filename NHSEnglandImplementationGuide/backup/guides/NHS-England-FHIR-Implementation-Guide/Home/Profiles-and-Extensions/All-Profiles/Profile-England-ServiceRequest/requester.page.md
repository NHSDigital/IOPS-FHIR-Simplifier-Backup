## `requester`

<table class="regular assets">
<tr>
<td>Element Id</td>
<td>ServiceRequest.requester</td>
</tr>
<tr>
<td> <a href='https://www.hl7.org/fhir/conformance-rules.html#cardinality' target="_blank">Cardinality</a></td>
<td> 1..1</td>
</tr>
<td> <a href='https://www.hl7.org/fhir/datatypes.html' target="_blank">type</a></td>
<td> <a href='https://www.hl7.org/fhir/datatypes.html#Extension' target="_blank">Reference</a>({{pagelink:Profile-England-PractitionerRole, text:England-Practitioner}})<br/> Aggregation - <a href="http://www.hl7.org/fhir/valueset-resource-aggregation-mode.html" target="_blank">contained</a>  </td>
</tr>
</table>
<br/>

#### Definition
Who is created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.

This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry.

**e-RS**

The contained PractitionerRole must contain

- SDS User ID of the Referrer in `practitioner`
- ODS Code of the Referring Organisation in `organization`<br>
---