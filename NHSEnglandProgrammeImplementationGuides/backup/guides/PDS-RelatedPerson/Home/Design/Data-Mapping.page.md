## {{page-title}}

### RelatedPerson

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>unique_identifier</td>
    <td>1..1</td>
    <td>RelatedPerson.id</td>
    <td>Type: Identifier<br>PDS allocated identifier for the relationship</td>
</tr>
<tr>
    <td>relationship_type</td>
    <td>1..1</td>
    <td>RelatedPerson.relationship</td>
    <td>Type: CodeableConcept
</td>
</tr>
<tr>
    <td>period</td>
    <td>0..1</td>
    <td>RelatedPerson.period</td>
    <td>Type: Period<br>Start & end dates for relationship</td>
</tr>
<tr>
    <td>telecom</td>
    <td>0..1</td>
    <td>RelatedPerson.telecom</td>
    <td>Type: ContactPoint<br>Phone, email etc.</td>
</tr>
<tr>
    <td>address</td>
    <td>0..1</td>
    <td>RelatedPerson.address</td>
    <td>Type: Address<br>Address</td>
</tr>
<tr>
    <td>name</td>
    <td>0..1</td>
    <td>ReleatedPerson.name</td>
    <td>Type: HumanName<br>Related person’s name</td>
</tr>
<tr>
    <td>nhs_number</td>
    <td>0..1</td>
    <td>RelatedPerson.identifier</td>
    <td>Type: Identifier.<br>Related person’s NHS Number (optional).</td>
</tr>
<tr>
    <td>language (including preference proficiency)</td>
    <td>0..1</td>
    <td>RelatedPerson.communication.language<br>RelatedPerson.communication.preferred</td>
    <td>Type: CodeableConcept<br>Of related person.</td>
</tr>
<tr>
    <td>preferred_written_format</td>
    <td>0..1</td>
    <td>RelatedPerson.extension-UKCore-ContactPreference</td>
    <td>Type: Extension(CodeableConcept)<br>Of related person.</td>
</tr>
<tr>
    <td>preferred_contact_method</td>
    <td>0..1</td>
    <td>RelatedPerson.extension-UKCore-ContactPreference</td>
    <td>Type: Extension(CodeableConcept)<br>Of related person</td>
</tr>
<tr>
    <td>copy_correspondence_indicator</td>
    <td>0..1</td>
    <td>RelatedPerson.extension-UKCore-CopyCorrespondenceIndicator</td>
    <td>Type: Extension (Boolean)<br>CC’d or not</td>
</tr>
<tr>
    <td>next_of_kin_indicator</td>
    <td>0..1</td>
    <td>RelatedPerson.relationship</td>
    <td>Type: CodeableConcept<br>Populated as follows:<br/> "coding": [<br/>
        {<br/>
          "system": "http://terminology.hl7.org/CodeSystem/v3-RoleCode",<br/>
          "code": "NOK",<br/>
          "display": "Next of Kin"<br/>
        }<br/>
      ]</td>
</tr>
</tbody>
</table>