## {{page-title}}

Another issue with `record transfer messaging` is its focuses on the EHR record. Before modern technology (1990's onwards), interactions between practitioners especially in different care settings was via letters. 
From 1990's we started to see technical splitting this into:

- Systems being used to record EHR data.
- Messaging being used to support the workflow and care coordination between providers. This was mostly around Health Administration and pathology (as HL7 v2).

`record transfer messaging` has been and continues to be developed. The clinical process shown in the diagram below tends to be a high level view. 

{{render:diagrams-RecordFocusedWorkflowBPMN}}

<div markdown="span" class="alert alert-warning" role="information"><p>Robert Brown is a clinically obese patient who also has long term COVID. He has had breathing difficulties and due to an abnormal SPO2 readings he was admitted to a Leeds Teaching Trust hospital following consultation with NHS 111.</p>

 <b>input</b>

<p>The Yorkshire Ambulance service would handover an Emergency Care Summary to Leeds Teaching Trust. This would probably follow NHS England's UEC/BARS specifications and so be in HL7 v3 or HL7 Document/Message formats. It may also be manually handed over in paper format.</p>

<b>activity/encounter</b>

<p>The emergency department at Leeds Teaching Trust probably use a combination of EPR records, Leeds Care Record (HIE) and/or YHCR (HIE) to view Robert's medical history. 

Care provided is documented in Leeds Teaching Trusts EPR system.</p>

<b>output</b>

<p>Leeds Teaching Trust produces an Discharge document which is sent to the Roberts GP. The format of this document is based on NHS England's Transfer of Care specifications (HL7 FHIR Document+Message+MESH).</p>

</div>


This diagram uses [Business Process Model and Notation](https://www.bpmn.org/) to describe the workflow. BPMN diagrams often show a sequence of interconnected processes. In this diagram we have chosen to represent a high-level process which takes in

- input which is information required to perform the task. In record transfer this is usually a large EHR record extract. For example, a referral letter.
- output which is the information output from the task and is normally used to pass information to the next task. For example, a discharge or outpatient letter.

A practitioner performing this task will also use other resources to help perform the task. For example, a Shared Care Record (SCR). While they are performing the task, they will record what has taken places in local EHR records.

Potential uses of standards are shown alongside these. Note this is showing competing standards on both `input` and `output`. PRSB is another standard which applies here.

This view of process is high level, focused around both transfer of care and stays/episodes. In practice, health and care is a collection of many tasks which tend to revolve around individual encounters. For example:

 <div markdown="span" class="alert alert-warning" role="information"><p>Marge is an elderly citizen. While at her granddaughter’s wedding in Wakefield she started to feel unwell. One of the
  guests, Dawn a palliative nurse, offered to look at her.</p>

 <b>input</b>

<p>Dawn asked for confirmation on what had just happened. Annabelle, Marge's daughter and also a Social Worker/Carer, briefed Dawn on her mother's health and that she may have Cancer.</p>

<b>activity/encounter</b>

<p>Dawn took a series of measurements including blood pressure, pulse, and blood sugars. Dawn evaluated the measurements informing Dawn and Annabelle the readings were ok.</p>

<b>output</b>

<p>Dawn recommended Marge book an appointment/follow up with her GP.</p>

</div>

If Dawn had been attending Marge in her NHS role, she would have would retrieve Marge's summary from her NHS Trusts EPR system and/or Yorkshire and Humberside Care Record (YHCR), a Health Information Exchange (HIE) (**input**). The measurements and evaluation would have been recorded in the EHR (**activity**). A HL7 v2 ADT_A04 event message would have automatically been generated to inform other practitioners and systems of the event (**output**). Dawns NHS Trust is Mid Yorkshire and so the encounter notification messages are sent to Marge's GP Practice using NHS England HL7 v2 ADT Messaging standard which the trusts EPR supports. Marge's GP would have been notified of the event and could review the encounter in the YHCR HIE.

YHCR HIE and the EHR records it adhere to the INTEROPen (supported by NHS England) HL7 FHIR STU3 [CareConnectAPI](https://nhsconnect.github.io/CareConnectAPI/) standard. This is a vendor neutral `open API` standard, for FHIR R4 versions see 
{{pagelink:Home/Technical-Framework/Query-API}}

The separation of records and workflow is a natural pattern. Here the BPMN inputs change definitions. 

- input is either responding to an `event` (e.g. Patient Admitted, High Blood pressure observation) or a `request`
- output is normally a series of events (e.g. Patient Discharged, Patient demographics updated)
- reviewing patients and recording new EHR data items takes part during the activity. It does not form part of the input or output (unless EHR systems are not available).

{{render:diagrams-ModernWorkflowBPMN}}

However, the big point is where the standards are now applying. openEHR, HL7 v3 and FHIR are no longer competing but complementing each other. We also see the introduction of IHE standards to support the workflow. 
On shared care records, IHE has been introduced to define how FHIR should be used to help share records, openEHR is both a definition and system which implement health records. HL7 v2 has been reintroduced to provide health administration process support.

**Most importantly we have refocused the problem around practitioners, patient and associated clinical processes and not around transferring health records.**

This pattern can be repeated again and again on the different stages of a patient's pathway and journey.
