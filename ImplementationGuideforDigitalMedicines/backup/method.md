## Element: `{{page-title}}`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><strong>Note:</strong> Guidance on method under review to consider including use cases for when a free-text method instruction may be required.</div>

The [999000041000001103 ePrescribing method simple reference set (foundation metadata concept)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000041000001103&edition=uk-edition) reference set collates the commonly used terms for `method` for use in the United Kingdom. Additional terms can be requested to be added to this reference set.

For example:

```xml
<!-- Method -->
<method>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="129326001"/>
        <display value="Injection"/>
    </coding>
</method>
```
and
```xml
<!-- Method -->
<method>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="71791000001107"/>
        <display value="Nebulise - method of drug administration (qualifier value)"/>
    </coding>
</method>
```

Whilst a [FHIR value-set for method](http://hl7.org/fhir/valueset-administration-method-codes.html) does exist, together with two separate hierarchies within SNOMED-CT ([Dose form administration method](https://termbrowser.nhs.uk/?perspective=full&conceptId1=736665006&edition=uk-edition) and [Dosing instruction fragment](https://termbrowser.nhs.uk/?perspective=full&conceptId1=422096002&edition=uk-edition)), it is recommended to use the ePrescribing reference set in the first instance.

---