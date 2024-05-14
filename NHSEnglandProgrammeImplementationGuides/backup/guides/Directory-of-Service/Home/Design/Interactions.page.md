## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

### Query for an HealthcareService with matching criteria

<plantuml>
@startuml
actor       HealthcareProfessional       as Foo1
participant    Client    as Foo2
participant    Server    as Foo3    
Foo2 -> Foo3 : Find appropriate HealthcareService QueryRequest
Foo3 -> Foo2 : Find appropriate HealthcareService QueryResponse
@enduml
</plantuml>

### Query for an available HealthcareService, Location, Schedule, Slot

ABC

### Query for an FGM indicator

**<font color="#00008B">GET</font>** /Flag?patient:identifier=https://fhir.nhs.uk/Id/nhs-number|&lt;nhs-number&gt;

**Parameters**

The patient's NHS Number. This must be a verified NHS Number.
- patient:identifier (required), type <a href='http://hl7.org/fhir/R4/search.html#token'>token</a>. 

<br>
<br>
{{render:fgm-is-interactions-get}}
<br>
<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example---FGM-flag-found.page.md}}|
| No record found       | SearchSet Bundle - {{pagelink:Home/Examples/Example---FGM-flag-not-found.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

<br>

### Create an FGM indicator

**<font color="#00008B">POST</font>** /Flag

**Request body**

A FHIR Flag conforming to the UKCore-Flag profile. Values set as per {{pagelink:Home/Design/Data-mapping.page.md}}
- {{pagelink:Home/Examples/Example---An-active-FGM-flag.page.md}} 

<br>
<br>
{{render:fgm-is-interactions-post}}
<br>
<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Flag added       | Flag - {{pagelink:Home/Examples/Example---An-active-FGM-flag.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}

<br>

### Remove an FGM indicator

**<font color="#00008B">PUT</font>** /Flag/&lt;id&gt;

**Parameters**

The id of the Flag resource being updated (marked as removed).
- id (required)

**Request body**

A FHIR Flag conforming to the UKCore-Flag profile. Values set as per {{pagelink:Home/Design/Data-mapping.page.md}}
- the id element value must be identical to the [id] in the URL
- the status must be set to either 'inactive' or 'entered-in-error'.
- {{pagelink:Home/FHIRAssets/AllAssets/Extension/Extension-England-RemovalReason.page.md}} must be included. 
-  The Flag resource being updated (signified by [id]) must have a current server status of 'active'. No changes will be persisted to a Flag which has already been removed.
- The PUT interaction only supports updates to status and delete reason. Other fields should be supplied but will not be updated.
- {{pagelink:Home/Examples/Example---A-removed-FGM-flag.page.md}}

<br>
<br>
{{render:fgm-is-interactions-put}}
<br>
<br>

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Flag removed       | Flag - {{pagelink:Home/Examples/Example---A-removed-FGM-flag.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

