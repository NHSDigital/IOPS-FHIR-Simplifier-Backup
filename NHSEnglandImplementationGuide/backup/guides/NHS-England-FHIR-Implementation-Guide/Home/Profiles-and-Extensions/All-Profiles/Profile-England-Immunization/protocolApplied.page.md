## `protocolApplied`

<b>Definition</b><br>
`doseNumberPositiveInt` Nominal position in a series of vaccines,
N.B. This field will not always be reliable, therefore for Covid vaccinations, the vaccination procedure code or situation code should be used as that includes the dose number

It is recommended for international/EU interoperability `targetDisease` is populated. The SNOMED CT concept should be from [EU COVID-19 Diseases]() or <a href="http://www.fhir.org/guides/stats/valueset-hl7.fhir.uv.ips-targetdiseases-uv-ips.html" target="_blank">Vaccine Target Diseases (GPS) - IPS</a>

<table>
<thead>
<th data-no-sort width="20%">
Disease
</th>
<th data-no-sort width="25%">
UK SNOMED self
</th>
</thead>
<tr>
<td>
COVID-19
</td>
<td>
<a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=840539006" target="_blank">840539006</a>
</td>
</tr>
<tr>
<td>
Others
</td>
<td>
See <a href="http://www.fhir.org/guides/stats/valueset-hl7.fhir.uv.ips-targetdiseases-uv-ips.html" target="_blank">Vaccine Target Diseases (GPS) - IPS</a>
</td>
</tr>
</table>