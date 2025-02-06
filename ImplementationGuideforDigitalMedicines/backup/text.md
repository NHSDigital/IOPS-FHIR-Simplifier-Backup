## Element: `{{page-title}}`

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<strong>IMPORTANT:</strong> This guidance differs from the international FHIR specification. The FHIR standard is ambiguous with contradictory statements for what may or may not be contained within the <code>text</code> element. 
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: We recommend <code>text</code> is populated with a textual representation of the complete dosage instruction, in terms understood by a healthcare professional, excluding;<br/>
    <li>Name or description of the medication (Note 1)</li>
    <li>Problem or condition to which the medicine relates (Note 2)</li>
    <li>Any <code>patientInstruction</code> string (Note 3)</li>
    <br/>
This approach allows the <code>text</code> to be safely used by clinical systems that cannot (yet) consume the complete FHIR Dosage structure. All dosing instructions within <code>text</code> should also be contained within the relevant structured elements of the FHIR Dosage to allow the clinical system to consume the FHIR Dosage without requiring the human user to interpret the contents of <code>text</code>.
</div>

**Note 1**: The name or description of the medication is conveyed as a `codeableConcept` or referenced `Medication` resource in the resource that contains the Dosage structure.

**Note 2**: The reason for medication is conveyed within the `reasonCode` or `reasonReference` within the `MedicationRequest` and `MedicationStatement` resources.

**Note 3**: The `patientInstruction` element contains equivalent information to `text` but in terms that are understood by the patient or consumer so should not be repeated within `text`.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Exception: EPS FHIR Facade Implementation</strong><br/>
An exception to note 2 above relates to the current implementation of the <a href="https://digital.nhs.uk/developer/api-catalogue/electronic-prescription-service-fhir"/>Electronic Prescription Service - FHIR API</a>. The <code>text</code> may be appended with the reason for the medication (indication). The current implementation of the EPS converts the FHIR payload to HL7v3 for backwards compatibility. Wthin the HL7v3 data model, there is nowhere to hold the indication other than as an appendment to the free-text dosage instruction.
</div>

The textual representation **must** align with what the clinical user selects or sees on-screen. A textual and clinical equivalent of every element within the Dosage structure, excluding `text`, must be contained within `text`, with the exception of any [patientInstruction](ElementDosage?#patientInstruction) string.

This approach allows clinically safe dosage interoperability between systems that do and do not support the full Dosage structure. A consumer system that can only handle a dosage text string will consume `text` and ignore all other elements of the Dosage structure. A provider system that can only handle a dosage text string will only populate the `text` element of the Dosage structure.

The approach we recommend allows a fully FHIR-compliant consumer system to process all elements of Dosage **excluding** `text`. A system that only supports text-based dosage instructions will process **only** `text` for clinical users or `patientInstruction` for the patient user. Both implementations will consume an equivalent dosage instruction, albiet one as text and one that is machine readable.

### Implementation Example A

A provider system allows the user to pick an order sentence, e.g. “Two tablet(s), two times a day, with food. Please do not chew the tablets”. This string goes into `text` and in the background, the provider system constructs the coded Dosage structure.

```xml
<dosageInstruction>
     <text value="Two tablet(s), two times a day, with food. Please do not chew the tablets" />
     <timing>
          <repeat>
              <frequency value="2" />
              <period value="1" />
              <periodUnit value="d" />
              <when value="C"/>
          </repeat>
     </timing>
     <doseAndRate>
          <doseQuantity>
              <value value="2" />
              <unit value="tablet" />
              <system value="http://snomed.info/sct" />
              <code value="428673006" />
          </doseQuantity>
     </doseAndRate>
     <additionalInstruction>
         <text value=”Please do not chew the tablets” />
     </additionalInstruction>
</dosageInstruction>
```

### Implementation Example B

A provider system allows the user to construct a dosage instruction using various user interface components. The system translatesAd  the coded information into a text string for `text`. Refer to our [translation algorithm](DosetoTextTranslation) for guidance for such a translation. In the background, the provider system constructs the coded Dosage structure.

```xml
<dosageInstruction>
     <text value="2 tablets - twice a day – at a meal - Please do not chew the tablets" />
     <timing>
          <repeat>
              <frequency value="2" />
              <period value="1" />
              <periodUnit value="d" />
              <when value="C"/>
          </repeat>
     </timing>
     <doseAndRate>
          <doseQuantity>
              <value value="2" />
              <unit value="tablet" />
              <system value="http://snomed.info/sct" />
              <code value="428673006" />
          </doseQuantity>
     </doseAndRate>
     <additionalInstruction>
         <text value=”Please do not chew the tablets” />
     </additionalInstruction>
</dosageInstruction>
```

### Fully unstructured dosing instructions

Where no aspect of the dosing instruction can be coded, use the `text` to convey the text-based dosing instruction.

```xml
<dosageInstruction>
     <text value="Add half to 2 capfuls to bath water, or apply to wet skin and rinse" />
</dosageInstruction> 
```

<!--
### Implementation Example C - If the international FHIR specification is followed - to highlight the clinical risk

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> This example highlights what we want to avoid within a UK implementation.
</div>

In this example, the `Dosage.text` just contains the non-coded instruction of “Please do not chew the tablets”, as suggested within the FHIR specification. If this dosage instruction was consumed by a system that does not support the coded elements then all that system would process is the fragment of "Please do not chew the tablets".

```xml
<dosageInstruction>
     <text value="Please do not chew the tablets" />
     <timing>
          <repeat>
              <frequency value="2" />
              <period value="1" />
              <periodUnit value="d" />
              <when value="C"/>
          </repeat>
     </timing>
     <doseAndRate>
          <doseQuantity>
              <value value="2" />
              <unit value="tablet" />
              <system value="http://snomed.info/sct" />
              <code value="428673006" />
          </doseQuantity>
     </doseAndRate>
</dosageInstruction>
```

### Implementation Example D - If the international FHIR specification is followed - to highlight the clinical risk

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> This example highlights what we want to avoid within a UK implementation.
</div>

In this example, provider system has followed this guidance to include the dosage as selected by the prescriber within `Dosage.text` but has ADDITIONALLY followed the FHIR specification and has appended the uncoded part of the instruction to the text. This has resulted in duplication of the instruction "Please do not chew the tablets", which could be confusing.

```xml
<dosageInstruction>
     <text value="Two tablet(s), two times a day, with food. Please do not chew the tablets. Please do not chew the tablets." />
     <timing>
          <repeat>
              <frequency value="2" />
              <period value="1" />
              <periodUnit value="d" />
              <when value="C"/>
          </repeat>
     </timing>
     <doseAndRate>
          <doseQuantity>
              <value value="2" />
              <unit value="tablet" />
              <system value="http://snomed.info/sct" />
              <code value="428673006" />
          </doseQuantity>
     </doseAndRate>
</dosageInstruction>
```
-->
---