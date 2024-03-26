## {{page-title}}

Degradation is a process used in clinical systems interoperability for dealing with codes that
are not understood by receiving systems. When codes are degraded the original text entered
by a user is then associated with an appropriate degrade code. For example, a drug allergy
code that is not understood will be associated with a code for ‘Degraded drug allergy’.

### Why and how does it happen?

When clinical codes move between systems sometimes the receiving system may not
understand all the clinical codes that it was sent. This can be for a number of reasons:
- The receiving system may use a different terminology than the sending system. An
example of a place in which this happens is in primary care where TPP SystmOne
uses Clinical Terms Version 3 and EMIS Web uses Read version 2.
- Clinical systems may be using different releases of the same terminology. In the UK,
terminologies are updated regularly, usually 6 monthly. When they are updated new
codes are added and old codes deprecated. If one system updates before another
then for a period it may contain new codes that systems using an older version do not
understand.
- SNOMED CT has an extension mechanism that allows SNOMED CT to be
customized usually be adding additional concepts and descriptions. So sending
systems may have added content that is not available on the receiving system. See
examples 6 and 7 on how messages are populated with extension data.

There may be many other reasons that codes are not understood between systems but the
above are some of the most common reasons. Here they are intended to illustrate that
degrades happen but are not intended to be an exhaustive list.

### Why do we need a process to deal with it?

Where codes are not understood by clinical systems, having a degrade process enables us
to improve interoperability and related functionality. Having appropriate degrade codes
enables us to retain the structure and semantics. For example, degraded allergies appear in
allergies view, medication degrades appear in medication module.
Some examples of how this can work are:
- Where allergies are degraded, associating the item that was not understood with an
allergy degrade code that the clinical system understands can enable it to trigger (for
example) additional prescribing safety decision support systems and workflows
- Where medication codes are not understood and the data item is associated with a
medication degrade code, the information can be displayed alongside all other
medications in the clinical system.

### What do degrades look like?

Where items are degraded, how they appear can vary depending on how a clinical system
chooses to display them to a user. In many cases, depending on whether the actual code is
displayed to the user, the degrade may appear to be similar to any code natively added in a
system.

When they are then exported into a FHIR resource they will be exported as a degrade code
with the text originally entered by the user in the code.text element.

### FHIR message examples

Example of a degraded medication:
```json
{
  "code": {
    "coding": [
      {
        "display": "Transfer-degraded medication entry",
        "code": "196421000000109",
        "system": "http://snomed.info/sct"
      }
    ],
    "text": "Aspirin 75mg dispersible tablet"
  }
}
```

Example of a degraded drug allergy:
```json
{
  "code": {
    "coding": [
      {
        "display": "Transfer-degraded drug allergy",
        "code": "196461000000101",
        "system": "http://snomed.info/sct"
      }
    ],
    "text": "Amoxicillin 250mg capsules"
  }
}
```

