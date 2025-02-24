## {{page-title}}

On some systems it is possible to explicitly mark an allergy or intolerance as resolved or ended, such that it still appears in the patient record but is no longer active and no longer interacts with prescribing decision support. This inactivation may be achieved by explicit entry of an end date or a user action that alters the status of the allergy or intolerance.

Allergies and intolerances which have been explicitly resolved <strong>MUST</strong> only be returned in response to resource queries which have the `includeResolvedAllergies` parameter set to true (see [Retrieve a patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html)).

When the provider is sending resolved allergies, it **MUST** send them in a separate `List` to the active allergies as contained resources in that `List`. Resolved allergies **MUST** be returned as a transfer-degraded drug allergy regardless of the code system used.

If the allergy is SNOMED coded it **MUST** be returned with code `196461000000101`, if the allergy is a Read code it **MUST** be returned with code `9bJ4.`.
The text of the code should read `Resolved '<original term text>' original code <original term code>.` e.g. a resolved allergy to apixaban would have the text `Resolved 'Allergy to apixaban' original code 294505008.` for SNOMED and `Resolved 'Apixaban allergy' original code 1Z431.` for Read codes.

SNOMED example:

```json
{
    "code": {
        "coding": [
            {
                "system": "http://snomed.info/sct",
                "code": "196461000000101",
                "display": "Transfer-degraded drug allergy"
            }
        ],
        "text": "Resolved 'Allergy to apixaban' original code 985271000000102."
    }
}
```

Read code example:

```json
{
    "code": {
        "coding": [
            {
                "system": "http://read.info/readv2",
                "code": "9bJ4.",
                "display": "Transfer-degraded drug allergy"
            }
        ],
        "text": "Resolved 'Apixaban allergy' original code 1Z431."
    }
}
```

The `List` **MUST** have the title 'Ended allergies' and resolved allergy resources **MUST** be assigned a `clinicalStatus` of `resolved`.

A title of 'Allergies and adverse reactions' **MUST** be used for the `List` containing the active `AllergyIntolerance` resources. This list **MUST** be returned when any resolved allergies are returned as part of a consultations or problems query and the primary resolved allergies list **MUST** be used to create any references needed.

Consuming systems <strong>MUST</strong> ensure that resolved allergies are not treated as active - that is, they <strong>MUST NOT</strong> interact with prescribing decision support or be misinterpreted by users as being active.

Where the consuming system does not natively support a resolved allergy concept, suppliers <strong>MUST</strong> seek appropriate clinical safety advice on the handling of the resolved allergy concept.
