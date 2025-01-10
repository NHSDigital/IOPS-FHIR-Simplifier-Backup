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
        <td>BackboneElement</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

### dispenseRequest.numberOfRepeatsAllowed
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>UnsignedInt</td>
        <td>Optional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

An integer indicating the number of times, in addition to the original dispense, (aka refills or repeats) that the patient can receive the prescribed medication. Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus "3 repeats", then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.

The number of repeat issues authorised if specified.
MUST be present where a `continuous` is authorised for a defined number of issues.

MUST NOT be specified where the number of repeat issues has not been defined. Therefore, the `numberOfRepeats` allowed is the total number of allowed issues. See also extension `repeatInformation`

### Example
``` json
"numberOfRepeatsAllowed": 6,
```

### dispenseRequest.quantity
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
    <td>simpleQuantity</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The amount that is to be dispensed for one fill.

```json
"quantity": {
    "value": 1,
    "unit": "inhaler",
    "system": "http://snomed.info/sct",
    "code": "334980009"
},
```

### dispenseRequest.expectedSupplyDuration
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Duration</td>
        <td>Optional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Number of days’ supply per dispense.

```json
"expectedSupplyDuration": {
    "value": 28,
    "unit": "days",
    "system": "http://unitsofmeasure.org",
    "code": "d"
},
```

### dispenseRequest.performer
<table data-responsive>
    <thead>
        <tr>
            <th>DataType</th>
            <th>Optionality</th>
            <th>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>identifier</td>
        <td>Conditional</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

Patients pharmacy preferences may be sourced from PDS.

Patients pharmacy preferences may be overriden by a 'one-off pharmacy nomination' by populating the dispenseRequest.performer.identifier with the ODS code of the destination pharmacy. The one off ODS code can be obtained from input element of the corresponding Task resource.

### Example

```json
    "performer": {
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/ods-organization-code",
            "value": "FX748"
        }
    }
```

---