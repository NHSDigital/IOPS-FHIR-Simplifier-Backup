## {{page-title}}

The following table outlines what the receiver (or consumer) needs to return to the sender (or provider) in the form of an ITK3 response header or FHIR `ITK-Response-OperationOutcome-1` resource.

<table data-responsive=>
    <thead>
        <tr>
            <th data-no-sort>Reference</th>
            <th data-no-sort>Guidance</th>
            <th data-no-sort>Description</th>
        </tr>
    </thead>
    <tbody>
        <!-- GPCM-SD-050 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-050</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>Extension-ITK-MessageHandling-2</code> resource with the value <code>false</code>, populated in the <code>BusAckRequired</code> element</td>
        </tr>
        <!-- GPCM-SD-051 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-051</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>Extension-ITK-MessageHandling-2</code> resource with the value <code>false</code>, populated in the <code>InfAckRequired</code> element</td>
        </tr>
        <!-- GPCM-SD-052 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-052</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>Extension-ITK-MessageHandling-2</code> resource with the unique identifier of the activity which took place at the sending organisation, populated within the <code>SenderReference</code> element</td>
        </tr>
        <!-- GPCM-SD-053 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-053</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-ITK-Header-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-ITK-Header-Organization-1" class="nhsd-a-link">Profile: CareConnect-ITK-Header-Organization-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-ITK-Header-Organization-1</code> in the <code>ITK-Message-Bundle-1</code> profile</td>
        </tr>
        <!-- GPCM-SD-054 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-054</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>ITK-MessageHeader-2</code> resource, populated with a fixed value of <code>ITK008M</code>, taken from the <a href="https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2" class="nhsd-a-link">ITK-MessageEvent-2</a> code system, within the <code>event</code> element</td>
        </tr>
        <!-- GPCM-SD-055 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-055</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>ITK-MessageHeader-2</code> with the date and time of when the message was generated, populated within the <code>timestamp</code> element
            <br><br><div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Note</b>: A seperate process (such as the MESH client) may be responsible for sending the message at a later date and time.</div></td>
        </tr>
        <!-- GPCM-SD-065 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-065</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/Build/Error-handling?version=1.3.2-public-beta" title="Home/Build/Error-handling" class="nhsd-a-link">Error handling</a></td>
            <td class="nhsd-t-body">Where the received message does not conform to the requirements stated for ITK3 header, or for the payload, the message <b>MUST</b> be considered invalid</td>
        </tr>
        <!-- GPCM-SD-066 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-066</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/Build/Error-handling?version=1.3.2-public-beta" title="Home/Build/Error-handling" class="nhsd-a-link">Error handling</a></td>
            <td class="nhsd-t-body">Where a received message is invalid, an ITK3 Response <b>MUST</b> be generated, with the corresponding negative ITK3 Response Code which indicates the nature of the error, and the message <b>MUST NOT</b> be accepted for downstream processing</td>
        </tr>
        <!-- GPCM-SD-074 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-074</span></td>
            <td class="nhsd-t-body">
                <a href="/guide/gp-connect-send-document/Home/Build/Error-handling?version=1.3.2-public-beta" title="Home/Build/Error-handling" class="nhsd-a-link">Error handling</a>
                |
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Response-OperationOutcome-1" title="Home/FHIR-Assets/All-assets/FHIR-Assets/All-assets/Profiles/Profile--ITK-Response-OperationOutcome-1?version=1.3.2-public-beta" class="nhsd-a-link">Profile: ITK-Response-OperationOutcome-1</a>
            </td>
            <td class="nhsd-t-body">The context and description <b>MUST</b> be provided in the <code>ITK-Response-OperationOutcome-1.diagnostics</code> element to enable the sender of the originating message to correctly identify the error with their payload</td>
        </tr>
    </tbody>
</table>