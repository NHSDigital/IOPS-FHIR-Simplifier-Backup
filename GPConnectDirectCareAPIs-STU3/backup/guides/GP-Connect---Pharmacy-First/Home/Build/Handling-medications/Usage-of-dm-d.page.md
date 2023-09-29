## {{page-title}}

You must be familiar with the [NHS dictionary of medicines and devices (dm+d)](https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd) and [SNOMED-CT](https://termbrowser.nhs.uk/).

The dm+d is the NHS choice for recording details of medicines and devices in the electronic patient record and is the medicines standard approved by the Standardisation Committee for Care Information (SCCI) as an NHS Fundamental standard.

All dm+d concepts are included in the SNOMED-CT UK Drug Extension and all dm+d codes are SNOMED-CT codes. The basic dm+d structure with the associated SNOMED CT UK drug extension Trade Family concept class is shown below, with examples at each level.

As such, please ensure that a dm+d code as a `medicationCodeableConcept` is used where possible with the code system: `https://dmd.nhs.uk`, over a `medicationReference`.


{{render: dm-d-concepts-v2}}

---