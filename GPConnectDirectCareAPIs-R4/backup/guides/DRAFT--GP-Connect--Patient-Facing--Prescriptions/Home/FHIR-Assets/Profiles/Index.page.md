## {{page-title}}

This API utilises multiple different FHIR UK Core resources, dependent on the use case.

<table data-responsive>
    <thead>
        <tr>
            <th>Profile</th>
            <th>Use</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="nhsd-t-body">{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-Task}}</td>
            <td class="nhsd-t-body">To request a reissue of a repeat prescription. Must have a <code>focus</code> reference of a <code>MedicationRequest</code> to contain the medication information relating to the request.</td>
        </tr>
              
        <tr>
            <td class="nhsd-t-body">{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationRequest}}</td>
            <td class="nhsd-t-body">To display previously prescribed medication to the patient, including the <code>courseOfTherapyType</code>.</td>
        </tr>
                <tr>
            <td class="nhsd-t-body">{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-MedicationStatement}}</td>
            <td class="nhsd-t-body">To display a patient's medication, both past and present.</td>
        </tr>
  <tr>
            <td class="nhsd-t-body">{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-PractitionerRole}}</td>
            <td class="nhsd-t-body">To display practitioner details back to the patient.</td>
        </tr>
                <tr>
            <td class="nhsd-t-body">{{pagelink:Home/FHIR-Assets/All-Assets/Profiles/UKCore-OperationOutcome}}</td>
            <td class="nhsd-t-body">To display errors back to the patient.</td>
        </tr>
    </tbody>

</table>

---