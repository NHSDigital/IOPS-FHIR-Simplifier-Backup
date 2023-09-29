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
        <!-- Send Online Consultation Report to GP practice -->
        <tr>
            <td>
                Send Online Consultation Report to GP practice
            </td>
            <td>
                As member of staff at a GP practice... I want the Online Consultation Report to be sent directly to the GP clinical system... so that I don't have to manually move or copy the Online Consultation Report.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must send an Online Consultation Report to the patient's registered GP practice
                        <ul>
                        <li>
                            the sender system must flag the Online Consultation Report as <b>FOR ACTION</b> if the GP practice is identified as the primary recipient
                        </li>
                        <li>
                            the send system must flag as <b>FOR INFORMATION</b> and send a copy message if an alternative care provider is identified as the primary recipient
                        </li>
                        </ul>
                    </li>
                    <li>
                        where the sender system supports an alternative method for communicating the online consultation information back to the patient's registered GP practice, this method may be used in the place of GP Connect Messaging
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
        <!-- Send Online Consultation Report directly to an alternative care provider -->
        <tr>
            <td>
                Send Online Consultation Report directly to an alternative care provider
            </td>
            <td>
                As member of staff at a GP practice... I want the Online Consultation Report to be sent directly to an alternative care provider selected by the patient... so that the care provider can offer a service to the patient.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must send an Online Consultation Report to the patient's chosen alternative care provider (currently only community pharmacies)
                        <ul>
                        <li>
                            the sender system must flag the Online Consultation Report as <b>FOR ACTION</b>
                        </li>
                        <li>
                            a copy message must be sent to the patient's registered GP practice flagged as <b>FOR INFORMATION</b>
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
        <!-- Routing the report to the correct care provider -->
        <tr>
            <td>
                Routing the report to the correct care provider
            </td>
            <td>
                As member of staff at a GP practice... I want the Online Consultation Report to be routed to the patient's registered practice or chosen alternative care provider... so that the message is sent to the correct destination(s).
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>all sending systems will use the MESH API Address Lookup function to request/receive the destination system's MESH mailbox IDs</li>
                    <li>
                        when sending the Online Consultation Report
                        <ul>
                        <li>
                            the sender system should use the MESH API Send Message function to send the message
                        </li>
                        <li>
                           the sender system can use the MESH client to send the message
                        </li>
                        </ul>
                    </li>
                    <li>if the sender system is only ever sending the Online Consultation Report to the patient's registered GP practice, then MESH automated message routing function can be used</li>
                    <li>the sender system must use the allocated MESH Workflow ID associated solely with this capability</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>when sending to a GP practice, if the message received is for a patient who is not registered at the GP practice, the receiving system must send a response back to the sending system</li>
                    <li>the receiving system must use the allocated MESH Workflow ID associated solely with the GP Connect Send Document capability</li>
                </ol>
            </td>
        </tr>
        <!-- SNOMED coding applicable content -->
        <tr>
            <td>
                SNOMED coding applicable content
            </td>
            <td>
                As clinician at a GP practice... I want the Online Consultation Reports to be SNOMED coded where applicable... so that I don't have to manually code clinically relevant information into the patient's record.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>
                        the sender system must SNOMED code all clinically relevant information in an Online Consultation Report sent to the patient's practice
                        <ul>
                        <li>
                            the sender system must use a SNOMED code for a defined collection of Clinical indicators
                        </li>
                        </ul>
                    </li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>the receiving system should have the ability to consume the additional structured data contained in the extended payload</li>
                    <li>the receiving system should allow review and confirm before the SNOMED coded information is saved to the patient's record</li>
                </ol>
            </td>
        </tr>
        <!-- Payload identification -->
        <tr>
            <td>
                Payload identification
            </td>
            <td>
                As clinician at a GP practice... I want the Online Consultation Report, and its information, to be clearly identifiable... so that the provenance of the information is clear.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>the sending system must contain a SNOMED coded OC identifier</li>
                    <li>the sender system must identify items in the payload as patient entered information, where applicable</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>the receiving system must display the OC identifier sent in the payload by the sender system</li>
                    <li>the receiving system should be able to display items flagged as patient entered information</li>
                </ol>
            </td>
        </tr>
        <!-- Non-coded payload content -->
        <tr>
            <td>
                Non-coded payload content
            </td>
            <td>
                As clinician at a GP practice... I want the ability to save all the non-coded information in the Online Consultation Report to the patient record... so that I can add all clinically relevant information to the patient record.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>the sender system must include a PDF of the Online Consultation Report in the payload</li>
                    <li>the sender system must be able to contain one or more images or supported attachment types</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>the receiving system must be able to save the PDF in the Online Consultation Report to the patient record</li>
                    <li>the receiving system must be able to save one or more attachments in the patient record</li>
                    <li>where images are contained in the payload, the receiving system must record them in the audit trail</li>
                </ol>
            </td>
        </tr>
        <!-- Triage -->
        <tr>
            <td>
                Triage
            </td>
            <td>
                As clinician at a GP practice... I want the OC system to be able to triage the information in the Online Consultation AND send the OC payload either to the GP or an alternative care provider, dependent on the triage outcome... so that the patient receives the correct level of care.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>the sender system should be able to auto triage based on the patient entered symptom information in an Online Consultation Report, AND make a routing decision (GP or alternative care provider)</li>
                    <li>the sender system should be able to send the OC payload to a GP or alternative care provider, if there is manual triage functionality available within the OC system</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                NA
            </td>
        </tr>
        <!-- Patient preference of alternative care provider -->
        <tr>
            <td>
                Patient preference of alternative care provider
            </td>
            <td>
                As clinician at a GP practice... I want a patient to be able to give a preference of an alternative care provider (for example, community pharmacy) in their locality whenever they complete an Online Consultation Report... so that the Online Consultation Report can be directed to a preferred alternative care provider.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>the sender system must offer the patient a list of local alternative care providers (for example, Community Pharmacies) AND record the patient's entered preference</li>
                    <li>the sender system must include the patient's response for the alternative care provider preference in the Online Consultation payload</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                NA
            </td>
        </tr>
        <!-- Send Online Consultation Report from an alternative care provider back to a GP -->
        <tr>
            <td>
                Send Online Consultation Report from an alternative care provider back to a GP
            </td>
            <td>
                As a member of staff at an alternative care provider... I want to be able to send the Online Consultation Report back to the GP system... so that escalated Online Consultation Reports can be returned to the patient's registered GP practice for further action.
            </td>
            <td>
                <b>Sending system</b>
                <br />
                <ol>
                    <li>the sender (alternative care provider) system must be able to send the OC payload back to a GP system if required</li>
                </ol>
                <br />
                <b>Receiving system</b>
                <br />
                <ol>
                    <li>the receiving system (GP system) must be able to receive an Online Consultation Report sent from an alternative care provider if escalated</li>
                </ol>
            </td>
        </tr>
    </tbody>
</table>