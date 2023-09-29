## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: The preferred method for sending Online Consultation Reports is the MESH API, this is because the MESH API is more easily integrated into sending systems, and the MESH API Address Lookup function needs to used to identify MESH mailbox IDs for community pharmacies.

The MESH client can be used to send the message, but the MESH API Address Lookup is still required if sending to a community pharmacy.

The Message routing to registered practice can be used if only ever sending to the patient’s registered GP practice.
</div>

Please refer to Integration to MESH for an introduction to the use of MESH for GP Connect Messaging use cases.


## MESH API Address Lookup

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-159">GPCM-SD-OC-159</td>
      <td>all messages sent through this use case to non-GP practice care providers <strong>MUST</strong> use the MESH API Address Lookup function to lookup the MESH mailbox ID of the receiving care provider. <br><br>Details of how to use Address Lookup can be found on the <a href="https://digital.nhs.uk/developer/api-catalogue/message-exchange-for-social-care-and-health-api#api-Endpoints-meshAddressLookup-0">MESH API page</a></td>
    </tr>
  </tbody></table>


---

## Workflow groups and Workflow ID

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-160">GPCM-SD-OC-160</td>
      <td>each instance of a Online Consultation Report message <strong>MUST</strong> include the following MESH Workflow ID in the MESH message metadata: <code>GPFED_CONSULT_REPORT</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-161">GPCM-SD-OC-161</td>
      <td>each instance of an acknowledgement message generated as a result of receipt of a Online Consultation Report message <strong>MUST</strong> include the following Workflow ID in the MESH message metadata: <code>GPFED_CONSULT_REPORT_ACK</code></td>
    </tr>
  </tbody></table>

---

## MESH API configuration

When using the MESH API the Send Message API call will be used by a sending organisation API client to send a message to the MESH server. MESH metadata items are defined in HTTP header fields as described below:

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-162">GPCM-SD-OC-162</td>
      <td><code>Mex-From</code> <strong>MUST</strong> contain the MESH mailbox ID of the sender of the message – in this case the originating organisation</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-163">GPCM-SD-OC-163</td>
      <td><code>Mex-To</code> <strong>MUST</strong> contain the MESH mailbox ID of the receiver of the message – in this case either the mailbox ID for the patient's registered GP practice, or chosen community pharmacy</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-164">GPCM-SD-OC-164</td>
      <td><code>Mex-Subject</code> <strong>MUST</strong> contain <code>To</code> text in the following format:<br><br><code>Online consultation report for {Patient Name}, NHS Number {NHS Number}, ODS Code {ODS Code}</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-175">GPCM-SD-OC-175</td>
      <td><code>Mex-Localid</code> <strong>MUST</strong> contain the ODS code of the sending organisation</td>
    </tr>
  </tbody></table>

---

## MESH client configuration

When using the MESH client to send a message to the MESH server, the `.CTL` file will contain the following metadata about the message:

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-165">GPCM-SD-OC-165</td>
      <td><code>From_DTS</code> <strong>MUST</strong> contain the MESH mailbox ID of the sender of the message – in this case the originating organisation</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-166">GPCM-SD-OC-166</td>
      <td><code>To_DTS</code> <strong>MUST</strong> contain the NHS Number, DOB and Surname of the patient delimited by the underscore character ‘_'. This enables automatic routing of the message to the registered GP MESH mailbox</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-167">GPCM-SD-OC-167</td>
      <td><code>Subject</code> <strong>MUST</strong> contain <code>To</code> text in the following format:<br><br><code>Online consultation report for {Patient Name}, NHS Number {NHS Number}, ODS Code {ODS Code}</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-174">GPCM-SD-OC-174</td>
      <td><code>LocalID</code> <strong>MUST</strong> contain the ODS code of the sending organisation</td>
    </tr>
  </tbody></table>
