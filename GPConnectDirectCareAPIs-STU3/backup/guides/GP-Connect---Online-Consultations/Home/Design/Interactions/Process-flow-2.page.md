## {{page-title}}

Online Consultation Report - Process flow 2  (OC auto triage to GP practice)

{{ render: oc_process_2.png }}

<br />

### Steps

**1. Auto triage decision**

The OC system makes the decision to send the Online Consultation Report to the patient’s registered GP practice.

**2. OC payload generation**

The OC payload is created, containing a PDF of the Online Consultation Report and any FHIR coded resources applicable.

**3. Send OC to GP practice**

The OC payload is sent to the patient’s registered GP practice.

**4. Payload received by GP practice**

The OC payload is received by the GP practice. The payload is labelled as “For Action”.

**5. Save online consultation into patient record**

The provider system saves the Online Consultation Report into the patient’s electronic record at the GP practice.

**6. GP actions the OC**

The patient’s registered GP practice provides care for the patient.

---