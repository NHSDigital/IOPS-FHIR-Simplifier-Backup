## {{page-title}}

Online Consultation Report - Process flow 1  (OC auto triage to alternative care provider, for example community pharmacy (CP))

{{ render: oc_process_1.png }}

<br />

### Steps

**1. Auto triage decision**

The OC system makes the decision to send the Online Consultation Report to a community pharmacy.

**2. OC payload generation**

The OC payload is created, containing a PDF of the Online Consultation Report and any FHIR coded resources applicable.

**3. Send copy to GP practice**

A copy of the OC payload is sent to the patient’s registered GP practice.

**4. Copy received by GP practice**

The copy OC payload is received by the GP practice. The payload is labelled as “For Information”.

**5. Save online consultation into patient record**

The provider system saves the Online Consultation Report into the patient’s electronic record at the GP practice.

**6. Send OC payload to CP**

The OC payload is sent to the community pharmacy requested by the patient.

**7. Payload received by CP**

The OC payload is received by the community pharmacy. The payload is labelled as “For Action”.

**8. DECISION A - CP accepts the OC**

The community pharmacy accepts the OC and saves the Online Consultation Report in the CP system.

**9. CP actions the OC**

The community pharmacy provides care for the patient.

**10. DECISION B - CP escalates the OC**

The community pharmacy does not accept the OC and escalates the OC back to the patient’s registered GP practice.

**10. Send OC payload to GP**

The OC payload is sent to the patient’s registered GP practice.

**11. Payload received by GP**

The OC payload is received by the patient’s registered GP practice. The payload is labelled as “For Action”.

**12. GP actions the OC**

The patient’s registered GP practice accepts the OC and provides care for the patient.

---