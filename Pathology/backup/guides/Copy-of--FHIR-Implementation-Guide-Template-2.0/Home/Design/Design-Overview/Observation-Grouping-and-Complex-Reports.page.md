---
topic: DesignRelatedTests
---
### Observation Grouping and Complex Reports
Pathology test reports may contain groups of related test results, such as those defined as part of a battery or a panel e.g. a Full Blood Count. Test results may also be related to one another in other ways, for example as a chronological sequence of results such as those associated with a dynamic function test (also known as a timed test) e.g. a Glucose Tolerance Test.

FHIR provides several mechanisms for grouping related tests i.e. Observations. The various approaches are detailed in the base [R4](https://hl7.org/fhir/R4/observation.html#obsgrouping) specification.

#### Test Groups
The main method of grouping test results that has been adopted by this specification is the use of the ‘hasMember’ relationship. This allows an Observation to be defined as a test group (such as a Full Blood Count) with ‘hasMember’ references to Observations containing the results for each of the tests contained within the test group. In the case of a Full Blood Count, the referenced Observations would contain the results for white blood cell count, red blood cell count, platelet count etc.

 {{render:path-data-model-LFT-UandE-report}}

#### Complex Reports
Multiple levels of test group Observations and test result Observations may be nested to support complex report structures, such as those used in Microscopy, Culture and Sensitivity (MCS) reports.

#### Dynamic Function Tests
Dynamic function tests may be structured using a combination of:
* a group level Observation with ‘hasMember’ relationships to the Observations containing the test results for each time interval e.g. blood glucose level at 0 minutes, blood glucose level at 30 minutes, blood glucose level at 60 minutes etc.
* ‘sequelTo’ relationships to link the Observations containing the test results to one another

---


