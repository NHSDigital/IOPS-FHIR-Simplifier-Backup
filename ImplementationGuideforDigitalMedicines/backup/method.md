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

### Use of a free-text method

The `method` element with the `Dosage` structure can be populated with a free-text instruction. However, where a suitable coded SNOMED term exists, the coded term should always be used to allow the instruction to be machine-readable.

Scenarios exist where a suitable coded SNOMED term for `method` does not exist. For example, some paediatric-suitable methods of medication administration and where complex methods are required.

Example: **Nystatin 100,000units/ml oral suspension sugar free** for paediatric use.

```xml
<method>
   <text value="Rub onto the inside of the mouth and gums"/>
</method>
```

Example: **Tiotropium bromide 18microgram inhalation powder capsules with device**

```xml
<method>
   <text value="Inhale the contents"/>
</method>
```

Example: **Creon capsules**

```xml
<method>
   <text value="Swallowed whole or for ease of administration may be opened and the granules taken with acidic fluid or soft food but without chewing"/>
</method>
```

---