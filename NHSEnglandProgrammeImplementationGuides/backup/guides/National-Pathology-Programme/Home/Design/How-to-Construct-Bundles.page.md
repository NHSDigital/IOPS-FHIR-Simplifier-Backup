---
topic: ContructBundles
---
## How to Construct Bundles
### Test Request Bundles
The following is a list of the profiles that are used to construct a `Bundle` for a pathology test request:

* {{pagelink:R4Bundle}}
* {{pagelink:R4MessageHeader}}
* {{pagelink:R4Organization}}
* {{pagelink:R4Patient}}
* {{pagelink:R4Practitioner}}
* {{pagelink:R4PractitionerRole}}
* {{pagelink:R4ServiceRequest}}
* {{pagelink:R4Specimen}}

The following diagram illustrates the relationships between each of the profiles that form the <code>Bundle</code>. The arrows represent the direction of the references between the profiles.

{{render:path-diagram-R4-request-bundle}}

---

### Test Report Bundles
The following is a list of the profiles that are used to construct a `Bundle` for a pathology test report:

* {{pagelink:R4Bundle}}
* {{pagelink:R4DiagnosticReport}}
* {{pagelink:R4MessageHeader}}
* {{pagelink:R4ObservationTestGroup}}
* {{pagelink:R4ObservationTestResult}}
* {{pagelink:R4Organization}}
* {{pagelink:R4Patient}}
* {{pagelink:R4Practitioner}}
* {{pagelink:R4PractitionerRole}}
* {{pagelink:R4ServiceRequest}} 
* {{pagelink:R4Specimen}}

The following diagram illustrates the relationships between each of the profiles that form the <code>Bundle</code>. The arrows represent the direction of the references between the profiles.

{{render:path-diagram-R4-report-bundle}}