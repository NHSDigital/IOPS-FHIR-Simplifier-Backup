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
        <td>Reference</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

A business-required element identifying the clinically qualified human prescriber referenced by a PractitionerRole resource. 

They may be other possible references depending on the use case the full list is below. The resource being referenced should conform to one of the following:

* [Profile UKCore-Organization](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Organization?version=0.5.0)

* [Profile UKCore-Patient](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-Patient?version=1.0.0)

* [Profile UKCore-Practitioner](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/Profile-UKCore-Practitioner?version=1.0.0)

* [Profile UKCore-PractitionerRole](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-PractitionerRole?version=1.0.0)

* [Profile UKCore-RelatedPerson](https://simplifier.net/guide/uk-core-implementation-guide/Home/ProfilesandExtensions/ProfileUKCore-RelatedPerson?version=0.5.0)
 
* [UKCore-Device Profile](https://simplifier.net/hl7fhirukcorer4/ukcoredevice)

* [UKCore-CareTeam Profile](https://simplifier.net/hl7fhirukcorer4/ukcorecareteam)

#### Example
```json
 "requester" : {
    "reference" : "PractitionerRole/ed313d93-f470-420f-ae4e-2b7eb91d3f45",
    "display" : "Dr Jane Smith"
  },
```

---