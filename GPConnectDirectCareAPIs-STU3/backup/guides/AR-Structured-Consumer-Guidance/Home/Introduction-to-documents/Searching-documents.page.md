## {{page-title}}

### Use case 

Search for a patient’s Documents from a GP practice. 

### Search parameters 

Provider systems **SHALL** support the following search parameters: 

| Name          | Type                 | Description                                   | Paths                                                      | 
|---------------|----------------------|-----------------------------------------------|------------------------------------------------------------| 
| `created`     | `date` or `dateTime` | Creation/Edit datetime of the Document.       | `DocumentReference.created`                                | 
|     `author`  | `token`              |     Who and/or what authored the Document.    | `DocumentReference.author`                                 | 
| `description` | `string`             | Keyword based search.                          | `DocumentReference.description` + `DocumentReference.type` | 

==flesh out descriptions and author in above table, with the aim of being more human readable== 

>**Note:** If you need to know what search parameters exist for a certain Provider, check the Provider's Access Document [FHIR capability statement]( https://developer.nhs.uk/apis/gpconnect-1-6-0/access_Documents_use_case_get_the_fhir_capability_statement.html). 

<span style="color:red">**Provider or provider?**</span>


>**Important:** The `type` and `facility` parameters have been removed from the API. These will be reinstated in the future when provider systems contain the metadata to support them. The original release of the Access Documents capability contained `type` and `facility` parameters which could be used to search for types of clinical Document and the types of clinical settings where they were created. These have been removed while the quality of the metadata in provider systems around these items improves. They will be reinstated at the point that they can be supported. 

 

==simplify the above – consumers probably only need to know that these are the current ones and more will be added in the future== 

 

### _include parameters 

Provider systems **SHALL** support the following include parameters: 

 

==add table== 

Name 

Description 

Paths 

`_include= DocumentReference:subject:Patient` 

Include `Patient` resources referenced within the returned `DocumentReference` resources 

`DocumentReference.subject` 

`_include= DocumentReference:custodian:Organization` 

Details of organisations that are custodians for the Documents that are returned in DocumentReference resources 

  

`_include= DocumentReference:author:Organization` 

Details of organisations that authored the Documents that are returned in DocumentReference resources 

  

`_include= DocumentReference:author:Practitioner` 

Details of who/what authored the Documents that are returned in DocumentReference resources 

  

`_revinclude:recurse= PractitionerRole:practitioner` 

Include `PractitionerRole` resources referenced from matching `Practitioner` resources 

`DocumentReference.author:Practitioner` 

 

==in addition to the documents returned, other additional information can be requested to reduce the number of API calls. The parameters for this can be found here (add link)== 

 

 

| Name                                                          | Description                                                                                                              | Paths                                          | 

|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------|------------------------------------------------| 

| `_include= DocumentReference:subject:Patient`                 |     Include `Patient` resources referenced within the   returned `DocumentReference` resources                           |     `DocumentReference.subject`                | 

|     `_include= DocumentReference:custodian:Organization`      |     Details of organisations that are custodians for   the Documents that are returned in DocumentReference resources    |                                                | 

|     `_include=   DocumentReference:author:Organization`       |     Details of organisations that authored the Documents   that are returned in DocumentReference resources              |                                                | 

|     `_include=   DocumentReference:author:Practitioner`       |     Details of who/what authored the Documents that   are returned in DocumentReference resources                        |                                                | 

|     `_revinclude:recurse=   PractitionerRole:practitioner`    |     Include `PractitionerRole` resources referenced from matching `Practitioner` resources                               |     `DocumentReference.author:Practitioner`    | 

 

==end table== 

 

Consumer systems **MUST** send the following parameters to reduce the number of API calls: 

- `_include=DocumentReference:subject:Patient` 

- `_include=DocumentReference:custodian:Organization` 

- `_include=DocumentReference:author:Organization` 

- `_include=DocumentReference:author:Practitioner` 

- `_revinclude:recurse=PractitionerRole:practitioner` 

Consumer systems **MAY** send the following parameters in the request: 

- `created` 

- `author` 

- `description` 

When using the ‘created’ parameter, consumers **MUST** do the following 

- to search for a lower boundary of a date: 

==tab bullet== - a single `created` parameter with a date prefixed by `ge` should be supplied 

- to search for a upper boundary of a date: 

==tab bullet== - a single `created` parameter with a date prefixed by `le` should be supplied 

- to search between two dates: 

==tab bullet== -two created parameters should be supplied 

==double tab bullet== - a single `created` parameter with a date prefixed by `ge` 

==double tab bullet== - a single `created` parameter with a date prefixed by `le` 

 

##### Payload request body 

n/a 

##### Error handling 

==author search is only for an author organisation – this is executed using the ODS code for the organisations. Gp systems sometimes identify the authoring organisation without linking the ods code so consumers could miss docs from an author or organisation by searching via author plus ODS code. An alternative would be to search for all authors and to offer the consumer user the ability to filter on the text string of the author within the consuming system UI== 

 

==explain the three parameters and explain the consequences of using them== 
