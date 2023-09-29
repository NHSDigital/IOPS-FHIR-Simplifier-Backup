## {{page-title}}

Qualifiers are used to refine the meaning of the coded element of the record.

Each provider system supports a different set of qualifiers; Hhwever, there are three key qualifiers that are common across all provider systems:

- Laterality - for example, a patient record may have a fracture of the left femur
- Severity - for example, a patient record may have a severe asthmatic attack
- Episodicity - for example, this is the patient’s first episode of an asthmatic attack

The provider system will translate all of the qualifiers included with the clinical code into human-readable text and concatenate them with the text entered by the recorder (placing the qualifiers first) and placing in a FHIR `Observation.comment` resource.

---