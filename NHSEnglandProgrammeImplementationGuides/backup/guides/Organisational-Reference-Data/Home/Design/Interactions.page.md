## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>


### **Read an Organisation Record**

#### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?\{id}

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

### **Query for Organisation Record using lastChangeDate**

#### HTTP request and Headers

**<font color="#00008B">GET</font>** \{fhir-server}/Organization?lastchangeDate=\{lastChangeDate}

#### Parameters

The lastChangeDate – the date when ODS last modified the record<br>
Supports: =, lt (less than), gt (greater than), and can be compounded to retrieve results between two dates
-	\{lastChangeDate} 

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

