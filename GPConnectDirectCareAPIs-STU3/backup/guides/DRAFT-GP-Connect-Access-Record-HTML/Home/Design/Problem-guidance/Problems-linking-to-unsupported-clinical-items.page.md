## {{page-title}}

Depending on the GP Connect version supported by the provider system, it can be possible for the problem to link to a clinical item that the provider system is not yet able to export with GP Connect. For example, if the problem contains a link to a referral record but the provider system does not yet support exporting referrals.

Where a provider system is not able to export a linked clinical item, it will create a reference entry with the:

`Condition.extension:relatedClinicalContent.valueReference.display` should have the value: "[Clinical area] items are not supported by the provider system."

Where [Clinical area] identifies the type of the clinical item that is not supported.

The example below shows references to two items, one for an observation and another for referrals that aren’t supported by the provider system:

```xml
<extension>
    <url value="http://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1" />
    <valueReference value="observation-7634572634" />
</extension>
<extension>
    <url value="http://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-RelatedClinicalContent-1" />
    <valueReference>
        <display value="Referral items are not supported by the provider system" />
    </valueReference>
</extension>
```