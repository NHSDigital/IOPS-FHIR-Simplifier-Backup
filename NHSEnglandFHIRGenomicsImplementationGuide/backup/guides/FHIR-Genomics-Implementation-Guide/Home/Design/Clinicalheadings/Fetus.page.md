## {{page-title}}

### Purpose
To support genetic interpretation of tests and samples for fetuses.
To provide a clear divide between mother and fetus and support the management of multiple fetuses.

### Notes
Mapped to its own Patient resource, optionally tagged via a proposed birthStatus extension or future dated EDD in place of birthDate, as well as linked observations.

**Correct representation of fetal data is under review within the Interoperability Standards Team ans is subject to change**

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Fetus - Is sample for fetal or unregistered neonate|Patient indicated as fetus through either birthStatus extension (**pending backport of R5 extension**) on Patient resource or future dated birthDate, Specimen.subject|N/A PID-7 could be used if birthDate discrimination is chosen|Confirmation that the test is for a fetus or an unregistered neonate.|
|Fetus - Local identifier|Patient.identifier:system != https://fhir.nhs.uk/Id/nhs-number |PID-3 where PID-3.5 = 2.16.840.1.113883.2.1.3.2.4.18.24|Fetus identification code other than NHS number.|
|Fetus - Observed sex|Patient.gender|PID-8|Fetus phenotypic sex classification. Estimated physical characteristics determined by ultrasound. Gender for PLCM.|
|Fetus - Phenotypic sex (**TBC**)|Patient.extension:birthSex|PID-8|Fetus' sex classification determined by ultrasound.|
<!--|Fetus - Karyotypic sex|Observation.code( subject=Patient )|OBX-5 with appropriate SNOMED/READ/LOINC code|Absence or presence of X chromosome in the fetus.|-->
|Fetus - Are multiple fetuses being tested|N/A Inferred through inclusion of multiple Patient resources attached to test order|N/A inferred though inclusion of multiple PID segments attached to OML message|Confirmation that multiple fetuses are being tested.|
|Fetus - Is testing for fetal loss from 24 weeks of gestation|Inferred through inclusion observation/condition for fetal loss (code under 363681007) with date later than 24 weeks after pregnancy observation|Inferred though difference in OBX-14 for pregnancy and miscarriage/loss observations|Confirmation that the test is for a loss of pregnancy after 24 weeks gestation.|
|Fetus - Additional details|Clinical resources referencing fetal Patient resource|NTE/PRB/OBX segments related to PID for fetus|Further details for a fetal test.|
