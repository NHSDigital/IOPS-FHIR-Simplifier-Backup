---
topic: ReleaseNotes
---
## Release Notes

### v0.1.3-Discovery (08/12/2023)

* Added a new Background section (under the Design menu bar item). This incorporates content from the previous version of the Design Overview section, with additional material describing GP practice pathology data flows. 
* Updated the Design Overview section (under the Design menu bar item). This now includes additional content, including a summary of the FHIR design approach that has been adopted as part of this specification and the use of SNOMED CT.
* Updated references to the PaLM and PBCL SNOMED CT reference sets throughout the specification.

### v0.1.2-Discovery (30/10/2023)

* All FHIR STU3 related content removed, in line with the recent [announcement](https://simplifier.net/organization/hl7uk/news/151) from the NHS England Interoperability Standards Team that CareConnect has been deprecated and all development on the CareConnect FHIR STU3 assets has ceased.
* Examples updated to include a populated <code>category</code> element for <code>UKCore-DiagnosticReport-Lab</code>, <code>UKCore-Observation-LabGroup</code> and <code>UKCore-Observation-Lab</code>.
* Specification structure updated to align with the latest NHS England FHIR Implementation Guide template. 

### v0.1.1-Discovery (04/10/2023)

* Updated to incorporate a new set of laboratory specific FHIR R4 derived profiles, as defined in the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current) (currently STU2):
    * <code>UKCore-DiagnosticReport-Lab</code>
    * <code>UKCore-Observation-LabGroup</code>
    * <code>UKCore-Observation-Lab</code>
    * <code>UKCore-ServiceRequest-Lab</code> 
    * Note: <code>UKCore-Specimen</code> does not have a pathology specific derived profile.
* Updated to use the NHS England FHIR Implementation Guide template. 

### v0.1.0-Discovery (17/04/2023)

* Initial draft.