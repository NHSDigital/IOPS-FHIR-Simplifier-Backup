## {{page-title}}

Definitions for bundles are included in {{pagelink:Home/FHIRAssets/GraphDefinitions}} **NOTE: these GraphDefinitions are still in development and will be iterated on as further requirements for bundled resources are identified**. However, please note the definitions are only indicative of the minimum resources expected in a request/report transaction, as the central service is expected to flexibly allow for additional information to be attached to payloads, such as clinical information for a test order. The Central Service is based on RESTful transactions rather than messages. Additional resources can be sent as long as they are not orphaned (not referenced from other resources in the transaction).

The bundles currently defined for the Genomic Medicine Service are the {{pagelink:Genomic-Test-Request}}, which includes the original test order and associated information, and the {{pagelink:Genomic-Test-Response}}, which is the final diagnostic report and associated information return by the genomic lab.

The use of messages within the Genomic Medicine Service, over a completely RESTful interface is currently under review.

It is intended that the central Genomic Order Management broker will support submission of Bundles of type ```"transaction"``` only. Supported HTTP verbs will be limited to 'POST' and 'PUT' i.e. creation of updates of resources on the server. GET requests submitted as part of transaction will be ignored and, as per the guidelines provided on the {{pagelink:Supported-CRUD-capability}} page, there are no plans to support DELETEs on the central broker.
