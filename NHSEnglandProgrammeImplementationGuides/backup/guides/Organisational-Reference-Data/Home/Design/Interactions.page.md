## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>


### **Read an Organisation Record**

#### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?\{id}

Authorization – \{Bearer Token}

#### Parameters

The Organisation Code
-	\{id} 

<br>
<br>
{{render:ods-interations-get}}
<br>
<br>

#### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | Organization - {{pagelink:Example-Organization-4VE03}}|
| Invalid ID     | OperationOutcome - {{pagelink:Example-Invalid-ID}}|
 
<br>

### **Query for Organisation Record using Search Parameters**

#### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?

Authorization – \{Bearer Token}

#### Parameters

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
Supports: =, lt (less than), gt (greater than), and can be compounded to retrieve results between two dates
-	lastChangeDate=*\{lastChangeDate}*
-	e.g. lastChangeDate=*eq2020-09-04*
-	e.g. lastChangeDate=*gt2020-09-01*

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

#### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | Organization - {{pagelink:Example-Organization-Search-Result}}|
| No Records Found      | Bundle - {{pagelink:Example-No-Search-Results-Found}}|
| Access Deniedd       | Organization - {{pagelink:Example-Access-Denied}}|

<br>

### **Read an OrganisationAffiliation Record**

#### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/OrganizationAffiliation?

Authorization – \{Bearer Token}

#### Parameters

**active** – a boolean flag for active only or inactive only organizations<br>
-	active=*\{active}*
- e.g. active=True

**primary-organisation** - The ‘source’ organisation which has a relationship. Referred to as the SourceOrganisation in the ORD schema. Must be a valid Organisation id with relationships to return results
-	primary-organisation=*\{primary-organisation}*
- e.g. primary-organisation=https://fhir.nhs.uk/Id/ods-organization-code|G81086

**participating-organisation** - The ‘Target’ or related organisation. Referred to as the TargetOrganisation in the ORD schema. Must be a valid Organisation id.
-	participating-organisation=*\{participating-organisation}*
- e.g. participating-organisation=https://fhir.nhs.uk/Id/ods-organization-code|4VE03

#### HTTP Response Body

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record Found       | OrganizatioAffiliation - {{pagelink:Example-OrganizationAffiliation-256248}}|
| No Records Found      | Bundle - {{pagelink:Example-No-Search-Results-Found}}|
| Access Deniedd       | Organization - {{pagelink:Example-Access-Denied}}|
 
<br>