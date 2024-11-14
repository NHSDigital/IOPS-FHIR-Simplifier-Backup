---
topic: Profile-UKCore-Observation
issue: UKCore-Observation
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation
expand: yes
---

## StructureDefinition {{variable:issue}}

Used to represent the bulk of clinical information to be sent alongside a Genomic Test Order, as well as clinical results included within structured Diagnostic Reports. 

Observations within Genomics are used to represent a point-in-time observation made about a patient or specimen. This means Observations SHOULD NOT be updated post-submission unless the original Observation has been entered in error or incorrectly coded (in this case, the appropriate status SHALL be used, e.g. entered-in-error or corrected).

For new observations which invalidate previous observations made about a patient, a new Observation resource SHOULD be created, the new observation MAY reference the invalidated observation via the observation-replaces extension.

| Profile url | FHIR Module | Normative Status |
|--
| <a href='https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release' target="_blank"> https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation </a> | [UKCore]() | trial-use |

{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}


<div id="Examples" class="tabcontent">
            <br/>
            <table>
                <tr>
                    <td>
                    {{pagelink:Observation-AutisticBehaviour-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-BlastPercentage-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-Bruising-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-Cellularity-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-CellularityKayBurbridge-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-DelayedSpeechLanguageDevt-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-DiseasePenetrance-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-DiseasePenetrancePheobeSmitham-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-DiseaseStatus-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-DutchLipidScore-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-EnlargedKidney-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-Haemoglobin-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-HepaticCysts-Example}}
                    </td>
                </tr> 
                <tr>
                    <td>
                    {{pagelink:Observation-Immunodefficiency-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-IntellectualDisabilityMild-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-IntellectualDisabilityProfound-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NatureAndAgeOfHearingLoss-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-Necrosis-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NecrosisKayBurbridge-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NeoplasticCell-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NeoplasticCellKayBurbridge-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-Neutrophils-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-GenomicEthnicity-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-MultipleRenalCysts-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-Nephronophthisis-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoBoneMarrowTransplantProbandFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoBoneMarrowTransplantProbandMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoFirstTrimesterFetalAnomalies-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoPregnancy-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoSecondTrimesterFetalAnomalies-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoTransfusion-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoTransfusionProbandFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoTransfusionProbandMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NoTransplant-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NonConsanguinousUnion-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NonConsanguinousUnionProband-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NonConsanguinousUnionProbandFather-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NonConsanguinousUnionProbandMother-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-NucleatedCellCount-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-Platelets-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-PregnancyConfirmation-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-QueryXanthoma-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-RenalInsufficiency-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-SimonBroomeCriteria-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-TumourType-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-TumourTypeKayBurbridge-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-UnknownConsanguinousUnionStatus-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-WhiteBloodCell-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Observation-SampleCellContent-Example}}
                    </td>
                </tr>
                 <tr>
                    <td>
                    {{pagelink:Observation-HistoryOfFetalLoss-Example}}
                    </td>
                </tr>
            </table>
        </div>

<div id="Mappings" class="tabcontent">
            <br>
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>Observation</td><td>Raw specimen/biopsy - Additional specimen/biopsy information, Extracted specimen - Additional specimen information, Further clinical information</td><td>OBX segments (may be attached to SPM)</td></tr>
                    <tr><td>Observation.code</td><td>Patient - Sexual orientation, Patient - Karyotypic sex, Patient - Pregnancy status, Patient - Fetal karyotypic sex, Patient - Is from consanguinous union, Fetus - Karyotypic sex, Fetus - Is testing for fetal loss from 24 weeks of gestation, PLCM activity - DNA concentration, PLCM activity - DNA quantification, PLCM activity - Test outcome code (Many), Raw specimen/biopsy - Taken alive/post mortem, Diabetic complications, Has absent reflexes</td><td>OBX-5 with appropriate SNOMED/READ/LOINC code</td></tr>
                    <tr><td>Observation.component</td><td>Patient - Pregnancy gestation period, Patient - Fetal gestation, Patient - Estimated Delivery Date (EDD), Patient - Pregnancy type, Absent reflexes detail</td><td>OBX-14 (compared with other ORC segments), OBR segments with appropriate codes</td></tr>
                    <tr><td>Observation.value\[x\]</td><td>Patient - Height (m), Raw specimen/biopsy - Skin/Bone affected status, Raw specimen/biopsy - Blasts %, Raw specimen/biopsy - Neoplastic cell content (%), Raw specimen/biopsy - Necrosis, Raw specimen/biopsy - Nucleated cell count, Raw specimen/biopsy - Tumour cellularity, Raw specimen/biopsy - Maternal cell contamination (MCC), Previous non genomic report - Test result value comparator, Previous non genomic report - Test result value unit of measure, Genomic ethnicity, ISTH BAT score, MODY probability calculator score, Patient BMI at time of genomic test request, Patient BMI at time of diagnosis, Maternal BMI at time of request, Paternal BMI at time of request, Birth weight</td><td>OBX-5/6</td></tr>
                    <tr><td>Observation.referenceRange.low</td><td>Previous non genomic report - Test result reference range low</td><td>OBX-7 (before operator)</td></tr>
                    <tr><td>Observation.referenceRange.high</td><td>Previous non genomic report - Test result reference range high</td><td>OBX-7 (after operator)</td></tr>
                    <tr><td>Observation.method</td><td>Previous non genomic report - Test result test method</td><td>OBX-17</td></tr>
                    <tr><td>Observation.referenceRange.text</td><td>Previous non genomic report - Test result reference range text</td><td>OBX-7</td></tr>
                    <tr><td>Observation.interpretation</td><td>Previous non genomic report - Test result clinical summary</td><td>OBX-8</td></tr>
                    <tr><td>Observation.bodySite</td><td>Subcutaneous fat loss areas, Increased fat deposition areas</td><td>OBX-5</td></tr>
                </table>
        </div>


<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>
<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#extension:observation-replaces">extension:observation-replaces</a>
- <a href="#status">status</a>
- <a href="#code">code</a>
- <a href="#subject">subject</a>
- <a href="#focus">focus</a>
- <a href="#effectiveDateTime">effectiveDateTime</a>
- <a href="#value">value\[x\]</a>
- <a href="#component">component</a>

<a name="extension:observation-replaces"></a>
<h4 class='additional-Guidance-Submenu'> extension:observation-replaces </h4>
A core extension on the base HL7 International Observation resource. Used to link to previous Observation resources which have been invalidated by this Observation instance, e.g. for cases where a previously present HPO term is now no longer applicable. For new observations which invalidate previous observations made about a patient, the new Observation resource SHOULD be created, and MAY reference the invalidated observation via the observation-replaces extension.

```json
    {
      "url": "http://hl7.org/fhir/StructureDefinition/observation-replaces",
      "valueReference": {
        "reference": "Observation/Observation-IntellectualDisabilityMild-Example"
      }
    }
  ```

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
SHOULD be marked as `final` for most observations unless corrected after submission. Observations within Genomics are used to represent a point-in-time observation made about a patient or specimen. This means Observations should not be updated post-submission unless the original Observation has been entered in error or incorrectly coded (in this case, the appropriate status SHALL be used, e.g. `entered-in-error` or `corrected`, respectively).

```json
"status": "final",
```

<a name="code"></a>
<h4 class='additional-Guidance-Submenu'> code </h4>
SHALL be present. SNOMED CT coding is preferred, though it is expected that alternative codings will be used depending on the appropriateness for a particular observation e.g. HPO or other codings found within the [HL7 International Genomic Reporting IG](https://hl7.org/fhir/uv/genomics-reporting/codings.html) as their use may already be widespread within Genomics. If a SNOMED CT equivalent exists for a code regularly captured within another CodeSystem, additional 'coding' elements within 'code' SHOULD be provided to aid analytics.

```json
"code": {
        "coding":  [
            {
                "system": "https://hpo.jax.org/app/",
                "code": "HP:0000105",
                "display": "Enlarged kidney"
            }
        ]
    },
```

<a name="subject"></a>
<h4 class='additional-Guidance-Submenu'> subject </h4>
SHALL be present. Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS

```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    },
```

<a name="focus"></a>
<h4 class='additional-Guidance-Submenu'> focus </h4>
For recording the Specimen the observation relates to, when the observation is not related to the patient from which the sample was taken e.g. Sample nucleated cell count.

This can also be used for observations related to the state of the patient at the time of collection e.g. pregnancy status. 

```json
"focus": {
        "reference": "Specimen/Specimen-BloodEDTA-Example"
    },
```

<a name="effectiveDateTime"></a>
<h4 class='additional-Guidance-Submenu'> effectiveDateTime </h4>
It is expected that all Observations SHOULD include the effective time the observation was made, if known, to aid interpretation.

```json
"effectiveDateTime": "2022-07-11T09:00:00Z",
```

<a name="value"></a>
<h4 class='additional-Guidance-Submenu'> value[x] </h4>
The value element SHOULD use the most appropriate data type for the observation in question. Using preferred CodeSystems as specified within HL7 International FHIR R4 or the UK Core. For asserting absence of a particular condition/situation, the finding SHOULD be specified within the 'code' element and 'valueBoolean' set to 'false' or 'valueCodeableConcept' set to an appropriate qualifier value code from SNOMED CT. For an assertion of a particular situation being present, e.g. a Condition or Procedure having been performed, these SHOULD be collected within the relevant clinical resources, alongside additional information needed to inform interpretation.

```json
"valueQuantity": {
        "value": 6.5,
        "system": "http://unitsofmeasure.org",
        "code": "10*12/L"
    }
```

<a name="component"></a>
<h4 class='additional-Guidance-Submenu'> component </h4>
SHOULD be used to group qualifiers of an observation. In particular, details regarding observations related to a pregnancy SHOULD be added as components on a pregnancy status observation.

Examples of how pregnancy information can be captured within Observations (pregnancy status with EDD, gestation etc. recorded as components) will be added to the {{pagelink:Fetus-Management}} Clinical Scenario.

```json
"component": [
		{
			"code": {
				"coding": [
					{
						"system": "http://snomed.info/sct",
						"code": "720451000000102",
						"display": "Assisted conception"
					}
				]
			}
		},
		{
			"code": {
				"coding": [
					{
						"system": "http://snomed.info/sct",
						"code": "226081000000107",
						"display": "Gestational age"
					}
				]
			},
			"valueQuantity": {
				"value": 87,
				"unit": "day",
				"system": "http://unitsofmeasure.org",
				"code": "d"
			}
		},
		{
			"code": {
				"coding": [
					{
						"system": "http://snomed.info/sct",
						"code": "161714006",
						"display": "Estimated date of delivery"
					}
				]
			},
			"valueDateTime": "2024-05-01"
		}
	],
```

---