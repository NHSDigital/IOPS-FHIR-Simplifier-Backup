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
        <td>Mandatory</td>
        <td>1..1</td>
      </tr>
    </tbody>
</table>

Where the requested medication is contained within the [NHS dm+d](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) then it must be recorded using the dm+d standard.

* The `medicationCodeableConcept.coding.code` should be the code for the medication.

* The `medicationCodeableConcept.coding.display` should be the description for the medication, i.e. the same value as medicationCodeableConcept.text.


### Example 
``` json
    "medicationCodeableConcept": [
      {
        "coding": [
          {
            "system": "http://snomed.info/ct",
            "code": 3113111000001106,
            "display": "Pulmicort 100 Turbohaler (AstraZeneca UK Ltd)"
          }
        ]
      }
    ]
```

---