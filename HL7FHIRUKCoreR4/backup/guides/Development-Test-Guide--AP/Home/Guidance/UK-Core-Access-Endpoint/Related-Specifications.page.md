## {{page-title}}

### Patient Index Provider

The Patient Index Provider capabilities in the UK Core Access implementation guide are closely related to patient search defined in international interoperability standards including:
- [HL7 International Patient Access](https://build.fhir.org/ig/HL7/fhir-ipa/index.html)
- [IHE Patient Demographics Query for Mobile](https://profiles.ihe.net/ITI/PDQm/index.html)

#### Patient search
Servers are required to support Patient search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Patient Index Provider</th>
<th width="10%">IPA</th>
<th width="10%">PDQm</th>
</tr>

<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>identifier </td>
<td>SHALL </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>family </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
<tr>
<td>given </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
<tr>
<td>name </td>
<td>SHALL </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
<tr>
<td>gender </td>
<td>SHALL </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
<tr>
<td>birthdate</td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
</table>


### Clinical Data Provider
The Clinical Data Provider capabilities in the UK Core Access implementation guide are closely related to clinical data retrieval
defined in international interoperability standards including:
- [HL7 International Patient Access](https://build.fhir.org/ig/HL7/fhir-ipa/index.html)
- [IHE Query for Existing Data for Mobile](https://wiki.ihe.net/index.php/Query_for_Existing_Data_for_Mobile_(QEDm))

#### Patient search
Servers are required to support Patient search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">PDQm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>identifier </td>
<td>SHALL </td>
<td>SHOULD </td>
<td>SHALL </td>
</tr>
</table>


#### AllergyIntolerance search
Servers are required to support AllergyIntolerance search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>clinical-status </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
<tr>
<td>date </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>last-date </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
</table>

#### Immunization search
Servers are required to support Immunization search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHOULD </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>status </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
<tr>
<td>date </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
</table>


#### MedicationAdministration search
Servers are required to support MedicationAdministration search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>status </td>
<td>SHALL </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>effective-time </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
</table>


#### MedicationDispense search
Servers are required to support MedicationDispense search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHOULD </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>status </td>
<td>SHALL </td>
<td>MAY </td>
<td>MAY </td>
</tr>
<tr>
<td>whenprepared </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
</table>

#### MedicationRequest search
Servers are required to support MedicationRequest search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHOULD </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>status </td>
<td>SHALL </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
<tr>
<td>authoredon </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
</table>

#### MedicationStatement search
Servers are required to support MedicationStatement search parameters as follows:

<table class="assets">
<tr>
<th width="40%">Parameter</th>
<th width="40%">Clinical Data Provider</th>
<th width="10%">IPA</th>
<th width="10%">QEDm</th>
</tr>
<tr>
<td>_id </td>
<td>SHOULD </td>
<td>SHOULD </td>
<td>SHOULD </td>
</tr>
<tr>
<td>patient </td>
<td>SHALL </td>
<td>SHALL </td>
<td>SHALL </td>
</tr>
<tr>
<td>status </td>
<td>SHALL </td>
<td>SHOULD </td>
<td>MAY </td>
</tr>
<tr>
<td>effective </td>
<td>SHOULD </td>
<td>MAY </td>
<td>MAY </td>
</tr>
</table>

<hr class="thickline">