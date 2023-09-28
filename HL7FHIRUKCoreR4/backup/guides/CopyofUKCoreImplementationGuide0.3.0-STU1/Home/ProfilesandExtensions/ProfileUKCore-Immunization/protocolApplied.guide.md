## `protocolApplied`
The protocol (set of recommendations) being followed by the provider who administered the dose.
 
`doseNumberPositiveInt` Nominal position in a series of vaccines,
N.B. This field will not always be reliable, therefore for Covid vaccinations, the vaccination procedure code or situation code should be used as that includes the dose number.


JSON
```json

{"protocolApplied":  [
        {
            "doseNumberPositiveInt": 1
        }
    ]
}
```

<br/>

It is recommended for international/EU interoperability `targetDisease` is populated. The SNOMED CT concept should be from [EU COVID-19 Diseases](https://build.fhir.org/ig/hl7-eu/dgc/ValueSet-covid-19-diseases.html) or [Vaccine Target Diseases (GPS) - IPS](http://hl7.org/fhir/uv/ips/ValueSet/targetDiseases-gps-uv-ips).

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
See <a href="http://hl7.org/fhir/uv/ips/ValueSet/targetDiseases-gps-uv-ips" target="_blank">Vaccine Target Diseases (GPS) - IPS</a>
</td>
</tr>
</table>

<br/>

JSON
```json

  "protocolApplied": [
    {
        "targetDisease": [
            {
                "coding": [
                    {
                        "system": "http://snomed.info/sct",
                        "code": "840539006",
                        "display": "COVID-19"
                    }
                ]
            }
        ],
        "doseNumberPositiveInt": 1
    }
]

```


<br>

<a name="SNOMEDCT"></a>
### SNOMED CT codes relating to COVID-19 Vaccination <a href="#SNOMEDCT" title="link to here" class="self-link"><i class="bi-link"></i></a>

A complete list of SNOMED CT Codes relating to this profile can be found here [SNOMED CT codes relating to COVID-19 Vaccination](https://hscic.kahootz.com/gf2.ti/f/762498/92769925.1/DOCX/-/COVID19_Vaccination_Codes_20210211_v1.7.docx).

---