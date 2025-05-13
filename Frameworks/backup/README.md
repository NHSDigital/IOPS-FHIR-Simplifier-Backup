# Acknowledgement Framework
The Framework project aims to become a repository for generic and agnostic solution that will support any future healthcare system using HL7 Standards.

# Use Cases
GP Registration - Patient registers online to join a GP practice
Galleri Pilot - Receive bio-sampling test results
Other use cases can be included in the near future


## Developers Information

### Validation Service
This repository uses the HAPI FHIR plain server to validate all assets and examples. See [IOPS-FHIR-Test-Scripts](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts/blob/main/README.md#iops-validation) for more information.
#### Validation Options
The `options.json` file gives the ability to customise the FHIR validator with options such a strict validation, ignore specific folders and files, and error if meta data is present. See [IOPS-FHIR-Test-Scripts README](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts/blob/main/README.md#options) for more information. 



### GitHub Actions
Information on the IG content spell / link / error checking can be found within the [IOPS-FHIR-Test-Scripts repo](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts/tree/main/IGPageContentValidator).

Information on the QualityControlChecker can be within the [IOPS-FHIR-Test-Scripts repo](https://github.com/NHSDigital/IOPS-FHIR-Test-Scripts/tree/main/QualityControlChecker).