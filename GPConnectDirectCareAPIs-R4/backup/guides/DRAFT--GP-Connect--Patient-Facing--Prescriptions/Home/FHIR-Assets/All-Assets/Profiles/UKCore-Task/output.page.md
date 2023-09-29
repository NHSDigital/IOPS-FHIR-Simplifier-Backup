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

Information produced as part of the task.

This can be used to identify the prescription outside of the scope of the patient facing API. 

In this specific case, once the prescription is created and been sent to EPS to be dispensed. This allows full end to end tracking of the request.

When applicable it must contain the EPS prescription ID and reference the code `sent-to-eps`.

The set of prescription ordering parameters can be found [here.](https://simplifier.net/gp-connect---direct-care-apis---r4/gpconnect-prescriptionorderingparameters)

### Example
``` json
"output": [
    {
        "type": {
            "coding": [
                {
                    "system": "https://fhir.hl7.org.uk/GPConnect-PrescriptionOrderingParameters",
                    "code": "sent-to-eps",
                    "display": "Sent to EPS"
                }
            ]
        },
            "valueIdentifier": {
                "system": "https://fhir.nhs.uk/Id/prescription-order-item-number",
                "value": "4857b9d3-b714-44b9-9e67-3df67275b785"
            }
    }
]
```

---