---
topic: Profile-Patient-IndexProvider
---
## Patient Index Provider

### `capabilities`
A Patient Index Provider SHALL support the <a href="https://hl7.org/fhir/R4/http.html#capabilities">capabilities</a> interaction so that
a Consumer can retrieve a <a href="https://hl7.org/fhir/R4/capabilitystatement.html">CapabilityStatement</a> resource of type
`instance` that specifies which resource types and interactions are supported by the FHIR endpoint:
```
GET [base]/metadata
```
The CapabilityStatement SHALL be conformant with this implementation guide and SHOULD state that the FHIR endpoint instantiates the UKCore Access Patient Index capabilities ./CapabilityStatement-UKCoreAccessPatientIndexProvider.html".
The Provider MAY provide further capabilities at this FHIR endpoint, in addition to those required by a Patient Index Provider.

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/metadata`
the Provider would respond with a CapabilityStatement resource. 

---

### `Patient search`
A Patient Index Provider SHALL support the <a href="https://hl7.org/fhir/R4/http.html#search">search</a> interaction on the <a href="https://hl7.org/fhir/R4/patient.html">Patient</a> resource so that a Consumer can retrieve a set of Patient resources matching the search criteria and conforming to {{pagelink:Profile-Patient}}.

A Patient Index Provider supports at least the following search parameters:

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

<tr>
<td>SHOULD</td>
<td><a href="#patient-family">family</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#string">string</a></td>
<td>A portion of the family name of the patient</td>
</tr>

<tr>
<td>SHOULD</td>
<td><a href="#patient-given">given</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#string">string</a></td>
<td>A portion of the given name of the patient</td>
</tr>

<tr>
<td>SHALL</td>
<td><a href="#patient-name">name</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#string">string</a></td>
<td> A server defined search that may match any of the string fields in the HumanName, including family, given, prefix, suffix, and/or text</td>
</tr>

<tr>
<td>SHALL</td>
<td><a href="#patient-gender">gender</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a> </td>
<td>Gender of the patient</td>
</tr>

<tr>
<td>SHOULD</td>
<td><a href="#patient-birthdate">birthdate</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#date">date</a> </td>
<td>The patient's date of birth</td>
</tr>
</table>
<br>

A Patient Index Provider supports at least the following search parameter combinations:

<table class="assets">
<tr>
<th width="15%">Conformance</th>
<th width="20%">Parameters</th>
<th width="65%">Example</th>
</tr>

<tr>
<td>SHOULD</td>
<td>birthdate+family</td>
<td><code>GET [[base]/Patient?birthdate=[date]&family=[name]</code></td>
</tr>

<tr>
<td>SHOULD</td>
<td>birthdate+name</td>
<td><code>GET [[base]/Patient?birthdate=[date]&name=[name]</code></td>
</tr>

<tr>
<td>SHOULD</td>
<td>gender+family</td>
<td><code>GET [[base]/Patient?gender=[gender]&family=[name]</code></td>
</tr>

<tr>
<td>SHOULD</td>
<td>gender+name</td>
<td><code>GET [[base]/Patient?gender=[gender]&name=[name]</code></td>
</tr>
</table>

---

<h4 id="patient-_id"><code>Patient _id</code></h4>

The Provider SHOULD support search by the logical identifier of the Patient resource:
```
GET [base]/Patient?_id=id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?_id=b88f0099-5213-4502-a49d-cc3887027bdd`
the Provider would respond with a Bundle containing Patient resources with id `b88f0099-5213-4502-a49d-cc3887027bdd`. Example Bundle-Response-patientsearchbyid.html"

---

<h4 id="patient-identifier"><code>Patient identifier</code></h4>

The Provider SHALL support search by identifier:
```
GET [base]/Patient?identifier=system]|value]
```

##### **Find a patient by NHS Number**
The national identifier within England, Wales and the Isle of Man is the <a href="https://digital.nhs.uk/data-and-information/information-standards/information-standards-and-data-collections-including-extractions/publications-and-notifications/standards-and-collections/isb-0149-nhs-number">NHS Number</a> which uses the identifier system `https://fhir.nhs.uk/Id/nhs-number`.

The Provider MAY support search by NHS Number:
```
GET [base]/Patient?identifier=[https://fhir.nhs.uk/Id/nhs-number|NHS Number]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?identifier=https://fhir.nhs.uk/Id/nhs-number|9912003888` the Provider would respond with a Bundle containing Patient resources with NHS Number `9912003888`. Example Bundle-Response-patientsearchbynhsnumber.html"

##### **Find a patient by CHI Number**
The national identifier within Scotland is the <a href="https://www.ndc.scot.nhs.uk/Dictionary-A-Z/Definitions/index.asp?ID=128">CHI Number</a>. 

The Provider MAY support search by CHI Number.

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Note</h4>
No identifier NamingSystem has been published for CHI Number. Potential implementers are recommended to contact the UK Core development team, and the relevant data standards team for this domain.
</div>


##### **Find a patient by H&C Number**
The national identifier within Northern Ireland is the <a href="https://www.datadictionary.nhs.uk/attributes/health_and_care_number.html">H&C Number</a>.

The Provider MAY support search by H&C Number.

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Note</h4>
No identifier NamingSystem has been published for H&C Number. Potential implementers are recommended to contact the UK Core development team, and the relevant data standards team for this domain.
</div>

##### **Find a patient by local identifier**
Organisations holding patient data are likely to have their own identifier systems _e.g._ a hospital number from a PAS system.

Organisations may use existing OIDs or allocate their own system but SHALL ensure that these do not clash with those used elsewhere.

Health and Care organisations in Wales should adopt the <a href="https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Design/Naming-Systems.page.md?version=current">NHS Wales Data Standards for Welsh Patient Identifiers</a>.

The Provider MAY support search by local identifier:
```
GET [base]/Patient?identifier=[Local system]|[PAS Identifier]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?identifier=https://fhir.example-provider.nhs.uk/Id/pas-identifier|12345`
the Provider would respond with a Bundle containing Patient resources with hospital number `12345` issued by the `provider` organisation. Example Bundle-Response-patientsearchbylocalsystem.html"

##### **Find a patient by identifier value**
It is possible to search for patient by providing an identifier without specifying the identifier system.

The Provider MAY support search by identifier value:
```
GET [base]/Patient?identifier=[Identifier]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?identifier=12345`
the Provider would respond with a Bundle containing any Patient resources with identifier `12345` issued by any organisation. Example Bundle-Response-patientsearchbyidentifiervalue.html"

---

<h4 id="patient-family"><code>Patient family</code></h4>

The Provider SHOULD support search by patient family name:
```
GET [base]/Patient?family=[name]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?family=Smith`
the Provider would respond with a Bundle containing Patient resources with family name starting with `Smith`. Example Bundle-Response-patientsearchbyfamily.html"

---

<h4 id="patient-given"><code>Patient given</code></h4>

The Provider SHOULD support search by patient given name:
```
GET [base]/Patient?given=[name]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?given=Rich`
the Provider would respond with a Bundle containing Patient resources with given name starting with `Rich`. Example Bundle-Response-patientsearchbygiven.html"

---

<h4 id="patient-name"><code>Patient name</code></h4>

The Provider SHALL support search by patient name:
```
GET [base]/Patient?name=[name]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?name=Rich`
the Provider would respond with a Bundle containing Patient resources where part of the name starts with `Rich`. Example Bundle-Response-patientsearchbyname.html"

---

<h4 id="patient-gender"><code>Patient gender</code></h4>

A Provider SHALL support search by patient gender:
```
GET [base]/Patient?gender=c[ode]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?gender=female`
the Provider would respond with a Bundle containing Patient resources with gender `female`. Example Bundle-Response-patientsearchbygender.html"

---

<h4 id="patient-birthdate"><code>Patient birthdate</code></h4>

The Provider SHOULD support search by patient birthdate:
```
GET [base]/Patient?birthdate=[date]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Patient?birthdate=1970-09-11`
the Provider would respond with a Bundle containing Patient resources with birthdate `1970-09-11`. Example Bundle-Response-patientsearchbybirthdate.html"

Where a Provider supports search by patient birthdate, the Provider SHOULD support:
- partial dates *e.g.* `birthdate=1970-09`
- the `eq`, `ge`, `le` operators *e.g.* `birthdate=ge1970-09-01`
- multiple date parameters *e.g.* `birthdate=ge1970-09-01&birthdate=le1970-10-01`

 