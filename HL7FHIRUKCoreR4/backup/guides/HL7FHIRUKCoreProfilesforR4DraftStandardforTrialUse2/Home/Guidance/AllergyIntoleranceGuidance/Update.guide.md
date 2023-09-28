## {{page-title}}

Out of scope for this version of UK Core.

Refer to {{pagelink:Profile-AllergyIntolerance--clinicalstatus-eeda043a-89b7-4c4e-8f82-4ba921c43947}} for related guidance.


<!--
When the `clinicalStatus` changes, create a new instance of the resource. This preserves an audit trail for when the allergy was first recorded as *active* and when the clinical status changes. This is because the resource does not have an element akin to a 'last updated' timestamp.

When allergy clinical data is changed, more likely when corrected, e.g. if the wrong SNOMED code has been used within `code` then update the instance of the resource. In a RESTful implementation use a PUT or PATCH operation. If implemented within a FHIR Message or FHIR Document then post an updated version of the resource to the original recipient(s).

When a new occurrence of a `reaction` is recorded for an existing allergy then;
  - If the instance is mastered by the provider system then update the instance, adding an additional `reaction` element. Consumer systems will pick up this change via an event or when next queried.
  - If the instance is mastered by a different system and cannot be updated by the provider system, then create a new instance of the resource. Consumer systems will pick up the new instance and can link it a previous instance by `code`.-->

---
