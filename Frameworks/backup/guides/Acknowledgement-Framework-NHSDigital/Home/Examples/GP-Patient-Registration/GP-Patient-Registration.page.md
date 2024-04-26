## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

This page shows examples supported by the specification. Examples should be as comprehensive as possible to aid developers.

Subpages may be added for navigation for example for Clinical scenarios. 

### Background

These are a collection of use case examples specific for GP Patient Registration. This includes positive and negative acknowledgement responses. This is to illustrate how the generic and agnostic Acknowledgement Framework can support a specific project use case.

This use case uses the Messaging paradigm within FHIR.  

<plantuml>
skinparam actorStyle awesome
left to right direction
actor "GP Administrator" as gpadmin
actor "Patient" as patient
package "GP Local System" as gplocalsys {
  usecase "Accept GP Registration" as acc
  usecase "Reject GP Registration" as rej
}
package "GP Registration Central System" as gpregsys {
  usecase "Request GP Registration"as req

}
patient --> req
gpadmin --> acc
gpadmin --> rej
</plantuml>


## Use Case Examples






