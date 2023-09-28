## `vaccineCode`
Vaccine that was administered or was to be administered.

Where status is `completed` this is Mandatory. This indicates vaccine product administered. This should be a SNOMED CT code from {{pagelink:ValueSetUKCoreVaccineCode-index}}
AMPP codes should not be used.

<br/>

XML
```xml
<vaccineCode>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="39114911000001105" />
        <display value="COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)" />
    </coding>
</vaccineCode>
```


JSON
```json
{
"vaccineCode": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "39114911000001105",
                "display": "COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)"
            }
        ]
    },
}
```

<br/>

For EU/international purposes, a vaccination type code can be also be included. The SNOMED CT concept should be from [Vaccines (GPS) - IPS](http://hl7.org/fhir/uv/ips/ValueSet/vaccines-gps-uv-ips) and [EU SNOMED CT Vaccine List (COVID-19)](https://build.fhir.org/ig/hl7-eu/dgc/ValueSet-sct-vaccines-covid-19.html).

XML
```xml
 <vaccineCode>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="39114911000001105" />
            <display value="COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)" />
        </coding>
		<coding>
		     <system value="http://snomed.info/sct" />
            <code value="1119305005" />
            <display value="SARS-CoV-2 antigen vaccine" />
		</coding>
 </vaccineCode> 
```

JSON
```json
{
    "vaccineCode": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "39114911000001105",
                "display": "COVID-19 Vaccine AstraZeneca (ChAdOx1 S [recombinant]) 5x10,000,000,000 viral particles/0.5ml dose solution for injection multidose vials (AstraZeneca)"
            },
            {
                "system": "http://snomed.info/sct",
                "code": "1119305005",
                "display": "SARS-CoV-2 antigen vaccine"
            }
        ]
    },
}
```
---