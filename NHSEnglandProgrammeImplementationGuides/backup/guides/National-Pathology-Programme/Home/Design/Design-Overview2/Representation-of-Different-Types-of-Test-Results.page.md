### Representation of Different Types of Test Results
Laboratory test results are reported using a variety of forms. These are described below with supporting examples. Each example includes a link to a corresponding FHIR `Observation` example (all of the examples are also listed in the {{pagelink:R4Examples}}).

* **Quantitative Result:** the result is expressed as a number, usually with an associated unit of measure. Comparators may be used to indicate that the actual value is greater than or less than the stated value. A range of values may be reported instead of a single value. Examples include:
    * {{pagelink:R4ObservationAlbumin}}: 47 g/L
    * {{pagelink:R4ObservationeGFR}}: >90 mL/min/1.73m2
* **Semi-quantitative Result:** the result is expressed using a descriptor to indicate the relative degree of positivity or negativity based on a scale. The scale is not always formally defined. Semi-quantitative results are widely used in microbiology, particularly for reporting microscopy and culture test results to indicate the amount or level of growth of organisms. Examples include:
    * {{pagelink:R4ObservationEpithelialCells}}: +
    * {{pagelink:R4ObservationNitrofurantoinSusceptibility}}: RESISTANT
* **Qualitative Result:** the result is expressed using a descriptor to indicate positivity or negativity. The descriptors are usually defined as pairs, for example: positive/negative, detected/not detected, isolated/not isolated. In this respect, qualitative results can be seen as a subset of semi-quantitative results in that they contain only two scale points to indicate positivity or negativity. Examples include:
    * {{pagelink:R4ObservationHBsAg}}: NEGATIVE
    * {{pagelink:R4ObservationMRSAScreeningTest}}: NOT DETECTED
* **Quantitative Result Combined with an Interpretation:** in some cases, a result may contain a combination of quantitative and non-quantitative elements. The non-quantitative element is sometimes expressed separately as an interpretation to provide a categorical assessment of the quantitative value. Examples include:
    * {{pagelink:R4ObservationLymphocyteCount}}: 0.70 10*9/L LOW
    * {{pagelink:R4ObservationRubellaIgGAntibody}}: >10 IU/ml DETECTED
* **Narrative Result:** the result is presented as text, for example:
    * {{pagelink:R4ObservationAerobicBloodCulture}}: No growth detected after 5 days incubation

The `Observation.value[x]` data element is used to represent the test result value. The `[x]` part of the element name is replaced with an appropriate data type, based on the type of result:
* for **quantitative** results, `valueQuantity`, `valueRange` or `valueRatio` **SHOULD** be used
* for **semi-quantitative** and **qualitative** results, `valueCodeable` **SHOULD** be used, with a suitable SNOMED CT concept, for example: `260385009` `Negative`
* for **narrative** results, `valueString` **SHOULD** be used.

The `Observation.interpretation` data element is used to provide a coded, categorical assessment of a test result value. The code is taken from the [ObservationInterpretationCodes]( https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/80843) FHIR value set. The associated test result value is usually **quantitative** and represented using `valueQuantity`, `valueRange` or `valueRatio` as described above.

**Note:** Semi-quantitative and qualitative results are currently represented as text in PMIP EDIFACT (NHS003). To facilitate the adoption of FHIR and minimise the impact on existing systems and processes, it is anticipated that these types of results will initially continue to be represented as text (using `valueString`).

Refer to the {{pagelink:R4ObservationTestResult}} profile definition for further information relating to the representation of test results.