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
        <td>Dosage</td>
        <td>Required</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

Preferable as a structured dosage aligned to the [FHIR Dose Syntax Guidance](https://simplifier.net/guide/ukcoreimplementationguideformedicines/elementdosage?version=current) but as a minimum, dosage.text.

### Example
```json
  "dosageInstruction" : [ {
        "text" : "One to two puffs to be inhaled as needed",
        "method" : {
          "coding" : [ {
            "system" : "http://snomed.info/sct",
            "code" : 420652005,
            "display" : "Until Gone"
          } ]
        }
    } ]
```

---