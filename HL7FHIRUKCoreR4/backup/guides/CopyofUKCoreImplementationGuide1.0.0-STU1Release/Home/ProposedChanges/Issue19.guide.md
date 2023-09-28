## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>There is deemed to be a need to extend the MessageHeader to allow the ability to carry specific instructions for receivers of the message. For example please send an acknowledgement to confirm reciept of this message. This is to allow the use case for ITK3 to be supported.</td>
<td>Add a extension to the UK Core MessageHeader profile which will use a code/value pair appoach to allow defintion of a common set of coded values to specify the behaviour required. Further details of the approach will be shared if the need for this extension is confirmed by reviewers.There is also a use case to add the <a href="http://hl7.org/fhir/valueset-messageheader-response-request.html">Common extension messageheader-response-request</a> to the message header for the response part of ITK3. Feedback from the UK FHIR community would be helpful in sorting out a UK wide messaging behaviour.</td>
</tr>

</table>

