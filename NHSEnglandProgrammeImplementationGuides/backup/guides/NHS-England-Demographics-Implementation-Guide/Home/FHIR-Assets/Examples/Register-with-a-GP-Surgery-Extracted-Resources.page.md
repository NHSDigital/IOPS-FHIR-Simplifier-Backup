---
subject: GPReg-QuestionnaireResponse-Extracted-Example
---

## {{page-title}}

Certain resources can be extracted from the QuestionnaireResponse submitted to the Register with a GP Surgery. This includes the Patient resource, for submission to PDS as well as certain patient reported Observations, such as height and weight.

The extracted resources have been represented using a Transaction Bundle, which could also include the QuestionnaireResponse itself. Equally, the extracted resources could also be held or sent individually, pending design decisions by the Register with a GP Surgery Programme.
 
These observations have been extracted using the question SNOMED CT codes and codes included in answer ValueSets.

Determination of which questions can be extracted into observations, as well as where this extraction should occur, e.g. by the central Register with a GP Surgery service or by receiving GP systems, is still under review.

{{page:Home/Templates/Example-Template.page.md}}