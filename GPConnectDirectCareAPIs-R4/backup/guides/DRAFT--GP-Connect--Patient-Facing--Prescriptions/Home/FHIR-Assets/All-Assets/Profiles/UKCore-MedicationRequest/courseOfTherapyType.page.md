## {{page-title}}

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>DataType</th>
            <th data-no-sort>Optionality</th>
            <th data-no-sort>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Code</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Necessary in order to denote the type of therapy, such as an acute/one-off medication compared to a repeat/on-going medication.

Will be used in order to denote whether a prescription is acute or repeat.

<table data-responsive>
    <thead>
        <tr>
            <th>Code</th>
            <th>System</th>
            <th>Display</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>continuous</td> <td>https://fhir.hl7.org.uk/CodeSystem/UKCore-MedicationRequestCourseOfTherapy</td>
        <td>Continuous long term therapy</td>
      </tr>
            <tr>
        <td>acute</td>   <td>https://fhir.hl7.org.uk/CodeSystem/UKCore-MedicationRequestCourseOfTherapy</td>
        <td>Short course (acute) therapy</td>
      </tr>
    </tbody>
</table>

### Example
```json
  "courseOfTherapyType" : {
    "coding" : [ {
      "system" : "https://fhir.hl7.org.uk/CodeSystem/UKCore-MedicationRequestCourseOfTherapy",
      "code" : "continuous",
      "display" : "Continuous long term therapy"
    } ]
  },
```

---