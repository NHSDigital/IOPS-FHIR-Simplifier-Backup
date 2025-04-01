## {{page-title}}
Where a supplier is using the dm+d codes generated from the xml resources in TRUD which
does not contain any data at the descriptionId level then we would not expect the
descriptionId extension to be populated.

Where the descriptionId is available then this SHALL be included. 

The example below demonstrates how a dm+d code should be sent where there is no
descriptionId available.

```xml
<code>
    <coding>
        <code value="323509004"/>
        <display value="Amoxicillin 250mg capsules"/>
        <system value="http://snomed.info/sct"/>
        <userSelected value="true"/>
    </coding>
</code>
```

```json
{
    "code": {
        "coding": [{
        "code": "323509004",
        "display": "Amoxicillin 250mg capsules",
        "system": "http://snomed.info/sct",
        "userSelected": "true"
        }]
    }
}
```