## {{page-title}}

### capabilities
A Clinical Data Provider SHALL support the [capabilities](https://hl7.org/fhir/R4/http.html#capabilities) interaction so that a Consumer can retrieve a [CapabilityStatement](https://hl7.org/fhir/R4/capabilitystatement.html) resource of type `instance` that specifies which resource types and interactions are supported by the FHIR endpoint:
```
GET [base]/metadata
```

The CapabilityStatement SHALL be conformant with this implementation guide and SHOULD state that the FHIR endpoint instantiates the UK Core Access Clinical Data [capabilities](./CapabilityStatement-UKCoreAccessClinicalDataProvider.html).

The Provider MAY provide further capabilities at this FHIR endpoint, in addition to those required by a Clinical Data Provider.

### Patient search
A Clinical Data Provider SHALL support the [search](https://hl7.org/fhir/R4/http.html#search) interaction on the [Patient](https://hl7.org/fhir/R4/patient.html) so that a Consumer can retrieve a set of Patient resources matching the search criteria and conforming to the {{pagelink:Profile-Patient}}.

A Clinical Data Provider supports at least the following Patient search parameters:

<table class="assets">
<tr>
<th width="15%">Conformance</th>
<th width="15%">Parameter</th>
<th width="15%">Type</th>
<th width="55%">Description</th>
</tr>

<tr>
<td>SHOULD</td>
<td><a href="#patient-_id">_id</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a></td>
<td> </td>
</tr>

<tr>
<td>SHALL</td>
<td><a href="#patient-identifier">identifier</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a> </td>
<td>A patient identifier</td>
</tr>
</table>

#### `Patient _id`
See <a href="#patient-_id">Patient id</a> from Patient Index Provider for details.

#### `Patient identifier`
See <a href="#patient-identifier">Patient identifier</a> from Patient Index Provider for details.

---

{{render:profile-ukcore-allergyintolerance-clinical-data-provider}}

---

{{render:profilesandextensions-profile-ukcore-immunization-clinical-data-provider}}

---

<hr class="thickline">