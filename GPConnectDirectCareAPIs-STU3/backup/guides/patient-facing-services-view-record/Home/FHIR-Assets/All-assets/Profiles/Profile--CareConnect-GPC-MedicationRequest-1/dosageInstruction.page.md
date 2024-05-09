## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

Complete dosage instructions as text.

Where the dosage instructions have been changed during the lifetime of the Medication/Medical Device plan append the following warning text to end of the dosage instructions:

`WARNING – Dosage has changed during the effective period. The latest change was made on DD-Mmm-YYYY` - where `DD-Mmm-YYYY` is the date the dosage was last changed.

In exceptional cases where for legacy data there is no dosage recorded in the system then this **MUST** be populated with the text: `No information available`.

The `patientInstruction` elemement **MAY** provide additional instructions to the patient, this is, RHS of the prescription label.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: The information standards notice (ISN): <a href="https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/dapb4013-medicine-and-allergy-intolerance-data-transfer">DAPB4013: Medicine and Allergy/Intolerance Data Transfer</a> stipulates that <em>structured</em> dosage instructions should be sent.<br /><br />GP Connect providers may uplift to the Information Standards Notice outlined above at different times so please account for both textual and structured representations.<br /><br />See <a href="https://simplifier.net/guide/gp-connect-access-record-structured/Home/Design/Medication-and-medical-device-guidance?version=current#Medication-and-Medical-Device-interoperability">Medication and Medical Device interoperability</a> for additional information.
</div>

<h5><ins>Example</ins></h5>

Legacy (free text):

```xml
<dosageInstruction>
    <text value="10 milligram - two times a day - oral - Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <patientInstruction value="Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
</dosageInstruction>
```

Structured dose syntax:

```xml
<dosageInstruction>
    <text value="10 milligram - two times a day - oral - Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <patientInstruction value="Swallow your capsules whole with a glass of water. DO NOT break, crush or chew them" />
    <timing>
        <repeat>
            <frequency value="1" />
            <period value="2" />
            <periodUnit value="d" />
            <when value="C" />
        </repeat>
    </timing>
    <route>
        <coding>
            <system value="https://snomed.info/sct" />
            <code value="26643006" />
        </coding>
        <text value="oral" />
    </route>
    <doseQuantity>
        <value value="10" />
        <unit value="milligram" />
        <system value="https://unitsofmeasure.org" />
        <code value="mg" />
    </doseQuantity>
</dosageInstruction>
```

---
