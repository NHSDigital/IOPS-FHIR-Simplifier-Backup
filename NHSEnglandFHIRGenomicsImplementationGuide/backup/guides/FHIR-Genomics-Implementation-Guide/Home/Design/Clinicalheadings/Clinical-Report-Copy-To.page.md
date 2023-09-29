## {{page-title}}

### Purpose
**Superseded by Additional Contacts**

To know who to copy clinical results to and how they should be contacted.

<!--
### Notes
Mapped to Subscription resources targeting the response to the ServiceRequest. Note, this cannot explicitly record entity names so alternatives are being investigated.

### Mapping
| Source Data item | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Clinical report cc to - Entity name|Subscription.contact|Additional STF segments (STF-3), referenced through OBR-28|Name of who the report should be copied to.|
|Clinical report cc to - Email address|Subscription.channel.endpoint:type=email|STF-15|Email address of who the report should be copied to.|
-->
<!--
| Source Data item | Non WGS Rare Disease | Non WGS Cancer | WGS Rare Disease | WGS Cancer | Target FHIR Element | HL7v2.5.1 Mapping | Description 
|--|--|
|Clinical report cc to - Entity name|Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Subscription.contact|Additional STF segments (STF-3), referenced through OBR-28|Name of who the report should be copied to.|
|Clinical report cc to - Email address |Mandatory IF|Mandatory IF|Mandatory IF|Mandatory IF|Subscription.channel.endpoint:type=email|STF-15|Email address of who the report should be copied to.|
-->