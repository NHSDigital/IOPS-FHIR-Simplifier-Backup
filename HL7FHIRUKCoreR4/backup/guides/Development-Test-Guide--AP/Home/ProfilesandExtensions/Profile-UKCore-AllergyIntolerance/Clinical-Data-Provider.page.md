---
topic: Profile-AllergyIntolerance-ClinicalDataProvider
---
## Clinical Data Provider

### AllergyIntolerance search
Where the underlying system can reliably provide the information, a Clinical Data Provider SHOULD support the [search](https://hl7.org/fhir/R4/http.html#search) interaction on the [AllergyIntolerance](https://hl7.org/fhir/R4/allergyintolerance.html) resource so that a Consumer can retrieve a set of AllergyIntolerance resources matching the search criteria and conforming to the {{pagelink:Profile-AllergyIntolerance}}.

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
<td><a href="#allergyintolerance-_id">_id</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a></td>
<td> </td>
</tr>
<tr>
<td>SHALL</td>
<td><a href="#allergyintolerance-patient">patient</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#reference">reference</a> </td>
<td>Who the sensitivity is for</td>
</tr>
<tr>
<td>SHALL</td>
<td><a href="#allergyintolerance-clinical-status">clinical-status</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#token">token</a> </td>
<td>active, inactive or resolved</td>
</tr>
<tr>
<td>SHOULD</td>
<td><a href="#allergyintolerance-date">date</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#date">date</a> </td>
<td>Date first version of the resource instance was recorded</td>
</tr>
<tr>
<td>SHOULD</td>
<td><a href="#allergyintolerance-last-date">last-date</a></td>
<td><a href="https://hl7.org/fhir/R4/search.html#date">date</a> </td>
<td>Date(/time) of last known occurrence of a reaction</td>
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
<td><code>GET [[base]/AllergyIntolerance?patient=[id]&date=[date]</code></td>
</tr>
<tr>
<td>SHOULD</td>
<td>patient+last-date</td>
<td><code>GET [[base]/AllergyIntolerance?patient=[id]&last-date=[date]</code></td>
</tr>
<tr>
<td>SHOULD</td>
<td>patient+clinical-status</td>
<td><code>GET [[base]/AllergyIntolerance?patient=[id]&clinical-status=[status]</code></td>
</tr>
</table>

---

<h4 id="allergyintolerance-_id"><code>AllergyIntolerance _id</code></h4>
The Provider SHOULD support search by the logical identifier of the AllergyIntolerance resource:

```
GET [base]/AllergyIntolerance?_id=[id]
```

---

<h4 id="allergyintolerance-patient"><code>AllergyIntolerance patient</code></h4>
The Provider SHALL support search by patient:

```
GET [base]/AllergyIntolerance?patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/AllergyIntolerance?patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing AllergyIntolerance resources that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd`.

---

<h4 id="allergyintolerance-clinical-status"><code>AllergyIntolerance clinical-status</code></h4>
The Provider SHALL support search by clinical status:

```
GET [base]/AllergyIntolerance?clinical-status=[status]&patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/AllergyIntolerance?clinical-status=active&patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing AllergyIntolerance resources with clinicalStatus `active` that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd` .

---

<h4 id="allergyintolerance-date"><code>AllergyIntolerance date</code></h4>
The Provider SHOULD support search by recorded date:

```
GET [base]/AllergyIntolerance?date=[date]&patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/AllergyIntolerance?date=ge2018-01-01&patient=b88f0099-5213-4502-a49d-cc3887027bdd` the Provider would respond with a Bundle containing AllergyIntolerance resources recorded on or after `2018-01-01` that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd`.

Where a Provider supports search by date, the Provider SHOULD support:
- partial dates *e.g.* `date=1970-09`
- the `eq`, `ge`, `le` operators *e.g.* `date=ge1970-09-01`
- multiple date parameters *e.g.* `date=ge1970-09-01&date=le1970-10-01`

---

<h4 id="allergyintolerance-last-date"><code>AllergyIntolerance last-date</code></h4>
The Provider SHOULD support search by last occurrence:

```
GET [base]/AllergyIntolerance?last-date=[date]&patient=[id]
```

For example, when a Consumer sends the request `GET https://fhir.example-provider.nhs.uk/AllergyIntolerance?last-date=ge2018-01-01&patient=b88f0099-5213-4502-a49d-cc3887027bdd`
the Provider would respond with a Bundle containing AllergyIntolerance resources last occurring on or after `2018-01-01` that reference patient `b88f0099-5213-4502-a49d-cc3887027bdd`.

Where a Provider supports search by date, the Provider SHOULD support partial dates, the `eq`, `ge`, `le` operators and multiple date parameters. See above for details.