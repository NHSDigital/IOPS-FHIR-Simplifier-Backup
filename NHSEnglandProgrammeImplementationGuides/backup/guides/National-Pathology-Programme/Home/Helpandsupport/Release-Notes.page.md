---
topic: ReleaseNotes
---
## Release Notes

### v0.1.9 (TBC)

* Added {{pagelink:FHIRAssetsR4CapabilityStatements}} and {{pagelink:FHIRAssetsR4MessageDefinitions}} pages (both under the **FHIR Assets** menu bar item).
* Removed the **Build** menu bar item which contained the 'How to Construct a Pathology Test Request Bundle' and 'How to Construct a Pathology Test Report Bundle' pages. The content from these pages has been combined into a {{pagelink:ContructBundles}} page and added to the **Design** menu bar item.
* Updated the {{pagelink:R4BundleExampleFullBloodCountReport}} example to include `Observation.interpretation` for out of range values.
* Updated the {{pagelink:R4BundleExampleLipidsandHbA1cReport}} example to include the SNOMED CT PaLM concept for serum cholesterol/high density lipoprotein ratio result.
* Updated the GP practice data flows diagram and description in the {{pagelink:Background}} page to include message acknowledgements.
---

### v0.1.8 (30/08/2024)
* Updated the following examples:
    * {{pagelink:R4BundleExampleFullBloodCountRequest}} - changed the data element used to carry clinical context from `ServiceRequest.note` to `ServiceRequest.reasonCode.text`
    * {{pagelink:R4BundleExampleFullBloodCountReport}} - changed the data element used to carry clinical context from `ServiceRequest.note` to `ServiceRequest.reasonCode.text`
    * {{pagelink:R4SnippetsDiagnosticReport}} - added an example for `extension-DiagnosticReport.note`, changed `DiagnosticReport.basedOn.type` from "http://hl7.org/fhir/StructureDefinition/ServiceRequest" to "ServiceRequest" and added an additional instance of `DiagnosticReport.category` to illustrate how a laboratory department name may be carried.
    * {{pagelink:R4SnippetsServiceRequest}} - added examples for `ServiceRequest.identifier.type` to illustrate the use of separate business identifiers for the laboratory service requester and laboratory service provider.
* Added additional guidance to the {{pagelink:DesignOverview}} page and {{pagelink:R4ObservationTestResult}} profile definition regarding the use of text for semi-quantitative and qualitative result types.
* Added an {{pagelink:FHIRAssetsR4Extensions}} page (under the **FHIR Assets** menu bar item).

---

### v0.1.7 (21/06/2024)

* Added two new `Bundle` examples, {{pagelink:R4BundleExampleGTTReportUnstructured}} and {{pagelink:R4BundleExampleUrineMCSReportUnstructured}}, based on the existing structured versions of the same examples. The unstructured versions illustrate how complex reports may be represented using formatted text within a single `Observation`, rather than using a set of structured, coded `Observations`.
* Updated the {{pagelink:R4BundleExampleUrineMCSReportStructured}} example to include a new overarching test group `Observation`, with the following code (taken from the SNOMED CT PaLM procedure reference set):
    * 401324008 | Urinary microscopy, culture and sensitivities
* Added the following new `Bundle` examples:
    * {{pagelink:R4BundleExampleCRPRequest}}
    * {{pagelink:R4BundleExampleCRPReport}}
* Updated `UKCore-Observation-Lab.code` in the examples to use content from the SNOMED CT PBCL reference set alongside equivalent content from the SNOMED CT PaLM content reference set.
* Updated `UKCore-Practitioner.identifier` in the `Bundle` examples with a test GMC code for the requesting practitioner.

---

### v0.1.6 (17/05/2024)

* Updated the Additional Guidance section in each of the {{pagelink:FHIRAssetsR4Profiles}} to align with the content and format used in the [UK Core Implementation Guide (Version 2.0.0 - STU2 Sequence)](https://simplifier.net/guide/uk-core-implementation-guide-stu2?current).
* Added links from each of the {{pagelink:FHIRAssetsR4Profiles}} to the examples in the {{pagelink:R4Examples}}, and also added links to the examples in the UK Core Implementation Guide. Included a new Table view for all examples.
* Added a new {{pagelink:DataMapping}} page (under the **Design** menu bar item). This provides a set of data mappings between the FHIR profiles that are referenced by this implementation guide and the PMIP EDIFACT (NHS003) messaging specification.   
* Updated the {{pagelink:FHIRAssetsR4CodeSystems}} and {{pagelink:FHIRAssetsR4ValueSets}} pages (under the **FHIR Assets** menu bar item).

---

### v0.1.5 (01/03/2024)

* Updated the examples in the {{pagelink:R4Examples}} to correct various validation errors.
* Updated the {{pagelink:DesignOverview}} page to include a description of how various types of test result (i.e. quantitative, semi-quantitative, qualitative, quantitative with an interpretation, narrative) should be represented and added corresponding `Observation` examples to the {{pagelink:R4Examples}}.
* Included changes to the pathology related profiles that were made as part of the [HL7 UK STU2 Ballot](https://confluence.hl7.org/pages/viewpage.action?pageId=175611042) process.

---

### v0.1.4 (29/12/2023)

* Removed the content from the {{pagelink:Transport}} and {{pagelink:AcknowledgementFramework}} pages (under the **Design** menu bar item). Awaiting confirmation of what data exchange and acknowledgement approach will be adopted for FHIR UK Core R4 based interactions between pathology laboratory systems and GP EPR systems.
* Added the following new `Bundle` examples:
    * {{pagelink:R4BundleExampleLipidsandHbA1cRequest}}
    * {{pagelink:R4BundleExampleLipidsandHbA1cReport}}
* Added an overview of the Implementation Guide Structure to the {{pagelink:Home}} page.
* Updated the {{pagelink:Glossary}}.

---

### v0.1.3 (08/12/2023)

* Added a new {{pagelink:Background}} page (under the **Design** menu bar item). This incorporates content from the previous version of the {{pagelink:DesignOverview}} page, with additional material describing GP practice pathology data flows. 
* Updated the {{pagelink:DesignOverview}} page (under the **Design** menu bar item). This now contains additional content, including a summary of the FHIR design approach that has been adopted as part of this implementation guide and the use of SNOMED CT.
* Updated references to the PaLM and PBCL SNOMED CT reference sets throughout the implementation guide.

---

### v0.1.2 (30/10/2023)

* Removed all FHIR STU3 related content, in line with the recent [announcement](https://simplifier.net/organization/hl7uk/news/151) from the NHS England Interoperability Standards Team that CareConnect has been deprecated and all development on the CareConnect FHIR STU3 assets has ceased.
* Updated the examples in the {{pagelink:R4Examples}} to include a populated `category` element for `UKCore-DiagnosticReport-Lab`, `UKCore-Observation-Group-Lab` and `UKCore-Observation-Lab`.
* Updated the structure of the implementation guide to align with the latest NHS England FHIR Implementation Guide template.

---

### v0.1.1 (04/10/2023)

* Updated to incorporate a new set of laboratory specific FHIR R4 derived profiles, as defined in the [UK Core Implementation Guide](https://simplifier.net/guide/ukcoreversionhistory/home?version=current) (currently STU2):
    * `UKCore-DiagnosticReport-Lab`
    * `UKCore-Observation-Group-Lab`
    * `UKCore-Observation-Lab`
    * `UKCore-ServiceRequest-Lab` 
    * Note: `UKCore-Specimen` does not have a pathology specific derived profile.
* Updated to use the NHS England FHIR Implementation Guide template.

---

### v0.1.0 (17/04/2023)

* Initial draft.