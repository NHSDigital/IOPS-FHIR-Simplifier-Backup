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
        <td>Identifier</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The practitioner to which the role relates as a reference to UKCore-Practitioner.

### Example
```json
"practitioner" : {
   "display" : "Dr Jane Smith",
   "identifier" : {
     "system" : "https://fhir.hl7.org.uk/Id/gmc-number",
     "value" : "C9876543"
    }
}
```

---