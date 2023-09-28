---
topic: Profile-Immunization-ClinicalDataProvider
---
## Clinical Data Provider

### Immunization search
Where the underlying system can reliably provide the information, a Clinical Data Provider SHOULD support the [search](https://hl7.org/fhir/R4/http.html#search) interaction on the [Immunization](https://hl7.org/fhir/R4/Immunization.html) resource so that a Consumer can retrieve a set of Immunization resources matching the search criteria and conforming to the {{pagelink:Profile-Immunization}}.

A Clinical Data Provider supports at least the following search parameters:

<table class="assets">
<tr>
<th width="15%">Conformance</th>
<th width="15%">Parameter</th>
<th width="15%">Type</th>
<th width="55%">Description</th>
</tr>
<tr>
<td>SHOULD</td>
<td><a href="#immunization-_id">_id</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a></td>
<td> </td>
</tr>
<tr>
<td>SHALL</td>
<td><a href="#immunization-patient">patient</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#reference">reference</a> </td>
<td>Who the sensitivity is for</td>
</tr>
<tr>
<td>SHALL</td>
<td><a href="#immunization-status">status</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a> </td>
<td>active, inactive or resolved</td>
</tr>
<tr>
<td>SHOULD</td>
<td><a href="#immunization-date">date</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#date">date</a> </td>
<td>Date first version of the resource instance was recorded</td>
</tr>
</table>
<br>

A Clinical Data Provider supports at least the following search parameter combinations:

<table class="assets">
<tr>
<th width="15%">Conformance</th>
<th width="20%">Parameters</th>
<th width="65%">Example</th>
</tr>
<tr>
<td>SHOULD</td>
<td>patient+date</td>
<td><code>GET [[base]/Immunization?patient=[id]&date=[date]</code></td>
</tr>
<tr>
<td>SHOULD</td>
<td>patient+status</td>
<td><code>GET [[base]/Immunization?patient=[id]&status=[status]</code></td>
</tr>
</table>

---

<h4 id="immunization-_id"><code>Immunization _id</code></h4>
The Provider SHOULD support search by the logical identifier of the Immunization resource:

```
GET [base]/Immunization?_id=[id]
```

---

<h4 id="immunization-patient"><code>Immunization patient</code></h4>
The Provider SHALL support search by patient:

```
GET [base]/Immunization?patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Immunization?patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing Immunization resources that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd`.

---

<h4 id="immunization-status"><code>Immunization status</code></h4>
The Provider SHALL support search by status:

```
GET [base]/Immunization?clinical-status=[status]&patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Immunization?status=active&patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing Immunization resources that are completed and reference reference patient `b88f0099-5213-4502-a49d-cc3887027bdd` .

---

<h4 id="immunization-date"><code>Immunization date</code></h4>
The Provider SHOULD support search by administration date:

```
GET [base]/Immunization?date=[date]&patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/Immunization?date=ge2018-01-01&patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing Immunization resources administered on or after `2018-01-01` that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd`.

Where a Provider supports search by date, the Provider SHOULD support:
- partial dates *e.g.* `date=1970-09`
- the `eq`, `ge`, `le` operators *e.g.* `date=ge1970-09-01`
- multiple date parameters *e.g.* `date=ge1970-09-01&date=le1970-10-01`
