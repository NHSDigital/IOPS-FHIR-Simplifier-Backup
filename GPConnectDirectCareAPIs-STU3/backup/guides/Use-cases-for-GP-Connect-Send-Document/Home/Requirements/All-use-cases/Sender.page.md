## {{page-title}}

The following table outlines what the sender (or provider) needs to provide for all GP Connect Send Document use cases.

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>Reference</th>
            <th data-no-sort>Guidance</th>
            <th data-no-sort>Description</th>
        </tr>
    </thead>
    <tbody>
        <!-- GPCM-C-1 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-C-1</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body">MESH <b>MUST</b> be used as the message transport mechanism</td>
        </tr>
        <!-- GPCM-C-2 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-C-2</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Design/Using-ITK3?version=1.3.2-public-beta" title="Home/Design/Using-ITK3" class="nhsd-a-link">Using ITK3</a></td>
            <td class="nhsd-t-body">All FHIR Messages <b>MUST</b> conform to the ITK3 Message Distribution Standard, v2.10.0</td>
        </tr>
        <!-- GPCM-SD-028 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-028</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1" class="nhsd-a-link">Profile: CareConnect-Organization-1</a></td>
            <td class="nhsd-t-body">The payload&nbsp;<b>MUST</b>&nbsp;contain a FHIR <code>CareConnect-Organization-1</code> resource describing the sender organisation (the originating practice)</td>
        </tr>
        <!-- GPCM-SD-029 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-029</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1" class="nhsd-a-link">Profile: CareConnect-Organization-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a <code>CareConnect-Organization-1</code> resource with the sending organisation ODS Organisation Code, populated in the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element</td>
        </tr>
        <!-- GPCM-SD-030 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-030</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1" class="nhsd-a-link">Profile: CareConnect-Organization-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Organization-1</code> resource with the name of the organisation, populated in the <code>name</code> element</td>
        </tr>
        <!-- GPCM-SD-031 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-031</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1" class="nhsd-a-link">Profile: CareConnect-Organization-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>CareConnect-Organization-1</code> resource with the telephone number of the sending organization, populated in the <code>telecom</code> element, where&nbsp;<code>telecom.system</code>&nbsp;contains a fixed value of&nbsp;<code>phone</code>, and&nbsp;<code>telecom.value</code>&nbsp;contains the telephone number</td>
        </tr>
        <!-- GPCM-SD-032 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-032</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1" class="nhsd-a-link">Profile: CareConnect-Practitioner-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Practitioner-1</code> resource with the sending practitioner SDS User ID, populated in the <code>sdsUserId</code> slice of the <code>identifier</code> element</td>
        </tr>
        <!-- GPCM-SD-033 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-033</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1" class="nhsd-a-link">Profile: CareConnect-Practitioner-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Practitioner-1</code> resource with the official name of the sending practitioner, populated in the <code>name</code> element, and the <code>name.use</code> element must contain the value: <code>official</code></td>
        </tr>
        <!-- GPCM-SD-034 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-034</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1" class="nhsd-a-link">Profile: CareConnect-Practitioner-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Practitioner-1</code> resource with the telephone number of the sending practitioner, populated in the <code>telecom</code> element if it is available, where the&nbsp;<code>telecom.system</code>&nbsp;element contains a fixed value of&nbsp;<code>phone</code>, and&nbsp;<code>telecom.value</code> element contains the telephone number</td>
        </tr>
        <!-- GPCM-SD-035 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-035</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Patient-1</code> resource with an NHS number, populated within the <code>nhsNumber</code> slice of the <code>identifier</code> element</td>
        </tr>
        <!-- GPCM-SD-036 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-036</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>CareConnect-Patient-1</code> resource with the official name of the patient, populated in the <code>name</code> element, and <code>name.use</code> must contain the value: <code>official</code></td>
        </tr>
        <!-- GPCM-SD-037 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-037</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Patient-1</code> resource with the date of birth for the patient, populated in the format: <code>YYYY-MM-DD</code> within the <code>birthDate</code> element</td>
        </tr>
        <!-- GPCM-SD-038 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-038</span></td>
            <td class="nhsd-t-body">
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a>
                |
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a>
            </td>
            <td class="nhsd-t-body">All values, populated in the FHIR <code>CareConnect-Patient-1</code> resource in the <code>name</code>, <code>birthDate</code>, and <code>nhsNumber</code> elements <b>MUST</b> match those specified in the MESH message configuration - e.g., MESH API: <code>Mex_To</code>, and MESH Client: <code>To_DTS</code></td>
        </tr>
        <!-- GPCM-SD-039 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-039</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>Extension-ITK-MessageHandling-2</code> resource with a value taken from the FHIR ValueSet <a target="_blank"  href="https://fhir.nhs.uk/STU3/CodeSystem/ITK-RecipientType-1" class="nhsd-a-link">ITK-RecipientType-1</a>, populated in the <code>RecipientType</code> element</td>
        </tr>
        <!-- GPCM-SD-040 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-040</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The&nbsp;payload <b>MUST</b> contain a FHIR <code>Extension-ITK-MessageHandling-2</code> resource with the value <code>true</code>, populated in the <code>BusAckRequired</code> element. This will request an ITK3 response with a response code in the range: <code>30001</code> to <code>30003</code></td>
        </tr>
        <!-- GPCM-SD-041 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-041</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>Extension-ITK-MessageHandling-2</code> resource with the value <code>true</code>, populated in the <code>InfAckRequired</code> element. This will request an ITK3 response with a response code in the range: <code>10001</code> to <code>20013</code></td>
        </tr>
        <!-- GPCM-SD-042 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-042</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>Extension-ITK-MessageHandling-2</code> resource with a unique identifier of the activity which has taken place at the sending organisation, populated within the <code>SenderReference</code> element</td>
        </tr>
        <!-- GPCM-SD-043 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-043</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>Extension-ITK-MessageHandling-2</code> resource, populated with a fixed value of <code>https://fhir.nhs.uk/STU3/MessageDefinition/ITK-GPConnectSendDocument-MessageDefinition-Instance-1</code> within the <code>MessageDefinition</code> element</td>
        </tr>
        <!-- GPCM-SD-045 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-045</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-ITK-Header-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-ITK-Header-Organization-1" class="nhsd-a-link">Profile: CareConnect-ITK-Header-Organization-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-ITK-Header-Organization-1</code> in the <code>ITK-Message-Bundle-1</code> profile</td>
        </tr>
        <!-- GPCM-SD-046 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-046</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>ITK-MessageHeader-2</code> with the MESH mailbox identifier of the sender, populated within the <code>source</code> element</td>
        </tr>
        <!-- GPCM-SD-047 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-047</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>ITK-MessageHeader-2</code>, populated with the fixed value of <code>ITK007C</code> from the <a target="_blank"  href="https://fhir.nhs.uk/STU3/CodeSystem/ITK-MessageEvent-2" class="nhsd-a-link">ITK-MessageEvent-2</a> code system, within the <code>event</code> element</td>
        </tr>
        <!-- GPCM-SD-048 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-048</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>ITK-MessageHeader-2</code> with the date and time of when the message was generated, populated within the <code>timestamp</code> element
            <br><br><div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Note</b>: A separate process (such as the MESH client) may be responsible for sending the message at a later date and time.</div></td>
        </tr>
        <!-- GPCM-SD-049 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-049</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST NOT</b> populate the <code>receiver</code> element in the FHIR <code>ITK-MessageHeader-2</code> resource, as MESH routing will be used to route the message to the registered GP practice using the patient NHS number, date of birth, and surname</td>
        </tr>
        <!-- GPCM-SD-059 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-059</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>From_DTS</code>&nbsp;<b>MUST</b>&nbsp;contain the MESH mailbox ID of the sender of the message (e.g., the originating practice)</td>
        </tr>
        <!-- GPCM-SD-060 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-060</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>To_DTS</code>&nbsp;<b>MUST</b>&nbsp;contain the NHS Number, DOB and Surname of the patient delimited by the underscore "<code>_</code>" character. This enables automatic routing of the message to the registered GP MESH mailbox</td>
        </tr>
        <!-- GPCM-SD-061 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-061</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>Subject</code>&nbsp;<b>MUST</b>&nbsp;contain&nbsp;To&nbsp;text in the following format:<br><code>[document-title] for [patient-name], NHS Number: [nhs-number], seen at [location-name], [ods-code], Version: [version-number]</code></td>
        </tr>
        <!-- GPCM-SD-062 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-062</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>Mex-From</code>&nbsp;<b>MUST</b>&nbsp;contain the MESH mailbox ID of the sender of the message (e.g., the originating GP practice)</td>
        </tr>
        <!-- GPCM-SD-063 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-063</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>Mex-To</code>&nbsp;<b>MUST</b>&nbsp;contain the NHS Number, DOB and Surname of the patient delimited by the underscore (<code>_</code>) character. This enables automatic routing of the message to the registered GP MESH mailbox</td>
        </tr>
        <!-- GPCM-SD-064 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-064</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body"><code>Mex-Subject</code>&nbsp;<b>MUST</b>&nbsp;contain&nbsp;To&nbsp;text in the following format:<br><code>[document-title] for [patient-name], NHS Number: [nhs-number], seen at [location-name], [ods-code], Version: [version-number]</code></td>
        </tr>
        <!-- GPCM-SD-098 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-098</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-handle-updates-to-documents?version=1.3.2-public-beta" title="Home/Build/How-to-handle-updates-to-documents" class="nhsd-a-link">How to handle updates to documents</a></td>
            <td class="nhsd-t-body">Version 1 is the original document, and updates to documents sent after the initial document <b>MUST</b>&nbsp;increment by 1</td>
        </tr>
        <!-- GPCM-SD-103 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-103</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2" class="nhsd-a-link">Profile: ITK-MessageHeader-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>ITK-MessageHeader-2</code> resource, populated with an <code>entry</code> element, containing an <code>ITK-Document-Bundle-1</code> profile</td>
        </tr>
        <!-- GPCM-SD-104 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-104</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Document-Bundle-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Document-Bundle-1" class="nhsd-a-link">Profile: ITK-Document-Bundle-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>ITK-Document-Bundle-1</code> resource, populated with an <code>entry</code> element containing a <code>CareConnect-Composition-1</code> profile</td>
        </tr>
        <!-- GPCM-SD-105 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-105</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>CareConnect-Composition-1</code> resource, with the <code>custodian</code> element being populated with a reference to a <code>CareConnect-Organization-1</code>, containing information pertaining to the sending organisation</td>
        </tr>
        <!-- GPCM-SD-106 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-106</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to a <code>CareConnect-Patient-1</code> within the <code>subject</code> element</td>
        </tr>
        <!-- GPCM-SD-107 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-107</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to the sending organisation using the <code>CareConnect-Organization-1</code> within the <code>author</code> element</td>
        </tr>
        <!-- GPCM-SD-108 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-108</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/Profiles.page.md?version=1.3.2-public-beta" title="Home/FHIR-Assets/Profiles.page.md" class="nhsd-a-link">Profiles</a></td>
            <td class="nhsd-t-body">All FHIR profiles within the payload <b>MUST</b> be populated with resource metadata, using the  <code>Meta</code> resource<br><br><div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Note</b>: Guidance around how to populate the <code>Meta</code> element for this capability has yet to be defined and our reference example only populates the <code>profile</code> element.</div></td>
        </tr>
        <!-- GPCM-SD-109 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-109</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>CareConnect-Composition-1</code> resource, populated with a <code>section</code> element for each attachment</td>
        </tr>
        <!-- GPCM-SD-110 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-110</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">Related to GPCM-SD-109, the payload <b>MUST</b> contain a FHIR <code>CareConnect-Composition-1</code> resource, populated with a <code>section.entry</code> with a reference to an <code>ITK-Attachment-Binary-1</code> resource for each attachment</td>
        </tr>
        <!-- GPCM-SD-111 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-111</span></td>
            <td class="nhsd-t-body"><a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Attachment-Binary-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Attachment-Binary-1" class="nhsd-a-link">Profile: ITK-Attachment-Binary-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a FHIR <code>ITK-Attachment-Binary-1</code> resource, populated with a base64 encoded attachment in the <code>content</code> element
        </td></tr>
        <!-- GPCM-SD-123 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-123</span></td>
            <td class="nhsd-t-body">
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a>
                |
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-handle-updates-to-documents?version=1.3.2-public-beta" title="Home/Build/How-to-handle-updates-to-documents" class="nhsd-a-link">How to handle updates to documents</a>
            </td>
            <td class="nhsd-t-body">In the event of a replacement document being sent, the payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with the UUID of the previous message in the <code>relatesTo.identifier</code> element</td>
        </tr>
        <!-- GPCM-SD-131 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-131</span></td>
            <td class="nhsd-t-body">
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a>
                |
                <a target="_blank"  href="/guide/gp-connect-send-document/Home/Build/How-to-handle-updates-to-documents?version=1.3.2-public-beta" title="Home/Build/How-to-handle-updates-to-documents" class="nhsd-a-link">How to handle updates to documents</a>
            </td>
            <td class="nhsd-t-body">In the event of a replacement document being sent, the payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with the fixed value of <code>replaces</code> in the <code>relatesTo.code</code> element</td>
        </tr>
        
    </tbody>
</table>

---