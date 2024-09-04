## Genomics Reporting Operations
For Genomic Data Retrieval, including integration with the proposed NHS England Unified Genomic Record, the NHS England Genomics Unit are currently considering adoption of the [GenomeX Genomic Operations guidance](https://build.fhir.org/ig/HL7/genomics-reporting/operations.html).

### find-subject-variant

Specifically, the [find-subject-variants operation](https://build.fhir.org/ig/HL7/genomics-reporting/OperationDefinition-find-subject-variants.html) (Structured FHIR variant query) can be implemented as a facade on the [htsget operation](https://samtools.github.io/hts-specs/htsget.html) (binary VCF query), with the regions passed through to the htsget call, and the returned variants converted to FHIR resources, using the component allele slices as an un-altered copy of the VCF Variant, and potentially cached. The FHIR representation can then be further enriched with annotations and alternative representations of the variant using other component slices. 

The VCF model has support for annotations e.g. through the text field (8th column) within a VCF file. While this can be split by commas etc. fully structured annotation is not supported.

While storing all variants as FHIR resources would be prohibitively costly, [FHIR variants](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-variant.html) can be generated for variants of clinical significance. As structured reporting progresses, representing variants within FHIR can be incorporated into the interpretation process, using guidance from the [Genomics Reporting IG](https://build.fhir.org/ig/HL7/genomics-reporting/sequencing.html). Variants can then be linked directly to the report that uses this data.

This operation is linked to the DocumentReference resource in that the DocumentReference, within the context of the Genomics FHIR Implementation Guide, will point to the binary Genomic Data file, potentially using a DRS url. This file may be a full list of the variants found. htsget, and the FHIR equivalent find-subject-variants, will search this file for variants at particular locations and transform these into the relevant FHIR Variants (a profile on Observation).

### Other subject level operations

Implementation of other subject level operations are pending use cases to support these operations.

### Population level operations

Implementation of population level operations are pending use cases to support these operations. It is expected these operations may be used to support research or population health based statistics.

### Metadata operations

The [find-study-metadata](https://build.fhir.org/ig/HL7/genomics-reporting/OperationDefinition-find-study-metadata.html) operation can be used to query for subject/test specific metadata such as regions studied and DNA change types tested for.

It is expected that the test requested will have its own set of metadata, driven by the genomics testing service (Test Directory) but actual delivered tests may differ due to a number of factors, e.g. specimen quality, equipment available etc.

The delivered test metadata will need to be recorded against the outcome of a test i.e. the DiagnosticReport. As per the Genomics Reporting IG, it is expected that this would be recorded via the [Genomic Study](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study.html) profile on procedure, and component [Genomic Study Analysis](https://build.fhir.org/ig/HL7/genomics-reporting/StructureDefinition-genomic-study-analysis.html). Effective use of this operation requires the analyses performed to be consistently and routinely structured (which is not currently the case within Genomics in the UK. As such preliminary work to structure the metadata surrounding tests will need to be performed, this may be facilitated by the work programmes within NHS England to standardise and share bioinformatics pipelines/workflows.