## {{page-title}}

### Purpose
**Superseded by Patient and Previous Report sections**

To understand the family link between the triggering test and the cascade patient and locate the relative's genomic test results linked to the cascade test patient.
Relative's genomic test results/report used to direct and support interpretation.

<!--
### Notes
Information obtained from the index patient resource referenced from the ServiceRequest. Identifying relations to be considered for Cascade Testing requires sending RelatedPerson resources with the index patient test order. The exact process for cascade test ordering is still under consideration. 
Information from the report is mapped to DiagnosticReport, which can be included as 'supportingInfo' in a Cascade Patient test order.

### Mapping
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Linked test - Relative's relationship to cascade patient|Mandatory|N/A|N/A|N/A|Inverse of RelatedPerson.relationship||The relation of the triggering relative to the cascade patient.|
|Linked test - Relative's name|Mandatory|N/A|N/A|N/A|Patient.name|Inverse of NK1-3|The name of the relative whose results triggered the cascade test.|
|Linked test - Relative's DoB|Mandatory|N/A|N/A|N/A|Patient.birthDate|PID-7 for relative|The date of birth of the relative whose results triggered the cascade test.|
|Linked test - Relative's reporting organisation|Mandatory|N/A|N/A|N/A|DiagnosticReport.resultsInterpreter(PractitionerRole.organization)|OBR-32|The genomic reporting organisation of the relative whose results triggered the cascade test.|
|Linked test - Relative's reporting organisation identifier (lab number)|Mandatory|N/A|N/A|N/A|DiagnosticReport.resultsInterpreter(PractitionerRole.organization(Organization.identifier))|OBR-32.7.2|The genomic reporting organisation identifier of the relative whose results triggered the cascade test.|
|Linked test - Relative's clinical report / result|Optional|N/A|N/A|N/A|DiagnosticReport|OBR and OBX segments|The clinical report of the relative whose results triggered the cascade test.|
-->