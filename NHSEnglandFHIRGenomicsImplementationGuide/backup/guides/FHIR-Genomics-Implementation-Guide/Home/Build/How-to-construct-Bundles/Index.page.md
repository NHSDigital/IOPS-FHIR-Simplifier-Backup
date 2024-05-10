## {{page-title}}

Definitions for bundles are included in {{pagelink:Home/FHIRAssets/MessageDefinitions}} **NOTE: these will be replaced by GraphDefinitions as the Genomic Order Management Service will not be supporting the messaging paradigm**. However, please note the definitions are only indicative of the resources expected in a request/report transaction, as the central services will use RESTful transactions rather than messages. Additional resources can be sent as long as they are not orphaned (not referenced from other resources in the transaction).

The bundles currently defined for the Genomic Medicine Service are the {{pagelink:Genomic-Test-Request}}, which includes the original test order and associated information, and the {{pagelink:Genomic-Test-Response}}, which is the final diagnostic report and associated information return by the genomic lab.

The use of messages within the Genomic Medicine Service, over a completely RESTful interface is currently under review.


