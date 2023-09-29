## {{page-title}}

The `meta.security` element within the `CareConnect-GPC-Encounter-1` FHIR profile can be used to pass this information across with a simple code `NOPAT` which will inform the GP that the information received **SHOULD NOT** be disclosed anyone else without the provider or patient authorisation.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This specification requests that the non-disclosure code be used where relevant for the <b>entire Encounter (and all information contained)</b> rather than individual FHIR profiles to avoid complexity.
</div>


```xml
<Encounter xmlns="http://hl7.org/fhir">
    <meta>
        <security>
            <system value="http://hl7.org/fhir/v3/ActCode" />
            <code value="NOPAT" />
            <display value="no disclosure to patient, family or caregivers without attending provider's authorization" />
        </security>
    </meta>
    ...
</Encounter>
```