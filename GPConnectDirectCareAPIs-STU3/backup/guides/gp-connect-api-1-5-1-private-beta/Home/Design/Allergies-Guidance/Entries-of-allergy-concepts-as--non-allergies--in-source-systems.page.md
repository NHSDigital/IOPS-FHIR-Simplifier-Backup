## {{page-title}}

Participating systems have a variety of record types/structures that explicitly represent allergy and intolerance structures within the patient record. These structures are explicitly selected by users to record allergy and intolerance information in the record or may be automatically triggered by attempts to enter allergy codes/concepts into the patient record. As these structures readily identify the presence of allergy/intolerance concepts in the record, they are readily identifiable and mappable to the `AllergyIntolerance` request when processing FHIR requests.

It is also possible in some cases to bypass these data entry features and enter allergy codes/concepts as ordinary coded record entries in the patient record. Such entries may appear in the source system as ordinary journal entries and may not appear as allergies/intolerances in patient summaries or allergy/intolerance lists in provider systems.

_If it is possible on the provider system to record allergy concepts as non-allergies in the patient record, then the system **MUST** express these record entries as FHIR AllergyIntolerance resources when queried._
