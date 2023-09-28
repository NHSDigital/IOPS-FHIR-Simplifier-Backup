## `source`

<b>Definition</b><br>

`source.endpoint` is required and **MUST** indicate the address where replies are to be sent.

 <table class="regular assets">
<tr>
<td>Element Id</td>
<td>MessageHeader.source</td>
</tr>
<tr>
<td> <a href='https://www.hl7.org/fhir/conformance-rules.html#cardinality' target="_blank">Cardinality</a></td>
<td> 1..1</td>
</tr>
<tr>
<td> <a href='https://www.hl7.org/fhir/datatypes.html' target="_blank">Type</a></td>
<td> <a href='https://www.hl7.org/fhir/datatypes.html#BackboneElement' target="_blank">BackboneElement</a> </td>
</tr>
</table>

<br/>

- For responses to be received via http this will be the address of the `$process-message` endpoint.
- For MESH this will follow [ITK2.2 MESH Transport Requirements](https://data.developer.nhs.uk/architecture/itk/Docs/ITK%20MESH%20Transport%20%20Requirements.pdf) for ITK Routing. E.g. the MESH Endpoint for Organisation B80310 

---