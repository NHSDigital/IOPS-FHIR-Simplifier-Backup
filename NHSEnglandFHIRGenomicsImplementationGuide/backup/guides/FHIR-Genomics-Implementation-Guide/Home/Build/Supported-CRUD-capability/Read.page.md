## {{page-title}}

From initial design work, it is expected the main use case will be labs and requestors polling the central service for test orders and reports, including associated clinical information, as well as polling the system for the current state of Tasks and Task update history, through associated AuditEvents and Provenance resources. 

Retrieval of sets of resources using {{pagelink:Home/FHIRAssets/GraphDefinitions}} are also planned. The complete set of resources/operations supported are listed within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} page. All resources are expected to be compliant with UK Core FHIR R4.

### Search

#### Supported Functionality
* The search parameters to be supported by the Genomic Order Management system are defined within the {{pagelink:Home/FHIRAssets/CapabilityStatements/Instance.page.md}} page. Custom search parameters defined within {{pagelink:Home/FHIRAssets/SearchParameters}} will also be supported, such as a search parameter for supporting retrieval of supporting-info on ServiceRequests. 

* Multiple _include/_revinclude parameters will be supported within a single URL search string. The :iterate modifier will also be supported to enable traversal of multiple levels of references in searches e.g. `GET [base]/MedicationDispense?_include=Medication:prescription&_include:iterate=MedicationRequest:requester&criteria...`. 

* The `_history` and `_lastUpdated` parameters will be supported as part of history and audit provenance needs. The `_history` parameter will only be supported on instance level reads, i.e. history will not be retrievable at the resource type or base levels.

* Token type searching for coded values based on system and/or code e.g. http://snomed.info/sct%7C3738000 will be supported, to enable unabiguous searching of codes.

* Date and number based prefixes, such as `eq`, `gr`, `lt` will be supported, to enable retrieval of resources based on date/time and quantity ranges.

* Chaining, e.g. `ServiceRequest?subject:Patient.name` will be supported to aid building of complex search criteria.

* Search result modifiers such as `_count`, `_total` and `_sort` will be supported to allow clients to tailor search results.

* The `:not` operator will be supported to allow organizations visibility of tests outside their region, e.g. for home GLHs which want to see tests from within their patch routed to labs outside their region. An example of the query to support this would be:

```
GET [base]/ServiceRequest?requester:PractitionerRole.organization={ODS_codes_in_my_patch}&performer:not={my_GLH_code}
```

#### Unsupported Functionality
* Inclusion of external references (resources not hosted on the server) through the _include parameter will not be supported as there will be no guarantee they resolve or that they will return valid FHIR. While this may mean clients will need to perform multiple calls to construct a complete set of data, this ensures consistency of the responses from the broker. Within this Implementation Guide we expect test requesters to submit all relevant information for a test order to the broker so there should be very few instances where an external reference is used.

* No use cases requiring use of `_query` or `$operation` type searches have been elaborated so these are not planned to be supported as of the time of publication. Equally, usage of tags to encode data, and use of the `_tag` parameter will not be supported until use cases detailing their need are elaborated.

* Search modifiers such as `:contains`, `:missing`, `:not-in`, etc. will not be supported as there are currently no use cases for supporting text-based/fuzzy searching. 

### Common Patterns

<plantuml>
@startuml
scale 0.8
== Searching for Tasks by Org (Polling for tasks) ==
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
alt Only matching resources
LIMS -> GOMS : GET Task with owner=<ods_code> 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
else Additional includes
LIMS -> GOMS : GET Task with owner=<ods_code> and \n_include=Task:focus
GOMS --> LIMS : Searchset Bundle response with matching \nresources and included referenced ServiceRequests
end
== Searching for ServiceRequest by Patient ==
LIMS -> GOMS : GET ServiceRequest with subject=<nhs_number> 
GOMS --> LIMS : Searchset Bundle response with matching \nresources
== Retrieving Test Orders ==
opt
LIMS -> GOMS : Search for ServiceRequest to get ID 
end
LIMS -> GOMS : GET ServiceRequest/<id>/ with \n$graph?graph=genomics-test-order 
GOMS --> LIMS : Collection Bundle response with resources \nreferenced in the graph
== Retrieving DiagnosticReport by ID ==
alt Using report endpoint
EPR -> GOMS : Search for DiagnosticReport to get ID 
else Using task endpoint
EPR -> GOMS : Search for Tasks with focus=ServiceRequest
EPR -> EPR : Parse link in Task.output to get ID
end
alt Unstructured Report
EPR -> GOMS : GET DiagnosticReport using ID
GOMS --> EPR : DiagnosticReport
EPR -> EPR : Follow link to retrieve PDF \nor decode base65 encoded data
else Structured Reports
EPR -> GOMS : GET DiagnosticReport/<id>/ \n with $graph?graph=genomics-result 
GOMS --> EPR : Collection Bundle response with resources \nreferenced in the graph
end
@enduml
</plantuml>