## {{page-title}}

Conceptmaps created for use within the NHSE FHIR Genomics Implementation Guide. They are used for the translation and recording of concepts between MDS source data(code-options) to equivalent Snomed CT codes, and FHIR spec

@```
from
	ConceptMap
select
Title:title, Canonical:url
order by
  title
```