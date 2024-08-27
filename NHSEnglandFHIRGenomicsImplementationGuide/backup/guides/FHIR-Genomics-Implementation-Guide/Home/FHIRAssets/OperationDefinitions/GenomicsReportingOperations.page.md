## Genomics Reporting Operations
For Genomic Data Retrieval, including integration with the proposed NHS England Unified Genomic Record, the NHS England Genomics Unit are currently considering adoption of the [GenomeX Genomic Operations guidance](https://build.fhir.org/ig/HL7/genomics-reporting/operations.html).

### find-subject-variant

Specifically, the [find-subject-variants operation](https://build.fhir.org/ig/HL7/genomics-reporting/OperationDefinition-find-subject-variants.html) (Structured FHIR variant query) can be implemented as a facade on the [htsget operation](https://samtools.github.io/hts-specs/htsget.html) (binary VCF query), with the regions passed through to the htsget call, and the returned variants converted to FHIR resources, using the component allele slices as an un-altered copy of the VCF Variant, and potentially cached. The FHIR representation can then be further enriched with annotations and alternative representations of the variant using other component slices. 

The VCF model has support for annotations e.g. through the text field (8th column) within a VCF file. While this can be split by commas etc. fully structured annotation is not supported.

While storing all variants as FHIR resources would be prohibitively costly, [FHIR variants](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-variant.html) can be generated for variants of clinical significance. As structured reporting progresses, representing variants within FHIR can be incorporated into the interpretation process, using guidance from the [Genomics Reporting IG](https://build.fhir.org/ig/HL7/genomics-reporting/sequencing.html). Variants can then be linked directly to the report that uses this data.