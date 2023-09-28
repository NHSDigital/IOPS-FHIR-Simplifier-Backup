## `route`

The path by which the vaccine product is taken into the body.

A SNOMED concept ID value from either of the following should be used:
<br/>
UK “ePrescribing route of administration simple reference set (foundation metadata concept)” (999000051000001100)
<br/>
Or:
<br/>
UK published reference set “Vaccine route of administration simple reference set” (115231000001104).


XML
```xml
<route>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="78421000"/>
        <display value="Intramuscular route (qualifier value)"/>
    </coding>
</route>    
```



JSON
```json
{
 "route": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "78421000",
                "display": "Intramuscular route (qualifier value)"
            }
        ]
    },
}
```

---
