## {{page-title}}

As a consequence of supporting RESTful update operations on resources within the central broker, some information, such as patient history may change over time. This poses a problem when interrogating past 'documents', or resources such as ServiceRequests or DiagnosticReports, as the information contained within them, or the references to other resources, may change after a test request has been closed. 

To maintain the accuracy of historic information, such as the observations a genomic report was based on, it may be necessary to create an immutable snapshot of the resources related to a ServiceRequest or DiagnosticReport after closure of a request.

To support this, the central broker can create Document Bundles using the [$document](https://www.hl7.org/fhir/composition-operation-document.html) operation on [Composition](https://www.hl7.org/fhir/R4/composition.html). The Compositions would need to be generated on closure of a ServiceRequest (e.g. a ServiceRequest being marked as 'completed' or 'revoked', or a DiagnosticReport marked as 'final', 'amended', 'corrected' or 'appended') to capture the final IDs for the ServiceRequest and DiagnosticReport.

Upon generation of the Composition, the central broker can call the $document operation on the Composition resource, using the appropriate {{pagelink:Home/FHIRAssets/GraphDefinitions}} to follow the required resource references and generate a Bundle of type 'document' containing all the resources forming the order or result:

```
GET [base]/Composition/[id]/$document?persist=true&graph=genomics-test-result
```

This Bundle could then be stored/accessible via the Bundle endpoint as an immutable snapshot of the order/result at that point in time, regardless of whether any changes were made to those resources after generation:

```
GET [base]/Bundle/[id]
```

or searched via:

```
GET [base]/Bundle?composition.entry:DiagnosticReport=[id]
GET [base]/Bundle?composition.entry:ServiceRequest=[id]
```

The sequence diagram for the proposed process is given below:

<plantuml>
@startuml
scale 0.8
== Completion of Test Order ==
Participant EPR as "Requester (EPR)"
Participant GOMS as "Genomic Order Management Service Broker"
Participant LIMS as "Fulfilling Organization (GLH/LIMS)"
EPR -> GOMS : POST ServiceRequest Transaction Bundle \nmarking test as completed
GOMS -> GOMS : Create Composition with entry ServiceRequest
GOMS -> GOMS : Call $document on Composition with \n$graph?graph=genomics-test-order 
GOMS --> EPR : Transaction Response Bundle containing \ncreated resources
opt Return Final Document
GOMS --> EPR : Bundle containing \nreference to Document Bundle created
end
opt Event Notification
GOMS -> LIMS : POST event-notification Bundle \n(ServiceRequest completed)
end
== Finalisation of Genomic Report ==
LIMS -> GOMS : POST Genomic Report Transaction Bundle \nmarking report as final
GOMS -> GOMS : Create Composition with entry DiagnosticReport
GOMS -> GOMS : Call $document on Composition with \n$graph?graph=genomics-test-result 
GOMS --> LIMS : Transaction Response Bundle containing \ncreated resources
opt Return Final Document
GOMS --> LIMS : Bundle containing \nreference to Document Bundle created
end
opt Event Notification
GOMS -> EPR : POST event-notification Bundle \n(report available)
end
== Retrieval of Document (snapshot) ==
opt
EPR -> GOMS : Search for ServiceRequest to get ID 
end
EPR -> GOMS : GET Bundle?composition.entry:ServiceRequest=<id> 
GOMS --> EPR : Document Bundle response with snapshot \nof resources at time of creation
@enduml
</plantuml>