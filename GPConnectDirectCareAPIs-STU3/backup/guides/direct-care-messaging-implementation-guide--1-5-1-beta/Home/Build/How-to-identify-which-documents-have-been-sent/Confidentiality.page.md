## {{page-title}}

<strong>Confidential items contain information the patient has asked not to be shared.</strong>
<br><br>
Under previous versions of the spec, confidential items would be redacted but a notification still sent, with <code>Composition.confidentiality</code> set to value <strong>R</strong> (Restricted). 
<br>
Ideally the patient's intent in relation to why the document is restricted should be captured in consultation notes.
<br>
Despite all this, in some scenarios ingestion of the Send Document message could still result in accidental disclosure of confidential information via the context and SNOMED coding. 
Therefore the following guidance has been included to mitigate the risk of disclosure.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>For Senders:</b><br>
    Confidential items should NOT be sent via Send Document. 
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>For Receivers:</b><br>
    Although confidential information should not be sent, it is still possible a receiving system could receive such a transmission. 
    <br>
    If the value of <code>Composition.confidentiality</code> is <strong>R</strong>, the document should not be autofiled.
</div>

---