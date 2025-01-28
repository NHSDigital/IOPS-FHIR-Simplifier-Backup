# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    This page is work in progress...
</div>

## What are one-stop dispensing and patients’ own drugs schemes?

Definition taken from [hospitalpharmacyeurope.com](https://hospitalpharmacyeurope.com/news/editors-pick/guide-to-pod-schemes-and-one-stop-dispensing/).

“One-stop dispensing” refers to dispensing of the inpatient and discharge medication as a single supply on admission, already labelled with administration instructions for the patient. This system has also been referred to as “dispensing for discharge”. If all medication is dispensed in this way, patients should not have to wait for a separate supply of medication to be dispensed at discharge.

“Patients’ own drugs” (POD) schemes involve patients bringing supplies of their own medication into hospital so that, following assessment by pharmacy or nursing staff, they can be used during their inpatient stay and/or at discharge. Using PODs during the inpatient stay usually involves storing them in an individual bedside medicine cabinet rather than in a drug trolley.

While one-stop dispensing does not necessarily have to include the use of patients’ own drugs, and vice versa, in practice the two tend to operate together.

### The counter argument

One-stop dispensing is not used everywhere and has some drawbacks. Here is an short article from the [pharmaceutical-journal.com](https://pharmaceutical-journal.com/article/opinion/one-stop-dispensing-has-had-its-day-time-to-embrace-technology) that suggests using one-stop has had its day.

## FHIR implementation guidance when using one-stop schemes

To be written... to highlight how FHIR resources may be used in different ways and contain different data compared to other medicines schemes that might be adopted within a Trust.

<!-- notes

Meds labels will be patient friendly, so dosage should be friendly.
Assume product-based, so dose as "1 tablet" not "50mg".

Consider using the MedicationRequest.category of "discharge" for medicines requested during the inpatient stay that could then be taken away on discharge. This would also then provided a means to differentiate from any medication requests that are not following the one-stop process.

end notes -->
