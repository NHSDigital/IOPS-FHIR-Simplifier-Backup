## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

The ODS FHIR R4 API allows healthcare professionals to use healthcare applications acting as API consumers to search for, read and display organisation information.

The ODS FHIR R4 API provides 2 endpoints:

    - /Organization
    - /OrganizationAffiliation

While specific supported search parameters have been included for guidance, additional parameters and general guidance on searching is available here: [FHIR Search](https://hl7.org/fhir/R4/search.html).

---

## **Read an Organisation Record by ID**

### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?\{id}

Authorization – \{Bearer Token}

### Parameters

The Organisation Code
-	*\{id}*
- e.g. 4VE03

<br>
<br>
{{render:ods-interations-get}}
<br>
<br>

### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | Organization - {{pagelink:Example-Organization-4VE03}}|
| Invalid ID     | OperationOutcome - {{pagelink:Example-Invalid-ID}}|
 
---

## **Query for an Organisation Record using Search Parameters**

### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?

Authorization – \{Bearer Token}

### Parameters

**active** – a boolean flag for active only or inactive only organizations<br>
-	active=*\{active}*
- e.g. active=True

**type** – kind of organization <br>
Can be used to search for organizations with specific {{pagelink:CodeSystem-England-ODSRecordClass,text:ODSRecordClass}} or {{pagelink:CodeSystem-England-ODSRecordUseType,text:ODSRecordUseType}} values
-	type=*\{type}* 
- e.g. type=https://fhir.nhs.uk/England/CodeSystem/England-ODSRecordUseType|Full
- e.g. type=https://digital.nhs.uk/services/organisation-data-service/CodeSystem/ODSRecordClass|RC1

**name** – the name associated with the organization<br>
-	name=*\{name}* 
- e.g. name=ATOS%20MEDICAL

**lastChangeDate** – the date when ODS last modified the record<br>
Supports: eq (equal), lt (less than), gt (greater than), and can be compounded to retrieve results between two dates
-	lastChangeDate=*\{lastChangeDate}*
-	e.g. lastChangeDate=eq2020-09-04
-	e.g. lastChangeDate=gt2020-09-01

**roleCode** – searches on all ODS {{pagelink:Extension-England-OrganisationRole,text:OrganizationRole}} assignments, via the roleCode element<br>
-	roleCode=*\{roleCode}*
- e.g. roleCode=https://digital.nhs.uk/services/organisation-data-service/CodeSystem/ODSOrganisationRole|RO94

**activeRoleCode** – searches on active ODS {{pagelink:Extension-England-OrganisationRole,text:OrganizationRole}} assignments, via the roleCode element<br>
-	activeRoleCode=*\{activeRoleCode}*
- e.g. roleCode=https://digital.nhs.uk/services/organisation-data-service/CodeSystem/ODSOrganisationRole|RO182

<br>
<br>
{{render:ods-interations-search}}
<br>
<br>

### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | Bundle - {{pagelink:Example-Organization-Search-Result}}|
| No Records Found      | Bundle - {{pagelink:Example-No-Organisation-Search-Results-Found}}|

---


## **Read an Organisation Relationship Record by ID**

### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/OrganizationAffiliation?\{id}

Authorization – \{Bearer Token}

### Parameters

The organisation relationship ID
-	*\{id}*
- e.g. 256248

### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | OrganizationAffiliation - {{pagelink:Example-OrganizationAffiliation-256248}}||
| Invalid ID     | OperationOutcome - {{pagelink:Example-Invalid-ID}}|
 
---

## **Query for an Organisation Relationship Record using Search Parameters**

### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/OrganizationAffiliation?

Authorization – \{Bearer Token}

### Parameters

**active** – a boolean flag for active only or inactive only organisation relationships<br>
-	active=*\{active}*
- e.g. active=True

**primary-organization** - The ‘source’ organisation which has a relationship. Referred to as the SourceOrganisation in the ORD schema. Must be a valid Organisation id with relationships to return results
-	primary-organization=*\{primary-organisation}*
- e.g. primary-organization=https://fhir.nhs.uk/Id/ods-organization-code|G81086

**participating-organization** - The ‘Target’ or related organisation. Referred to as the TargetOrganisation in the ORD schema. Must be a valid Organisation id.
-	participating-organization=*\{participating-organisation}*
- e.g. participating-organization=https://fhir.nhs.uk/Id/ods-organization-code|4VE03

**_include** - enables you return related resources.<br>
For example:<br>
OrganizationAffiliation:primary-organization will include Organization resource records for the SourceOrganisations in the search results<br>
OrganizationAffiliation:participating-organization will include Organization resource records for all the TargetOrganisations in the search results
-	_include=*\{include}*
- e.g. _include=OrganizationAffiliation:primary-organization

### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | Bundle - {{pagelink:Example-OrganizationAffiliation-Search-Result}}|
| _include Usage       | Bundle - {{pagelink:Example-_include-Search-Result}}|
| No Records Found      | Bundle - {{pagelink:Example-No-Relationship-Search-Results-Found}}|
 
---