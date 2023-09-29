## {{page-title}}

No OperationDefinitions have been defined for genomics as of publication. The Genomic Medicine Service is being designed to be as RESTful as possible but some OperationDefinitions may need to be defined, pending requirements gathering.

@```
from
	OperationDefinition
select
	name, kind, url
order by
  name
```