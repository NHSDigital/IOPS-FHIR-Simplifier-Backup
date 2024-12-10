## Element: `{{page-title}}`

Additional dosage instructions that can be either SNOMED-CT coded terms or free-text instructions.

Where suitable SNOMED-CT coded terms exist, use them instead of free-text instructions. See the SNOMED-CT hierarchy descendants of [419492006 Additional dosage instructions (qualifier value)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=419492006&edition=uk-edition). These terms are also available from the example [FHIR valueset binding](http://hl7.org/fhir/stu3/valueset-additional-instruction-codes.html).

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> Where no code exists, <code>additionalInstructions</code> can be conveyed as free-text; however, if free-text is used rather than a SNOMED-CT coded term, the `MedicationRequest` cannot be computable, and requires human intervention in the case of conditional or contradictory instructions.
</div>

**Coded instruction**
```xml
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="419529008"/> 
        <display value="Dissolved under the tongue "/> 
    </coding>
</additionalInstruction>
```

**Multiple coded instructions**

```xml
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="417995008"/> 
        <display value="Dissolve or mix with water before taking"/> 
    </coding>
</additionalInstruction>
<additionalInstruction>
    <coding> 
        <system value="http://snomed.info/sct"/> 
        <code value="417980006"/> 
        <display value="Contains aspirin"/> 
    </coding>
</additionalInstruction>
```

**Free-text instruction**

```xml
<additionalInstruction>
    <text value="with dialysis"/>
</additionalInstruction>
```

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> Where a dosage is expressed as a number of <code>sequence</code> elements and the same <code>additionalInstructions</code> applies to each <code>sequence</code>, then repeat the <code>additionalInstructions</code> within each <code>sequence</code>.
</div>

For example:

```xml
<dosageInstruction>
    <sequence value="1" />
    <text value="1 tablet - once a day - for 1 week - take with food" />
    <timing>
        <repeat>
            <boundsDuration>
                <value value="1" />
                <unit value="week" />
                <system value="http://unitsofmeasure.org" />
                <code value="wk" />
            </boundsDuration>
            <frequency value="1" />
            <period value="1" />
            <periodUnit value="d" />
        </repeat>
    </timing>
    <doseAndRate>
        <doseQuantity>
            <value value="1" />
            <unit value="tablet" />
            <system value="http://snomed.info/sct" />
            <code value="428673006" />
        </doseQuantity>
    </doseAndRate>
    <additionalInstruction>
        <text value="take with food"/>
    </additionalInstruction>
</dosageInstruction>
<dosageInstruction>
    <sequence value="2" />
    <text value="2 tablets - twice a day - take with food" />
    <timing>
        <repeat>
            <frequency value="2" />
            <period value="1" />
            <periodUnit value="d" />
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
        <text value="take with food"/>
    </additionalInstruction>
</dosageInstruction>
```

### `additionalInstruction` / `when` overlap

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> The value-sets for <code>Timing.when</code> and <code>Dosage.additionalInstruction</code> do contain some overlapping values.
</div>

For example, they can both describe “with or after food”. 

In such cases, use `Timing.when` instead of a coded `Dosage.additionalInstruction`.


### continue / stop instructions

There may be the need for a clinician to give explicit instructions to either stop or continue taking medication. This could be applicable for discharge medication where one medicine may be for short term pain relief and should be stopped after the prescribed quantity has been taken, while another medicine must be continued until further notice. 

The patient’s GP would be informed of this as part of the discharge letter but having these instructions explicitly coded provides a more robust solution.

Three SNOMED-CT codes exist that can be used for this purpose.

- “Then stop” (SNOMED concept identifier = [422327006](https://termbrowser.nhs.uk/?perspective=full&conceptId1=422327006&edition=uk-edition))
- “Then discontinue” (SNOMED concept identifier = [421484000](https://termbrowser.nhs.uk/?perspective=full&conceptId1=421484000&edition=uk-edition))
- “Do not stop taking this medicine except on your doctor’s advice” (SNOMED concept identifier = [419444006](https://termbrowser.nhs.uk/?perspective=full&conceptId1=419444006&edition=uk-edition))

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note:</strong> It is recognised that such coded terms are akin to timing instructions so may be more logically containing within the various <code>Dosage.timing</code> structures. These do not currently support coded concept terms. Implementation experience will provide evidence to support any future change to the underlying FHIR specification.
</div>


### as directed

The use of a dosage instruction akin to “as directed” should be avoided wherever possible; however, if required then this can be SNOMED coded using [421769005 Follow directions (qualifier value)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=421769005&edition=uk-edition) or conveyed as text as a patient instruction.

---