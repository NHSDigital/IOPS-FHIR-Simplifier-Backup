## {{page-title}}

The Register with a GP Surgery Form has been represented through a {{pagelink:Questionnaire}} resource, developed using the [LHC-Forms Form Builder Tool](https://lhncbc.nlm.nih.gov/LHC-research/LHC-projects/health-information/lhc-forms.html). 

**The draft Form Definition can be found on the [IOPS FHIR Development and Testing Tool](https://nhsdigital.github.io/interoperability-standards-tools-skunkworks/questionnaire?url=https:%2F%2Ffhir.nhs.uk%2FEngland%2FStructureDefinition%2FEngland-Questionnaire-RegisterGPSurgeryv2). It is expected this will be moved into an NHS England Forms Library once this has been developed. Please note that this definition is pending review from NHS England Data Standards and Terminology teams**

Filling of the form should result in a {{pagelink:QuestionnaireResponse}} resource. Guidance on the generation of a QuestionnaireResponse resource for Structured Data Capture can be found on the {{pagelink:IHE-Structured-Data-Capture}} pages.

Individual questions can be extracted from the QuestionnaireResponse in the form of other clinical/administrative resources, e.g. Patient for demographic details and Observation for specific patient reported observations. Examples of the QuestionnaireResponse and extracted resources are linked from the {{pagelink:Home/Use-Cases/Patient-Registration/Services/Register-with-a-GP-Surgery/Examples.page.md}} page.