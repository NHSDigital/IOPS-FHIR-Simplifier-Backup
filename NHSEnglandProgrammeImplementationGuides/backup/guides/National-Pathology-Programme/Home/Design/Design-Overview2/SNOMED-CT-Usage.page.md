### SNOMED CT Usage
SNOMED CT concepts are used to populate the following key data elements in the FHIR profiles described in this implementation guide:

* The `code` element of {{pagelink:R4DiagnosticReport}} <b>SHALL</b> be populated using the following fixed SNOMED CT record artifact concept and description:
    * 721981007 | Diagnostic studies report
* The `code` element of {{pagelink:R4ObservationTestResult}} **SHALL** be populated using one of the following:
    * memberOf 1853551000000106 | PaLM (Pathology and Laboratory Medicine) observable entity simple reference set, OR
    * memberOf 999002881000000100 | PBCL (Pathology Bounded Code List) observables simple reference set
* The `code` element of {{pagelink:R4ObservationTestGroup}} **SHALL** be populated using one of the following:
    * memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
    * if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
    * if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the test group 
* The `code` element of {{pagelink:R4ServiceRequest}} **SHALL** be populated using one of the following:
    * memberOf 1853561000000109 | PaLM (Pathology and Laboratory Medicine) procedure simple reference set, OR
    * if a Procedure concept from the above reference set cannot be identified, use a SNOMED CT procedure code taken from descendantOf 386053000 | Evaluation procedure (procedure), OR
    * if the two methods described above fail to identify a suitable code, then it is acceptable to use a local code representing the requested test or test group
* The `type` element of {{pagelink:R4Specimen}} **SHALL** be populated using one of the following:
    * descendantOf 105590001 | Substance (in which case `Specimen.collection.method` and `Specimen.collection.bodySite` **SHOULD** also be populated), OR
    * descendantOf 49755003 | Morphologically abnormal structure, OR
    * descendantOf 123037004 | Body structure, OR
    * descendantOf 123038009 | Specimen, OR
    * descendantOf 260787004 | Physical object

The use of these aspects of SNOMED CT is illustrated in the following simplified data model for an example test report:

{{render:path-data-model-HbA1c-and-serum-lipid-levels-with-SNOMED-report}}

<br>

Further information on the use of SNOMED CT for pathology reporting can be found on the  [Pathology Standards and Implementation](https://digital.nhs.uk/services/pathology-standards-and-implementation/snomed-ct-for-pathology-reporting) website.