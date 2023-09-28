## {{page-title}}

*Note: Guidance replicated from that published for GPConnect*

It is recognised that allergy/intolerance information may not be fully interoperable between participating systems. Where allergy/intolerance information is not fully understood by a receiving system then it is the responsibility of the **consumer** to mitigate any risks arising and make related workflows as safe as possible.

Where allergy/intolerance information is integrated into the consuming system patient record then allergy/intolerance information **MUST** be degraded where the coded allergy/intolerance information is not fully understood by the consumer. In the context of drug allergies, an allergy/intolerance is only understood if the coded causative agent triggers equivalent prescribing decision support to that triggered on the producing system.

Degradation can be handled by coding the record entries resulting from the processed allergy as a [196461000000101 | transfer-degraded drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196461000000101&edition=uk-edition) or a [196471000000108 | transfer-degraded non-drug allergy (record artifact)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=196471000000108&edition=uk-edition) preserving the original term for the received code as text.



XML
``` xml
<code>
  <coding>
    <system value="http://snomed.info/sct"/>
    <code>196471000000108</code>
    <display>transfer-degraded non-drug allergy(record artifact)</display>
  </coding>
  <text>Latex</text>
</code>
 ```   



JSON
``` json
{
"code": {
        "coding":  [
            {
                "system": "http://snomed.info/sct",
                "code": "196471000000108",
                "display": "transfer-degraded non-drug allergy(record artifact)"
            }
        ],
        "text": "Latex"
    }
    
```


Where the processing of an `AllergyIntolerance` resource results in degradation, or the FHIR resource is already coded as a degrade drug allergy code, then the consuming system **MUST** prevent prescribing while degraded drug allergies are present in the patient record and **MUST** inform users attempting prescribing actions that prescribing is being prevented due to the presence of degraded drug allergies.

In other contexts, task-based workflows have been utilised to assist users on consuming systems to process degraded drug allergies by re-coding them to concepts understood by the consuming system.

When considering the implementation of interoperability for use cases involving allergy/intolerance, suppliers **MUST** perform an appropriate clinical safety assessment and obtain the necessary clinical safety approvals for the processing performed by their system.

---