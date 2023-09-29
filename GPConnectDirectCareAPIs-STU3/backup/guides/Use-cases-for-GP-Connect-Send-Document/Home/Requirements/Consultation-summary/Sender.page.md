## {{page-title}}

The following table outlines what the sender (or provider) needs to provide for the Consultation summary report use case of GP Connect Send Document.

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>Reference</th>
            <th data-no-sort>Guidance</th>
            <th data-no-sort>Description</th>
        </tr>
    </thead>
    <tbody>
        <!-- GPCM-SD-044 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-044</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Extensions/Extension--Extension-ITK-MessageHandling-2" class="nhsd-a-link">Extension: Extension-ITK-MessageHandling-2</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>Extension-ITK-MessageHandling-2</code> resource populated with a fixed value of <code>SendDocument-ConsultationReport</code> within the <code>LocalExtension</code> element</td>
        </tr>
        <!-- GPCM-SD-056 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-056</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/Design/Using-MESH?version=1.3.2-public-beta" title="Home/Design/Using-MESH" class="nhsd-a-link">Using MESH</a></td>
            <td class="nhsd-t-body">All messages sent for this use-case <b>MUST</b> use MESH automated message routing to ensure that the message is correctly routed to the citizen's registered practice</td>
        </tr>
        <!-- GPCM-SD-057 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-057</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/Build/How-to-configure-MESH?version=1.3.2-public-beta" title="Home/Build/How-to-configure-MESH" class="nhsd-a-link">How to configure MESH</a></td>
            <td class="nhsd-t-body">Each instance of a Send Consultation Report message <b>MUST</b> include the following MESH Workflow ID in the MESH message metadata: <code>GPFED_CONSULT_REPORT</code></td>
        </tr>
        <!-- GPCM-SD-076 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-076</span></td>
            <td class="nhsd-t-body">
                {{pagelink:Home/Requirements/Consultation-summary}}
            </td>
            <td class="nhsd-t-body">"Send Consultation Report" messages&nbsp;<b>MUST</b>&nbsp;be sent for 100% of practice encounters to ensure that the registered practice care record is an accurate statement of care delivered in a primary care setting</td>
        </tr>
        <!-- GPCM-SD-077 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-077</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The "Send Consultation Report" send facility&nbsp;<b>MUST</b>&nbsp;be implemented in such a way as to minimise administrative burden on the practice</td>
        </tr>
        <!-- GPCM-SD-083 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-083</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">If the patient registration type of the patient record at the appointment hosting practice is Regular (GMS/PMS), then the registered practice care record is already up-to-date, and a message&nbsp;<b>MUST NOT</b>&nbsp;be sent</td>
        </tr>
        <!-- GPCM-SD-084 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-084</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">A PDS lookup of the patient&nbsp;<b>MUST</b>&nbsp;be performed to determine the ODS code of the registered practice of the patient</td>
        </tr>
        <!-- GPCM-SD-086 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-086</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The provider system&nbsp;<b>MUST</b>&nbsp;include all data entered by the clinician at the sender practice into the "Clinical notes [notes]" section of the PDF document. This includes all free text, clinical/SNOMED CT codes, dm+d codes and any other data entered relating to the consultation</td>
        </tr>
        <!-- GPCM-SD-087 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-087</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">All data <b>MUST</b>&nbsp;be displayed in a format that matches how the consultation is displayed on screen or when printed</td>
        </tr>
        <!-- GPCM-SD-088 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-088</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The provider system&nbsp;<b>MUST</b>&nbsp;include in the message all attachments relating to the consultation</td>
        </tr>
        <!-- GPCM-SD-089 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-089</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Where the system does not have a concept of a consultation in its architecture, then the provider system&nbsp;<b>MUST</b> consider all data asserted about the patient for a specified date as part of the same consultation (this follows the same model as GP2GP)</td>
        </tr>
        <!-- GPCM-SD-090 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-090</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The layout and content of the PDF&nbsp;<b>MUST</b>&nbsp;conform to the template and logical field model outlined within the Consultation Summary report wireframe</td>
        </tr>
        <!-- GPCM-SD-091 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-091</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The version number&nbsp;MUST&nbsp;be displayed in the PDF in the relevant field and within the <code>Subject</code> of the MESH .CTL file</td>
        </tr>
        <!-- GPCM-SD-092 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-092</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">When displaying the Consultation Report in the practice workflow/task list, the message receiver <b>SHOULD</b> display the Subject contained in the MESH .CTL file:<br><code>Consultation report for [patient-name], NHS Number: [nhs-number], seen at [location-name], [ods-code], Version: [version-number]</code><br><br><div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Important</b>: These items <b>MUST NOT</b> be displayed if the consultation has been flagged as confidential.</div></td>
        </tr>
        <!-- GPCM-SD-094 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-094</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Where a consultation report is not successfully received/managed by the message receiver, the sender system&nbsp;<b>MUST</b>&nbsp;inform an appropriate person/team</td>
        </tr>
        <!-- GPCM-SD-095 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-095</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Where either the infrastructure or business acknowledgements, or both, are not received for a consultation report, the sender system&nbsp;<b>MUST</b>&nbsp;inform an appropriate person/team</td>
        </tr>
        <!-- GPCM-SD-096 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-096</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The message sender system&nbsp;<b>MUST</b>&nbsp;send the consultation report within 3 hours after the consultation was created, or last updated</td>
        </tr>
        <!-- GPCM-SD-102 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-102</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">If the patient has requested that the consultation is confidential then the following data items&nbsp;<b>MUST NOT</b>&nbsp;be sent <ins>in the PDF</ins>:<br><br><ul class="nhsd-t-list nhsd-t-list--bullet"><li>Clinical Notes</li><li>Clinician</li><li>Surgery Tel No.</li><li>Surgery Email</li><li>Place of consultation</li></ul></td>
        </tr>
        <!-- GPCM-SD-113 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-113</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource</td>
        </tr>
        <!-- GPCM-SD-114 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-114</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource populated with a fixed value of <code>final</code> within the <code>status</code> element<br><br><div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Note</b>: Updated documents may need to use the status of <code>amended</code>.</div></td>
        </tr>
        <!-- GPCM-SD-115 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-115</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a fixed SNOMED code with the value: <code>371531000</code> (Report of clinical encounter)</td>
        </tr>
        <!-- GPCM-SD-116 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-116</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with the date and time that the message was created within the <code>date</code> element</td>
        </tr>
        <!-- GPCM-SD-117 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-117</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with either the value <code>N</code> (normal) or <code>R</code> (restricted) within the <code>confidentiality</code> element</td>
        </tr>
        <!-- GPCM-SD-118 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-118</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a fixed value of <code>Consultation report</code> in the <code>title</code> element</td>
        </tr>
        <!-- GPCM-SD-119 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-119</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a summary of the consultation report within the <code>text</code> element (as outlined below)<br><br><code>Consultation report for [patient-name], NHS Number: [nhs-number], seen at [location-name]*, [ods-code]*, Version: [version-number]</code><br><br><div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">Items marked with <code>*</code> <b>MUST NOT</b> be sent if the consultation is confidential (for example, where <code>Composition.confidentiality</code> has the value <code>R</code>.</div></td>
        </tr>
        <!-- GPCM-SD-120 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-120</span></td>
            <td class="nhsd-t-body">
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a>
                |
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a>
            </td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to a <code>CareConnect-Patient-1</code> resource in the <code>subject</code> element</td>
        </tr>
        <!-- GPCM-SD-121 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-121</span></td>
            <td class="nhsd-t-body">
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a>
                |
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1" class="nhsd-a-link">Profile: CareConnect-Patient-1</a>
            </td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to a <code>CareConnect-Practitioner-1</code> resource in the <code>author</code> element</td>
        </tr>
        <!-- GPCM-SD-122 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-122</span></td>
            <td class="nhsd-t-body">
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a>
                |
                <a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1" class="nhsd-a-link">Profile: CareConnect-Organization-1</a>
            </td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to a <code>CareConnect-Organization-1</code> resource in the <code>custodian</code> element</td>
        </tr>
        <!-- GPCM-SD-124 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-124</span></td>
            <td class="nhsd-t-body"><a href="/guide/gp-connect-send-document/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1?version=1.3.2-public-beta" title="Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1" class="nhsd-a-link">Profile: CareConnect-Composition-1</a></td>
            <td class="nhsd-t-body">The payload <b>MUST</b> contain a&nbsp;FHIR <code>CareConnect-Composition-1</code> resource, populated with a reference to the consultation report PDF in the <code>section.entry</code> element</td>
        </tr>
        <!-- GPCM-SD-128 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-128</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">The sender of the new document&nbsp;<b>SHOULD</b>&nbsp;mark the original and any replacement documents prior to the new document, as null and void and report a error to the sender using the ITK Response message and appropriate code see&nbsp;ITK3 response codesfor further information</td>
        </tr>
        <!-- GPCM-SD-129 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-129</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Replacement documents&nbsp;MAY&nbsp;be done more than once and the new document always refers to the previous document, multiple replacements&nbsp;<b>SHOULD</b>&nbsp;be avoided due to complexity of maintaining the audit trail</td>
        </tr>
        <!-- GPCM-SD-130 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-130</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">Replacement documents&nbsp;SHOULD&nbsp;be sent within 24 hours of the original document</td>
        </tr>
        <!-- GPCM-SD-133 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-133</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">If the local system supports setting individual data items as confidential, then each item flagged as confidential&nbsp;<b>MUST</b>&nbsp;contain the warning text: <code>Confidential item</code>&nbsp;when sent in the consultation report</td>
        </tr>
        <!-- GPCM-SD-134 -->
        <tr>
            <td class="nhsd-t-body"><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-134</span></td>
            <td class="nhsd-t-body">{{pagelink:Home/Requirements/Consultation-summary}}</td>
            <td class="nhsd-t-body">If <ins>multiple data items</ins> are flagged as confidential, the warning text:&nbsp;<code>Confidential item</code>&nbsp;MUST&nbsp;be repeated for each item</td>
        </tr>
    </tbody>
</table>

---