---
topic: ReleaseNotes
---
## Release Notes

### v0.1.5 (TBC)

* Updated the examples in the {{pagelink:R4Examples}} to correct various validation errors.
* Added the following new <code>Observation</code> examples:
    * TBC	
* Updated the {{pagelink:DesignOverview}} page to include a description of how various types of test result should be represented.
* Included changes to the pathology related profiles that were made as part of the [HL7 UK STU2 Ballot](https://confluence.hl7.org/pages/viewpage.action?pageId=175611042) process.

### v0.1.4 (29/12/2023)

* Removed the content from the {{pagelink:Transport}} and {{pagelink:AcknowledgementFramework}} pages (under the Design menu bar item). Awaiting confirmation of what data exchange and acknowledgement approach will be adopted for FHIR UK Core R4 based interactions between pathology laboratory systems and GP EPR systems.
* Added the following new <code>Bundle</code> examples:
    * {{pagelink:R4BundleExampleLipidsandHbA1cRequest}}
    * {{pagelink:R4BundleExampleLipidsandHbA1cReport}}
* Added an overview of the Implementation Guide Structure to the {{pagelink:Home}} page.
* Updated the {{pagelink:Glossary}}.

### v0.1.3 (08/12/2023)

* Added a new {{pagelink:Background}} page (under the Design menu bar item). This incorporates content from the previous version of the {{pagelink:DesignOverview}} page, with additional material describing GP practice pathology data flows. 
* Updated the {{pagelink:DesignOverview}} page (under the Design menu bar item). This now contains additional content, including a summary of the FHIR design approach that has been adopted as part of this implementation guide and the use of SNOMED CT.
* Updated references to the PaLM and PBCL SNOMED CT reference sets throughout the implementation guide.

### v0.1.2 (30/10/2023)

* Removed all FHIR STU3 related content, in line with the recent [announcement](https://simplifier.net/organization/hl7uk/news/151) from the NHS England Interoperability Standards Team that CareConnect has been deprecated and all development on the CareConnect FHIR STU3 assets has ceased.
* Updated the examples in the {{pagelink:R4Examples}} to include a populated <code>category</code> element for <code>UKCore-DiagnosticReport-Lab</code>, <code>UKCore-Observation-LabGroup</code> and <code>UKCore-Observation-Lab</code>.
* Updated the structure of the implementation guide to align with the latest NHS England FHIR Implementation Guide template. 

### v0.1.1 (04/10/2023)

* Updated to incorporate a new set of laboratory specific FHIR R4 derived profiles, as defined in the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current) (currently STU2):
    * <code>UKCore-DiagnosticReport-Lab</code>
    * <code>UKCore-Observation-LabGroup</code>
    * <code>UKCore-Observation-Lab</code>
    * <code>UKCore-ServiceRequest-Lab</code> 
    * Note: <code>UKCore-Specimen</code> does not have a pathology specific derived profile.
* Updated to use the NHS England FHIR Implementation Guide template. 

### v0.1.0 (17/04/2023)

* Initial draft.