## {{page-title}}

The following table outlines what the receiver (or consumer) needs to return to the sender (or provider) in the form of an ITK3 response header or FHIR `ITK-Response-OperationOutcome-1` resource.

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>Reference</th>
            <th data-no-sort>Guidance</th>
            <th data-no-sort>Description</th>
        </tr>
    </thead>
    <tbody>
        <!-- GPCM-SD-058 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-058</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body">Each instance of an acknowledgement message generated as a result of receipt of a Send Consultation Report message <b>MUST</b> include the following Workflow ID in the MESH message metadata: <code>GPFED_CONSULT_REPORT_ACK</code></td>
        </tr>
        <!-- GPCM-SD-093 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-093</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The message receiver <b>MUST</b> make any attachments included with the Consultation Report available to the end user</td>
        </tr>
        <!-- GPCM-SD-125 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-125</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Where binary documents are included in the payload in addition to the Consultation Report, the&nbsp;message receiver <b>MUST</b>&nbsp;process these accordingly, ensuring all attachments remain in the context of the encounter information delivered to downstream systems</td>
        </tr>
        <!-- GPCM-SD-126 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-126</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Receivers of replacement documents&nbsp;<b>MUST</b>&nbsp;process the replacement document and archive the replaced document</td>
        </tr>
        <!-- GPCM-SD-127 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-127</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The receiver of a replacement document&nbsp;<b>SHOULD</b>&nbsp;mark the original and any replacement documents prior to the new document as null and void and report an error to the sender using the ITK Response message and appropriate code see&nbsp;ITK3 response codes for further information</td>
        </tr>
    </tbody>
</table>