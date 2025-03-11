## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: Documents where the patient has not consented to share with their GP, or wish to remain confidential <strong>should not handled according to the guidance below</strong>. This differs from the previous versions of Send Document.

### What changed?

Previously, "Send Document" allowed the sharing of confidential or "restricted" documents from consultations, even if they took place at a different GP practice. The system would hide the content of these documents.

Now, with the updated "Send Document v2x", you can no longer share confidential consultations. If a patient requests their consultation to remain private, it cannot be shared using this system.

<b>For Senders:</b>

* Confidential items <strong>should NOT be sent</strong> via Send Document.
* If the patient has asked for information about this encounter not to be shared, no message should be sent

<b>For Receivers:</b>

* Although confidential information should not be sent, it is still possible a receiving system could receive such a transmission.
* If the value of Composition.confidentiality is <strong>R</strong>, the document <strong>should be rejected</strong> by the receiving system. 
* Upon rejection, an ITK response code 20009 (Payload content validation failure) should be sent back to the sending system.

</div>

### Why the change?

This update aligns "GP Connect: Update Record" with how patient records are handled in other systems.

- **More detailed information**: "Send Document v2x" now shares more specific information about the service a patient used. This helps the recipient understand the context of the consultation.
- **Patient privacy**: Similar to how confidential consultations with a pharmacist are not shared with a GP without patient consent, "Send Document v2x" now respects patient confidentiality in the same way.

Essentially, the update prioritises patient privacy and ensures consistency across different healthcare systems.


<h5><ins>Example</ins></h5>

```xml
<!-- Normal -->
<confidentiality value="N" />

<!-- Restricted -->
<confidentiality value="R" />
```

---