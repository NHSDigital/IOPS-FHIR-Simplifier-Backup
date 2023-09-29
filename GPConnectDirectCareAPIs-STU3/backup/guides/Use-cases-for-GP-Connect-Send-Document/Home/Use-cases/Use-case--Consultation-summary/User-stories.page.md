## {{page-title}}

<table data-responsive>
    <thead>
        <tr>
            <th data-no-sort>User story</th>
            <th data-no-sort>Description</th>
            <th data-no-sort>Acceptance criteria</th>
        </tr>
    </thead>
    <tbody>
        <!-- Send report for correct patient -->
        <tr>
            <td>
                Send report for correct patient
            </td>
            <td>
                <b>As a clinician</b> at a practice,
                <br />
                <b>I want</b> to send a document containing a patient's consultation notes when the patient is registered at another practice,
                <br />
                <b>so that</b> the patient's medical record is kept up to date with a full treatment history.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must send a consultation report when the patient in question is registered at another GP practice
                        <ul>
                        <li>
                            the sender system must follow the method stated in the specification to determine whether a patient is registered at another GP practice.
                        </li>
                        </ul>
                    </li>
                    <li>
                        where the sender system supports an alternative method for communicating the consultation information back to the patient's registered GP practice, this method may be used in the place of GP Connect Messaging (based on local agreement)
                        <ul>
                            <li>
                                where an alternative method is used, the GP Connect Messaging requirements do not apply
                            </li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
            </td>
        </tr>
        <!-- Routing the report to the correct practice -->
        <tr>
            <td>
                Routing the report to the correct practice
            </td>
            <td>
                <b>As a clinician</b> at a practice,
                <br />
                <b>I want</b> the consultation report to be routed to the patient's registered practice,
                <br />
                <b>so that</b> the patient's medical record is kept up to date with a full history.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        all consultation reports will use MESH automated message routing in order to ensure that the message is routed correctly to the registered practice of the patient. It is not necessary for the sender system to specify a destination MESH mailbox ID
                    </li>
                    <li>
                        the sender system must specify the patient's NHS Number, Surname and Date of Birth in the message header and use these to populate the Mex-To HTTP header in the MESH endpoint lookup service
                    </li>
                    <li>
                        the sender system must use the allocated MESH Workflow ID associated solely with the GP Connect Send Document capability
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>
                        where the message received is for a patient who is not registered at the GP practice, the receiver system must send a response back to the sending GP practice
                    </li>
                    <li>
                        the receiver system must use the allocated MESH Workflow ID associated solely with the GP Connect Send Document capability
                    </li>
                </ol>
            </td>
        </tr>
        <!-- Generate PDF and associated metadata -->
        <tr>
            <td>
                Generate PDF and associated metadata
            </td>
            <td>
                <b>As a clinician</b> at a practice,
                <br />
                <b>I want</b> a full and complete record of the consultation to be sent and the data entered into the local record to exactly match what is received at the patient's registered GP practice,
                <br />
                <b>so that</b> the patient's medical record is kept up to date with a full history.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must include all data entered by the clinician at the originating practice into the 'Clinical notes <code>[notes]</code>' section of the PDF document; this includes all free text, clinical / SNOMED CT codes, dm+d codes and any other data entered relating to the consultation
                    </li>
                    <li>
                        the sender system must include in the message all attachments relating to the consultation
                    </li>
                    <li>
                        where the system does not have a concept of a consultation in its architecture, then the sender system will consider all data asserted about the patient for a specified date as part of the same consultation (this follows the same model as GP2GP)
                    </li>
                    <li>
                        the layout and content of the PDF must conform to the template and logical field model contained within this requirements catalogue
                    </li>
                    <li>
                        the version number must be displayed in the PDF in the relevant field and within the Subject of the MESH <code>.CTL</code file
                        <ul>
                            <li>
                                version 1 is the original report with each subsequent report that relates to the same consultation incrementing by 1
                            </li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
            </td>
        </tr>
        <!-- Receiving the consultation report -->
        <tr>
            <td>
                Receiving the consultation report
            </td>
            <td>
                <b>As member of staff</b> at a practice,
                <br />
                <b>I want</b> a full and complete report of our patient's consultation when they are receiving care at another practice,
                <br />
                <b>so that</b> the patient's medical record is kept up to date with a full history.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                Not applicable
                <br />
                <br />
                <b>Receiving system</b>
                <br />
               <ol>
                    <li>
                        the receiver system must route consultation reports into the practice workflow and display it as a task
                    </li>
                    <li>
                        the sender system must include in the message all attachments relating to the consultation
                    </li>
                    <li>
                        when displaying the consultation report in the practice workflow/task list, the receiver system must display the Subject from the MESH .CTL file:
                        <br />
                        <code>Consultation report for [patient-name], NHS Number: [nhs-number], seen at [practice-name], [ods-code], Version: [version-number]</code>
                    </li>
                    <li>
                        the receiver system must display all data in the same form as supplied by the sender system
                    </li>
                    <li>
                        the receiver system must make any attachments included with the consultation report available to the end user
                    </li>
                </ol>
            </td>
        </tr>
        <!-- Alert staff of errors -->
        <tr>
            <td>
                Alert staff of errors
            </td>
            <td>
                <b>As a member of the admin staff</b> at the originating practice,
                <br />
                <b>I want</b> to be informed when a consultation report is not sent successfully,
                <br />
                <b>so that</b> I can take appropriate measures to get the data to the patient's registered practice.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        where a consultation report is not successfully received/managed by the receiver system, the sender system must inform an appropriate person
                    </li>
                    <li>
                        where either the infrastructure or business acknowledgements, or both, are not received for a consultation report, the sender system must inform an appropriate person
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>
                        the receiver system must return an error code when the processing of the message is unsuccessful
                    </li>
                </ol>
            </td>
        </tr>
        <!-- Report version number -->
        <tr>
            <td>
                Report version number
            </td>
            <td>
                <b>As a clinician</b> at the receiving GP practice,
                <br />
                <b>I want</b> to know what version / iteration of the PDF document has been received,
                <br />
                <b>so that</b> I am informed of updates to previous consultation reports and to understand that there are earlier versions that can be discarded / updated.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must identify if there are multiple consultation report documents sent for a specific consultation and patient. The version number must be displayed within the relevant section of the PDF document and in the subject of the MESH .CTL file in the format:<br /><br /><code>Consultation report for [patient-name], NHS Number: [nhs-number], seen at [practice-code], [ods-code], Version: [version-number]</code>
                        <br />
                        <ul>
                            <li>version 1 is the original report with each subsequent report that relates to the same consultation incrementing by 1</li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>
                        when displaying the consultation report in the practice workflow / task list, the receiving system must display the Subject of the MESH .CTL file in the format:<br /><br /><code>Consultation report for [patient-name], NHS Number: [nhs-number], seen at [practice-code], [ods-ode], Version: [version-number]</code>
                    </li>
                </ol>
            </td>
        </tr>
        <!-- Send consultation report -->
        <tr>
            <td>
                Send consultation report
            </td>
            <td>
                <b>As the authoring clinician</b>,
                <br />
                <b>I want</b> the system to automate the process of generating and sending the consultation report to the registered practice,
                <br />
                <b>so that</b> the consultation report document is sent for 100% of consultations.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must send the consultation report a configurable time period after the consultation was created or last updated
                        <ul>
                            <li>
                                where a consultation is updated within the configurable time period of the last update, the time delay to sending the consultation report will be from the later update
                            </li>
                            <li>
                                where a consultation is updated after the configurable time period (and therefore the consultation report has already been sent) a new consultation report will be sent (after the configurable time period)
                            </li>
                            <li>
                                each GP practice must be able to set its own a configurable time period
                            </li>
                            <li>
                                where a GP practice has not set its own configurable time period the value will default to three hours
                            </li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
            </td>
        </tr>
        <!-- Patient confidentiality -->
        <tr>
            <td>
                Patient confidentiality
            </td>
            <td>
                <b>As a patient</b>,
                <br />
                <b>I want</b> to be able to request that the details of the consultation are kept private,
                <br />
                <b>so that</b> the data is not shared with someone I do not want to see it.
            </td>
            <td>
                <div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This is the equivalent of a clinician setting a consultation as confidential and restricting the members of the GP practice who can view the details
</div>            
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the clinician must be able to set a consultation as confidential (or the clinical system's equivalent)
                    </li>
                    <li>
                        the consultation record held at the GP practice is recorded as confidential (or equivalent) and its access restricted to the clinician who made the record
                    </li>
                    <li>
                        where a consultation has been marked as confidential, the message is still sent to the patient's GP practice stating the consultation took place; it will contain no information on what took place in the consultation
                        <ul>
                            <li>
                                information on the patient and when the consultation took place are still included
                            </li>
                            <li>
                                information on the clinician and where the consultation took place are not included
                            </li>
                            <li>
                                the clinical notes are replaced by the text 'The details of this consultation have been set as confidential'
                            </li>
                        </ul>
                    </li>
                    <li>
                        confidentially is applied on a per consultation basis. A request for confidentiality for one consultation will have no impact on the messages sent for any other consultation
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
                <br />
            </td>
        </tr>
        <!-- Local record retention -->
        <tr>
            <td>
                Local record retention
            </td>
            <td>
                <b>As a clinician</b>,
                <br />
                <b>I want</b> the original record of the consultation recorded on the local system,
                <br />
                <b>so that</b> it is available to support ongoing care of the patient and to review if there are any legal or clinical challenges about the care given.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must retain a copy of every consultation report that is sent
                    </li>
                    <li>
                        for every consultation where a consultation report is produced, the sender system must retain a copy of the consultation in the format is was originally recorded
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
                <br />
            </td>
        </tr>
        <!-- Data-sharing -->
        <tr>
            <td>
                Data-sharing
            </td>
            <td>
                <b>As a clinician (and the data controller)</b> sending a point-to-point targeted communication,
                <br />
                <b>I want</b> sending and receiving the consultation report to not be restricted by any data sharing controls,
                <br />
                <b>so that</b> the consultation report document is sent and received for 100% of consultations.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        data sharing controls must not prevent the consultation message being sent
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>
                        data sharing controls must not prevent the consultation message being received and made available to the GP practice
                    </li>
                </ol>
            </td>
        </tr>
        <!-- Deleted consultation -->
        <tr>
            <td>
                Deleted consultation
            </td>
            <td>
                <b>As a clinician</b> at the originating practice,
                <br />
                <b>I want</b> the patient's registered GP practice to be informed if I delete a consultation,
                <br />
                <b>so that</b> the patient's medical record is kept up-to-date.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                       when a user deletes a consultation where a consultation report has been sent, the sending system must give a warning message to the user
                        <ul>
                            <li>
                                the warning message must include the patient name and NHS number, the consultation date and the GP practice the consultation report has been sent to(the patient's registered GP practice)
                            </li>
                        </ul>
                    </li>
                    <li>
                       where a consultation is deleted it is the responsibility of the GP practice that recorded the consultation to inform the registered GP practice
                        <ul>
                            <li>
                                there is no requirement for the sending system to send an automated message to inform the registered GP practice about the deletion
                            </li>
                            <li>
                                the sending system should assist the GP practice in managing and tracking the process of informing other organisations
                            </li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                Not applicable
                <br />
            </td>
        </tr>
    </tbody>
</table>