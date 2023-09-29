## {{page-title}}

The Supplier Conformance Assessment List (SCAL) is a technical document which details the requirements for the GP Connect Send Document capability, and others within the GP Connect product suite. It will be provided during the assurance stage of the onboarding; however, for convenience, a complete list of requirements fo this capability can be found in the table below, and downloaded as a pipe-separated "|" CSV.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: To open in Microsoft Excel go to the "Data" tab and select "From Text/CSV".
</div>

<!-- CSV download button -->
<button class="nhsd-a-button nhsd-a-button--outline download-csv" type="button">
  <span class="nhsd-a-button__label">Download CSV</span>
</button>

<br />

<!-- CSV download jQuery -->
<script>
$(function() {
  $("button.download-csv").on('click', function() {
    var data = "";
    var tableData = [];
    var rows = $("table tr");
    var epochTime = Math.floor(new Date().getTime()/1000.0);

    rows.each(function(index, row) {
      var rowData = [];
      $(row).find("th, td").each(function(index, column) {
        rowData.push(column.innerText);
      });
      tableData.push(rowData.join("|"));
    });
    data += tableData.join("\n");
    $(document.body).append('<a id="download-link" download="scal-gpc-send-doc-requirements-'+epochTime+'.csv" href=' + URL.createObjectURL(new Blob([data], {
      type: "text/csv"
    })) + '/>');

    $('#download-link')[0].click();
    $('#download-link').remove();
  });
});
</script>


<table data-no-sort data-responsive class="scal">
    <thead>
        <tr>
            <th>Identifier</th>
            <th>Use case</th>
            <th>Type</th>
            <th>Link</th>
            <th>Description</th>
            <th>Item</th>
            <th>Test cases</th>
            <th>Evidence required</th>
        </tr>
    </thead>
    <tbody>
        <!-- ALL REQUIREMENTS -->
        <!-- GPCM-C-1 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-C-1</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Design/Using-MESH}}</td>
            <td>MESH MUST be used as the message transport mechanism</td>
            <td>Using MESH to support GP Connect Messaging</td>
            <td>Pre-condition / covered by other tests</td>
            <td>Provide details of MESH and ITK3 compliance</td>
        </tr>
        <!-- GPCM-C-2 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-C-2</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Design/Using-ITK3}}</td>
            <td>All FHIR Messages MUST conform to the ITK3 Message Distribution Standard, v2.9.0</td>
            <td>Using MESH to support GP Connect Messaging</td>
            <td>Pre-condition / covered by other tests</td>
            <td>Provide details of MESH and ITK3 compliance</td>
        </tr>
        <!-- GPCM-SD-056 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-056</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH/How-to-configure-MESH.page.md}}</td>
            <td>All messages sent for this use-case MUST use MESH automated message routing to ensure that the message is correctly routed to the citizen's registered practice</td>
            <td>Using MESH to support GP Connect Messaging</td>
            <td>Pre-condition / covered by other tests</td>
            <td>Provide details of MESH and ITK3 compliance</td>
        </tr>
        <!-- GPCM-SD-28 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-028</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Organization-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Organization-1 resource describing the sender organisation (the origiN/Ating practice), ODS code, N/Ame , telephone number</td>
            <td>Requirements describing how the Organization resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-03</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-032 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-032</span></td>
            <td>All</td>
            <td>UI</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Practitioner-1}}</td>
            <td>The payload SHOULD (if known) contain a FHIR CareConnect-Practitioner-1 resource with the sending practitioner SDS User ID, populated in the sdsUserId slice of the identifier element, official N/Ame, telephone number</td>
            <td>Requirements describing how the Practitioner resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-03</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-035 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-035</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Patient-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Patient-1 resource with an NHS number, populated within the nhsNumber slice of the identifier element, official N/Ame, date of birth  populated in the format: YYYY-MM-DD within the birthDate element</td>
            <td>Requirements describing how the Patient resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-038 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-038</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>All values, populated in the FHIR CareConnect-Patient-1 resource in the N/Ame, birthDate, and nhsNumber elements MUST match those specified in the MESH message configuration - e.g., MESH API: Mex_To, and MESH Client: To_DTS</td>
            <td>Using MESH to support GP Connect Messaging</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-040 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-040</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-identify-which-documents-have-been-sent/Extension-ITK-MessageHandling-2.LocalExtension.page.md}}</td>
            <td>The payload MUST contain a FHIR Extension-ITK-MessageHandling-2 resource with the value true, populated in the BusAckRequired element. This will request an ITK3 response with a response code in the range: 30001 to 30003</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-041 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-041</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-identify-which-documents-have-been-sent/Extension-ITK-MessageHandling-2.LocalExtension.page.md}}</td>
            <td>The payload MUST contain a FHIR Extension-ITK-MessageHandling-2 resource with the value true, populated in the InfAckRequired element. This will request an ITK3 response with a response code in the range: 10001 to 20014</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-042  -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-042</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-identify-which-documents-have-been-sent/Extension-ITK-MessageHandling-2.LocalExtension.page.md}}</td>
            <td>The payload MUST contain a FHIR Extension-ITK-MessageHandling-2 resource with a unique identifier of the activity which has taken place at the sending organisation, populated within the SenderReference element</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-043 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-043</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-identify-which-documents-have-been-sent/Extension-ITK-MessageHandling-2.LocalExtension.page.md}}</td>
            <td>The payload MUST contain a FHIR Extension-ITK-MessageHandling-2 resource, populated with a fixed value of https://fhir.nhs.uk/STU3/MessageDefinition/ITK-GPConnectSendDocument-MessageDefinition-Instance-1 within the MessageDefinition element</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-044 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-044</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-identify-which-documents-have-been-sent/Extension-ITK-MessageHandling-2.LocalExtension.page.md}}</td>
            <td>The payload MUST contain a FHIR Extension-ITK-MessageHandling-2 resource populated with a fixed value of NONE within the LocalExtension element</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-045 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-045</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-ITK-Header-Organization-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-ITK-Header-Organization-1 in the ITK-Message-Bundle-1 profile</td>
            <td>Requirements describing how the CrareConnect-ITK-Header-Organization-1 profile within the ITK3 Document Bundle is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-046 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-046</span></td>
            <td>All</td>
            <td>UI (depending on solution)</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2}}</td>
            <td>The payload MUST contain a FHIR ITK-MessageHeader-2 with the MESH mailbox identifier of the sender, populated within the source element</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-047 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-047</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2}}</td>
            <td>The payload MUST contain a FHIR ITK-MessageHeader-2, populated with the fixed value of ITK007C from the ITK-MessageEvent-2 code system, within the event element</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-048 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-048</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2}}</td>
            <td>The payload MUST contain a FHIR ITK-MessageHeader-2 with the date and time of when the message was generated, populated within the timestamp element Note: A separate process (such as the MESH client) may be responsible for sending the message at a later date and time.</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-049 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-049</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2}}</td>
            <td>The payload SHOULD NOT populate the receiver element in the FHIR ITK-MessageHeader-2 resource, as MESH routing will be used to route the message to the registered GP practice using the patient NHS number, date of birth, and surN/Ame</td>
            <td>Requirements describing how the ITKMessageHandling extension within the ITK3 Message Header is populated for send document</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-057 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-057</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>The Use the following Meshdata ID : &lt;WorkflowId&gt;GPCONNECT_SEND_DOCUMENT&lt;/WorkflowId&gt;</td>
            <td>Requirement describing Workflow groups and Workflow ID</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-059 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-059</span></td>
            <td>All</td>
            <td>UI (depending on solution)</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>From_DTS MUST contain the MESH mailbox ID of the sender of the message (e.g., the origiN/Ating practice)</td>
            <td>Requirements describing the use of metadata if using the MESH client to send a message to the MESH server, the .CTL file</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-060 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-060</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>To_DTS MUST contain the NHS Number, DOB and SurN/Ame of the patient delimited by the underscore "_" character. This eN/Ables automatic routing of the message to the registered GP MESH mailbox</td>
            <td>Requirements describing the use of metadata if using the MESH client to send a message to the MESH server, the .CTL file</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-061 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-061</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>Subject MUST contain To text in the following format: [document-title] for [patient-N/Ame], NHS Number: [nhs-number], seen at [location-N/Ame], [ods-code], Version: [version-number]</td>
            <td>Requirements describing the use of metadata if using the MESH client to send a message to the MESH server, the .CTL file</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-062 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-062</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>Subject MUST contain To text in the following format: [document-title] for [patient-N/Ame], NHS Number: [nhs-number], seen at [location-N/Ame], [ods-code], Version: [version-number]</td>
            <td>Requirements describing the use of metadata items are defined in HTTP header fields if using the MESH API for the Send Message API call to send a message to the MESH server</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-063 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-063</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>Mex-To MUST contain the NHS Number, DOB and SurN/Ame of the patient delimited by the underscore "_" character. This eN/Ables automatic routing of the message to the registered GP MESH mailbox</td>
            <td>Requirements describing the use of metadata items are defined in HTTP header fields if using the MESH API for the Send Message API call to send a message to the MESH server</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-064 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-064</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>Mex-Subject MUST contain To text in the following format: [document-title] for [patient-N/Ame], NHS Number: [nhs-number], seen at [location-N/Ame], [ods-code], Version: [version-number]</td>
            <td>Requirements describing the use of metadata items are defined in HTTP header fields if using the MESH API for the Send Message API call to send a message to the MESH server</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-098 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-098</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-handle-updates-to-documents/How-to-handle-updates-to-documents.page.md}}</td>
            <td>Version 1 is the origiN/Al document, and updates to documents sent after the initial document MUST increment by 1</td>
            <td>Requirements describing sending replacement documents</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-08</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-103 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-103</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-MessageHeader-2}}</td>
            <td>The payload MUST contain a FHIR ITK-MessageHeader-2 resource, populated with an entry element, containing an ITK-Document-Bundle-1 profile</td>
            <td>Requirements describing the structure of the Send Document payload</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-104 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-104</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Document-Bundle-1}}</td>
            <td>The payload MUST contain a FHIR ITK-Document-Bundle-1 resource, populated with an entry element containing a CareConnect-Composition-1 profile</td>
            <td>Requirements describing how the Bundle resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-105 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-105</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Composition-1 resource, with the custodian element being populated with a reference to a CareConnect-Organization-1, containing information pertaining to the sending organisation</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-106 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-106</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with a reference to a CareConnect-Patient-1 within the subject element</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-107 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-107</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with a reference to the sending organisation using the CareConnect-Organization-1 within the author element</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-108 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-108</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>All FHIR profiles within the payload MUST be populated with resource metadata, using the Meta resource Note: Guidance around how to populate the Meta element for this capability has yet to be defined and our reference example only populates the profile element.</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-109 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-109</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with a section element for each attachment</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-110 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-110</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>Related to GPCM-SD-109, the payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with a section.entry with a reference to an ITK-Attachment-BiN/Ary-1 resource for each attachment</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-111 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-111</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--ITK-Attachment-BiN/Ary-1}}</td>
            <td>The payload MUST contain a FHIR ITK-Attachment-BiN/Ary-1 resource, populated with a base64 encoded attachment in the content element</td>
            <td>Requirements describing how biN/Ary documents are included in the payload</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-13</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-123 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-123</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-handle-updates-to-documents}}</td>
            <td>In the event of a replacement document being sent, the payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with the UUID of the previous message in the relatesTo.identifier element</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-08</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-128 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-128</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-handle-updates-to-documents}}</td>
            <td>The receiver of the new document SHOULD mark the origiN/Al and any replacement documents prior to the new document, as null and void and report a error to the sender using the ITK Response message and appropriate code see ITK3 response codesfor further information</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-08</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-129 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-129</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-handle-updates-to-documents}}</td>
            <td>Replacement documents MAY be done more than once and the new document always refers to the previous document, multiple replacements SHOULD be avoided due to complexity of maintaining the audit trail</td>
            <td>Requirements describing how the Composition resource is populated</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-08</span></td>
            <td>Screenshot(s) of the origiN/Ating patient activity and the resulting message and message response along with any appropriate commentary as to how the data matches between the screenshot and the messages / PDF or is hard coded.</td>
        </tr>
        <!-- GPCM-SD-115 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-115</span></td>
            <td>All</td>
            <td>General</td>
            <td>{{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-Composition-1}}</td>
            <td>The payload MUST contain a FHIR CareConnect-Composition-1 resource, populated with  SNOMED code: Current approved codes: 371531000 - Report of clinical encounter (record artifact), 149701000000109 -Remote health correspondence (record artifact)</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-083 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-083</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>{{pagelink:Home/Design/Design-overview/Typical-process-map.page.md}}</td>
            <td>Do NOT send the document to yourself if the patient registration is of type Regular (GMS/PMS)</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-06</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-084 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-084</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>A PDS lookup of the patient MUST be performed to determine the ODS code of the registered practice of the patient</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">N/A</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-086 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-086</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>The provider system MUST include all data entered by the clinician at the sender practice into the PDF Document in ssensible format and under appropriate clinical headings. This includes all free text, clinical/SNOMED CT codes, dm+d codes and any other data entered relating to the activity.</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-087 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-087</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>All data MUST be displayed in a format that matches how the consultation is displayed on screen or when printed</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-088 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-088</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td></td>
            <td>The provider system MUST include in the message all attachments relating to the activity</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-090 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-090</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>{{pagelink:Home/Examples/Generic-example}}</td>
            <td>The types of data that is expected to be common across all use cases (and should be contained within the PDF) are: document titleversion (if supported)page number x of ycitizen / patient informationsender informationthe intended recipient of the PDFdate and time of the activity / event logical headings representing the information being presented</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-091 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-091</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>{{pagelink:Home/Build/How-to-configure-MESH}}</td>
            <td>The version number MUST be displayed in the PDF and within the Subject of the MESH .CTL file</td>
            <td>N/A</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-01</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-094 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-094</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>Where a consultation report is not successfully received/maN/Aged by the message receiver, the sender system MUST inform an appropriate person/team</td>
            <td>Requirements describing error handling of receiver errors</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-04</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-095 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-095</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>Where either the infrastructure or business acknowledgements, or both, are not received for a consultation report, the sender system MUST inform an appropriate person/team</td>
            <td>Requirements describing error handling of receiver errors</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-05</span></td>
            <td>N/A</td>
        </tr>
        <!-- GPCM-SD-096 -->
        <tr>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-blue">GPCM-SD-096</span></td>
            <td>Consultation Summary</td>
            <td>General</td>
            <td>N/A</td>
            <td>The message sender system MUST send the consultation report within 3 hours after the consultation was created, or last updated</td>
            <td>Using Consultation Summary</td>
            <td><span class="nhsd-a-tag nhsd-a-tag--bg-light-grey">GPCM-SD-TST-07</span></td>
            <td>N/A</td>
        </tr>
    </tbody>
</table>