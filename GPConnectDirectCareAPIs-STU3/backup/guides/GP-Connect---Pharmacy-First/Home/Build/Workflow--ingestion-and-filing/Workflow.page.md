## {{page-title}}

The term 'workflow' can be thought of as a work or task list.

It is expected that the data from this specification will be **ingested** by the receiving system, and stored within a holding area which is either:

- separate from the patient record
- filed as provisional until a clinician reviews and accepts the incoming data to be saved into the patient record

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
   <b>Note:</b> The data will not be auto-filed in the initial version of this specification.
</div>

This is not an ideal situation and will result in administrative burden; however, it is hoped that as clinicians become accustomed to receiving structured data (rather than unstructured documents) filing can become automated.

{{render: worklow--fhir-inbox-patient-record.png}}

---