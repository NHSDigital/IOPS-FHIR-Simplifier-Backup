## Element: `{{page-title}}`

The [999000041000001103 ePrescribing method simple reference set (foundation metadata concept)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=999000041000001103&edition=uk-edition) reference set collates the commonly used terms for `method` for use in the United Kingdom.

Whilst a [FHIR value-set for method](http://hl7.org/fhir/valueset-administration-method-codes.html) does exist, together with two separate hierarchies within SNOMED-CT ([Dose form administration method](https://termbrowser.nhs.uk/?perspective=full&conceptId1=736665006&edition=uk-edition) and [Dosing instruction fragment](https://termbrowser.nhs.uk/?perspective=full&conceptId1=422096002&edition=uk-edition)), it is recommended to use the ePrescribing reference set in the first instance.

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

### Use of synonyms

In most instances it is anticipated that the UK Preferred term should be the term applied to SNOMED CT concepts However for some cases, for example the anatomically correct SNOMED-CT term may not be easily understood by the patient or clinician, the use of a synonym may be preferred. 

Guidance for using terms that are not preferred terms is available within the published document [Guidance on the use of CodeableConcept.](https://developer.nhs.uk/apis/gpconnect-1-2-0/pages/accessrecord_structured/guidance-on-the-population-of-codeableconcept.pdf)

---