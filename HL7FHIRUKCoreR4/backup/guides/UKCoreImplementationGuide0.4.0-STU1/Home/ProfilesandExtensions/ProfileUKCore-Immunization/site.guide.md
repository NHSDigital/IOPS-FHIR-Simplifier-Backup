## `site`

Body site where vaccine was administered.

Body site vaccine was administered into. A SNOMED Concept ID value from UK published reference set “Vaccine body site of administration simple reference set” (1127941000000100) should be used {{pagelink:ValueSetUKCore-BodySite}}.


XML

``` xml
<site>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="368208006"/>
        <display value="Left upper arm structure (body structure)"/>
    </coding>
 </site>   
```


JSON
```json

{
    "site": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "368208006",
                "display": "Left upper arm structure (body structure)"
            }
        ]
    },
}
```

---