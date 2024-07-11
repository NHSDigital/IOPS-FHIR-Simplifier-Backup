## {{page-title}}


 <div markdown="span" class="alert alert-warning" role="alert"> PUT /Encounter?identifier={identifier}</div>

 This is an *upsert* interaction, if the identifier does not exist this SHALL act as a POST (create/insert) interaction otherwise this acts as an PUT (update) interaction.


### Event Triggers

These initial triggers are based on existing IHE PEM and HL7 v2 ADT definitions.

#### Basic Inpatient / Outpatient Encounter Management

| Trigger Event | Description	| IHE PEM | HL7 ADT (NHS England v2.4) |
|-- 
| Admit inpatient |	Is intended to be used for "Admitted" patients only. The event is sent as a result of a patient undergoing the admission process which assigns the patient to a bed. It signals the beginning of a patient’s stay in a healthcare facility. Normally, this information is entered in the primary Patient Administration system and broadcast to the nursing units and ancillary systems. It includes short stay and "John Doe" (e.g. patient name is unknown) admissions. |	[Patient Encounter Management [ITI-31]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-31.html)	| ADT_A01 |
|Register outpatient |Signals that the patient has arrived or checked in as a one-time, or recurring outpatient, and is not assigned to a bed. One example might be its use to signal the beginning of a visit to the Emergency Room (= Casualty, etc.). Note that some systems refer to these events as outpatient registrations or emergency admissions. |[Patient Encounter Management [ITI-31]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-31.html) |	ADT_A04	|
| Discharge patient | Signals the end of a patient’s stay in a healthcare facility (inpatient, outpatient, etc). It signals that the patient’s status has changed to "discharged" and that a discharge date has been recorded. The patient is no longer in the facility. The patient’s location prior to discharge should be present. |[Patient Encounter Management [ITI-31]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-31.html)|ADT_A03	|
| Pre-admit patient |	Is sent when a patient undergoes the pre-admission process. During this process, episode related data is collected in preparation for a patient’s visit or stay in a healthcare facility. For example, a pre-admit may be performed prior to inpatient or outpatient surgery so that lab tests can be performed prior to the surgery. This event can also be used to pre-register a non-admitted patient. |[Patient Encounter Management [ITI-31]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-31.html)| ADT_A04	|
| Transfer patient | Is issued as a result of the patient changing his or her assigned physical location.| [Patient Encounter Management [ITI-31]](https://profiles.ihe.net/ITI/TF/Volume2/ITI-31.html) | ADT_A02|