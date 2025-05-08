## {{page-title}}

Discharge Medications, Discharge Prescription, or Medication To Take Out (TTO), are medications which are given to a patient when they are discharged from the hospital with a limited supply.

This instruction is sent to the GP via a **Discharge Summary** document, which may be electronic, and contains a wealth of information under several headings (each heading contains additional sub-headings with various cardinality).

The prescription may include information that the treatment is intended to continue beyond the supply of medication provided and there may be an expectation that the GP will continue the supply which would be highlighted within the discharge summary itself.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    More detail about the electronic discharge summary standard can be found on the <a class="nhsd-a-link" href="https://digital.nhs.uk/services/transfer-of-care-initiative/edischarge-summaries">NHS Digital</a> and <a href="https://theprsb.org/standards/edischargesummary/" class="nhsd-a-link">Professional Records Standards Body</a> websites.
</div>

### PRSB eDischarge Summary Standard - Top level headings

1: Patient demographics

2: GP practice

3: About me

4: Legal information

5: Safeguarding

... etc ...
<!--    <li>Professional contacts</li>
    <li>Personal contacts</li>
    <li>Individual requirements</li>
    <li>Participation in research</li>
    <li>Referrer details</li>
    <li>Admission details</li>
    <li>Discharge details</li>
    <li>Problems list</li>
    <li>Procedures and therapies</li>
    <li>Clinical summary</li>
    <li>Social context</li>
    <li>Investigation results</li>
    <li>Assessments</li>
    <li>Risks</li> -->
20: Allergies and adverse reactions

<span class="nhsd-a-text-highlight nhsd-a-text-highlight--bg-light-green">21: Medications and medical devices</span>
 <!-- <li>Information and advice given</li>
    <li>Distribution list</li>
    <li>Plan and requested actions</li>
    <li>Person completing record</li>
    <li>Care and support plan</li>
    <li>Contigency plans</li> -->
... etc ...

28: Additional supoort plans

Note that "Medications and Medical Devices" (highlighted in <span class="nhsd-a-text-highlight nhsd-a-text-highlight--bg-light-green">green</span>) is only <u>one heading out of 28</u>.

### Bundling the Discharge Medications with the Discharge Summary

All NHS Trusts will be familiar with the Transfer of Care process from secondary to primary care. They may complete a discharge summary using a system provided by an NHS supplier, a bespoke area within their Electronic Patient Record (EPR), or using paper.

Most digital solutions available today currently bundle discharge medications with the discharge summary, as it makes sense to bundle related things together into one document; however, this presents the following challenges.

#### Discharge summaries are completed <span class="nhsd-a-text-highlight nhsd-a-text-highlight--bg-light-blue">after</span> a patient has been discharged

{{ render: edischarge-summary-timeline }}{: .img-responsive }

A discharge summary has a linear progression during a patient stay, lasting for duration of the inpatient encounter.

A mature digital system may populate some of the discharge summary headings automatically; however, many of the headings require manual input from a clinician, which can be a time-consuming process.

NHS Trusts that send a digital copy of a discharge summary to GPs often delay the discharge notification to the ePMA system and the system responsible for sending the discharge summary electronically.

This delay is usually 6-24 hours after the patient has been discharged, and allows additional time for a clinician to complete the discharge summary.

The discharge summary alone is a single document where there is only one version of it that is clinically auditable and relevant - the one that is sent to the GP.

All iterations of the document up until the point the document is sent to the GP are considered as <u>draft</u>.

#### Discharge medications are required <span class="nhsd-a-text-highlight nhsd-a-text-highlight--bg-light-blue">before</span> a patient is discharged and have workflow

{{ render: discharge-medication-timeline }}{: .img-responsive }

A patient being discharged with medication will result in at least one `MedicationRequest` being sent to the pharmacy. An NHS Trust will have an additional clinical verification process in which a pharmacist will review the medications requested before approving and dispensing, resulting in at least one `MedicationDispense`, or several if there are multiple line items within the prescription.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: A discharge prescription could be requested several times during an inpatient encounter. For example, a patient may have been ready for discharge, but something happened which resulted in them staying within secondary care for longer.
</div>

Unlike the discharge summary, there can be many clinically auditable and relevant versions of a discharge prescription during an inpatient encounter; however, only the medications taken home when the patient is discharged from the hospital can be shown in the discharge prescription. 

<br />

### In summary

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    While discharge medications and discharge summaries happen around the time that a patient is discharged from a hospital, <strong>they are not the same thing</strong>.
</div>

It is recommended that any delays to the notification of inpatient discharge to downstream systems be avoided where possible.

Applicable FHIR resources: `MedicationStatement` and optionally `MedicationDispense`

---