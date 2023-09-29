## {{page-title}}

The prescription token allows the patient to choose the pharmacy which will fulfill the prescription order. 

The prescription token is used by the dispenser to retrieve a non-nominated prescription quickly and effectively without having to cross-reference different stand-alone systems. 

The prescription may be in a variety of forms:

- [EPS Token](https://nhs-prod.global.ssl.fastly.net/binaries/content/assets/website-assets/services/electronic-prescription-service/eps-prescribing-system-mvp/eps_prescription_token_specification.pdf)
- [digital](https://digital.nhs.uk/services/electronic-prescription-service/eps-requirements/eps-digital-prescription-token-specification)

For EPS purposes they are both considered to be FHIR {{pagelink:NHSDigital-Task}}

{{render:release-patient}}

1. The {{pagelink:PrescriptionRelease}} operation is used to retrieve the prescriptions using the prescription token id code as a parameter.


