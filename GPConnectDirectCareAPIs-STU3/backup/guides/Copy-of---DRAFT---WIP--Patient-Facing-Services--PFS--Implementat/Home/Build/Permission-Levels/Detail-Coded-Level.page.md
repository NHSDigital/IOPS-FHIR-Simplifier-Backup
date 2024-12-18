## {{page-title}}

This access level is everything from Summary + All read/clinical codes, Immunisations, Health conditions, Test results, Consultations, Referrals.

That means, any free text elements and documents must not be returned. 

In order to ensure no free text from consultations are not returned, the provider needs to ensure where text is entered freely into a consultation without being associated with a clinical code is not returned to a patient of this access level.

In the clinical facing Access Record these are returned in an `Observation` with the SNOMED code 37331000000100 Comment note. At this access level, providers must not return an `Observation` with the Comment note code.

Providers also must ensure that `specimen.note` is not returned at this level.

To ensure no documents are returned, the provider must reject any requests to the document endpoint where the patient does not have sufficient access.

