### Coded Entries (COVID-19)

Each Section of the Summary Care Record document (Composition) may be supported by coded data. Reference to the coded data for a section is found under Composition.section.entry.

The coded data that may be passed to the Summary Care Record is defined by the SNOMED CT refset 
999004331000000102 |Summary Care Record inclusion simple reference set (foundation metadata concept). COVID-19 related codes will have to be extracted from this refset.

In order to pass coded entry data to the SPINE, the SNOMED CT concepts (from the above refset) need to be coded with their relevant Care Record Element Type (CRE Type).

The relevant CRE Type for each concepts in the 999004331000000102 |Summary Care Record inclusion simple reference set (foundation metadata concept) can be looked-up using the refset 1322291000000109 National Health Service Care Record Element association reference set (foundation metadata concept), which maps SNOMED CT concepts onto their relevant CRE Types. Where a CRE Type mapping does not exist, the "default" CRE Type 163131000000108 | Clinical Observations and Findings | should be used.

Each CRE Type is synonymous with a Summary Care Record heaing, and should flow under its relevent heading. For example, CRE Type 163141000000104 | Investigation results - care record element (record artifact) | should flow under the Investigation Results section heading.

CRE Types use relevent FHIR resource types. In terms of the COVID-19 codes in the 999004331000000102 | Summary Care Record inclusion simple reference set (foundation metadata concept), COVID-19 concepts use the following CRE Types and resource types.

## CRE Type to Rescource Type Mapping

|CRE Type |Resource Type |
|--
|163141000000104 \|  Investigation results - care record element (record artifact)|Observation|
|163231000000100 \| Risks to patient - care record element (record artifact)|Observation|
|162951000000105 \|  Care events - care record element (record artifact)|Encounter|
|163081000000108 \|  Investigations - care record element (record artifact)|Procedure|
|163071000000106 \|  Treatments - care record element (record artifact)|Procedure|
|163001000000103 \| Diagnoses - care record element (record artifact)ses|Observation|
|163131000000108 \| Clinical observations and findings - care record element (record artifact) |Observation|
|162961000000108 \|  Personal preferences - care record element (record artifact)|Observation|
|185371000000109 \|  Medication recommendations - care record element (record artifact)|ImmunizationRecommendation*|
|163111000000100 \| Medication record - care record element (record artifact)|Immunization*|
|163101000000102 \| Provision of advice and information to patients and carers - care record element (record artifact) |Communication|
|163181000000107 \| Patient/carer correspondence - care record element (record artifact)|Communication|

\* note that for CRE Types 185371000000109 | Medication recommendations - care record element (record artifact) | and 163111000000100 | Medication record - care record element (record artifact) |, the COVID-19 concepts are related to immunisations, so Immunisation resources are used to hold the data. For other concepts that fall under these CRE Types (in future) other resource types may be used.