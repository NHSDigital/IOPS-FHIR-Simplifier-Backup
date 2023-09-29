### {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>User Storey</strong>: 
    Whaleshame community pharmacy downloads the FHIR Message and dispenses the medicine to Svetlana. The pharmacy stock control system sends a FHIR Message back to EPS using MedicationDispense to inform the prescription has been dispensed.
</div>

{{render:PrescriptionDispense-duplicate-2}}

Each time medication is provided to a patient (or a patient’s representative) a “Dispense Notification” HL7 interaction must be submitted to EPS. The dispense notification interaction contains the information of the dispensed medication items for the prescription.

It should be noted that no communication with the EPS is required during the medication preparation stage of the dispensing process.

During the process of preparing the medication, the dispense notification interaction can be created and populated with medication information. The “Author” entity of this message must be the currently logged on user. The dispense notification should be submitted when the medication is supplied to the patient (or patient representative) as closely as business processes allow. Dispense Notification messages can be submitted after the supply event, and outside the “Dispensing Window”, in which case the “effectiveTime” attribute within the message should record the date/time that the supply event occurred, rather than the date/time the Dispense Notification was submitted.

See also:

- {{pagelink: Dispense-OwingsandPartialDispensing}}
- {{pagelink: ReturningPrescriptionstoEPS.md}}
- {{pagelink: NonDispensedItems}}
- {{pagelink: CancelADispenseNotification}}
