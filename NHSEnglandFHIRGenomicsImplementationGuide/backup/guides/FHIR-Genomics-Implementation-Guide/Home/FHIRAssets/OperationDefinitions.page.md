## {{page-title}}

No OperationDefinitions have been defined for genomics as of publication. The Genomic Medicine Service is being designed to be as RESTful as possible but some OperationDefinitions may need to be defined, pending requirements gathering.

For Genomic Data Retrieval, including integration with the proposed NHS England Unified Genomic Record, the NHS England Genomics Unit are currently considering adoption of the [GenomeX Genomic Operations guidance](https://build.fhir.org/ig/HL7/genomics-reporting/operations.html).

@```
from
	OperationDefinition
select
	name, kind, url
order by
  name
```