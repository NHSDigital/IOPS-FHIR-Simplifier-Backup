## {{page-title}}

One of the purposes in developing the FHIR&reg; profiles is to ensure that clinical data is, as much as possible, presented the same way regardless of the provider system.
This ensures the consuming system (and clinician) will always know where to look for each type of information.
However, information about the patient is not just held within the profiles but in how those profiles are linked together.
For example, linking a medication to a problem means that as well as the record showing what the patient is taking, it also explains why they are taking it.

For a consuming system to be able to interpret this linkage information correctly, it needs to be presented in the same way regardless of the providing system.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
	<i class="fas fa-exclamation-circle text-primary"></i> <b>Note:</b> The diagrams are illustrative to support the specification text. There may be some simplifications or omissions, for instance not all possible linkages to the resources for investigations are shown.
</div>

### GP Connect FHIR&reg; model ###

To support this, GP Connect has developed a FHIR model that identifies all the GP Connect FHIR profiles and how they are related together to store the patient record.

The model currently covers Consultations, Problems, Medications and Medical Devices, Allergies, Immunisations, Uncategorised Data, Referrals, Investigations, Documents and Diary Entries.
Other clinical areas will be added as they are developed.

{{ render: GP_Connect_FHIR_Model_v5.png }}

<div align="center">
{{ render: GP_Connect_FHIR_Model_Key_v2.png }}
</div>

The relationships between two FHIR profiles are recorded in only one of the linked FHIR profiles (similar to in a relational database management system).
This is shown by the direction of the arrow in the FHIR model.
For example, the `MedicationStatement` profile contains a field that can be used to look up the linked `Medication`.
There is no field in the `Medication` profile that can be used to look up the linked `MedicationStatement`.