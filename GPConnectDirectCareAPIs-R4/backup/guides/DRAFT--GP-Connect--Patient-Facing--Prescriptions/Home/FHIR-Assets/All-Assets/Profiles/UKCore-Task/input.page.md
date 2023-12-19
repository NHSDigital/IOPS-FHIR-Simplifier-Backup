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
        <td>Conditional</td>
        <td>0..*</td>
      </tr>
    </tbody>
</table>

Information used to perform the task.

In this case it will be supplied when the patient wishes for their prescription to be dispensed by a different pharmacy to their nominated pharmacy on PDS.

When applicable it must contain the organization ODS code and reference the code `preferred-performer`. 

The set of prescription ordering parameters can be found [here.](https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Terminology/All-CodeSystems/CodeSystem-England-PFSPrescriptionOrderingParameter?version=1.1.0)

### Example
``` json
"input": [
    {
        "type": {
            "coding": [
                {
                    "system": "https://fhir.nhs.uk/England/CodeSystem/England-PFSPrescriptionOrderingParameter",
                    "code": "preferred-performer",
                    "display": "Preferred performer"
                }
            ]
        },
        "valueIdentifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FLM49"
        }
    }
]
```

---