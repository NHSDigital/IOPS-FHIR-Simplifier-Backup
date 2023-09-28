## `dosage`


Preferable as a structured dosage aligned to the <a href="https://simplifier.net/guide/ukcoreimplementationguideformedicines/elementdosage?version=current">FHIR Dose Syntax Guidance</a> but as a minimum, `dosage.text`.

Where a structured dosage is provided, populate `dosage.text` with a human readable dosage string that is clinically equivilant to the coded dosage instruction. This is for interoperability with consuming systems that do not yet support fully structured dosing instructions.

---
