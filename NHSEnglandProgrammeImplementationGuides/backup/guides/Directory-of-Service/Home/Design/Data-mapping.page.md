## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

## FHIR Model

- An Organization has an OrganizationAffiliation with another Organization
- An Organization has Location(s)
- A Location provides HealthcareService(s)
- A HealthcareService has a Schedule for the services it provides
- A Schedule contains Slot(s) that are available for the HealthcareService
- A Schedule has a PratitionerRole/Practitioner that can be referenced

## Organization, Location and HealthcareService (Searching)

<plantuml>
@startuml
Organization "1" *-- "many" OrganizationAffiliation : has
Organization "1" *-- "many" Location : exists at
Location "1" *-- "many" HealthcareService : provides
@enduml
</plantuml>

# Searching the DoS
For systems that don't require booking

### Organization (1..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>0..1</td>
    <td>Organization.name</td>
    <td>Name used for the organization</td>
  </tr>
  <tr>
    <td>Address</td>
    <td>0..*</td>
    <td>Organization.address</td>
    <td>An address for the organization</td>
  </tr>
</tbody>
</table>

### OrganizationAffiliation (0..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Organization</td>
    <td>0..1</td>
    <td>OrganizationAffiliation.organization Reference(Organization)</td>
    <td>Organization where the role is available</td>
  </tr>
</tbody>
</table>

### Location (1..*)

Describe the location from which the HealthcareService is offered

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>0..1</td>
    <td>Location.name</td>
    <td>Name of the location as used by humans</td>
  </tr>
  <tr>
    <td>Position</td>
    <td>0..1</td>
    <td>Location.position</td>
    <td>The absolute geographic location</td>
  </tr>
  <tr>
    <td>Position longitude</td>
    <td>1..1</td>
    <td>Location.position.longitude</td>
    <td>Longitude with WGS84 datum</td>
  </tr>
  <tr>
    <td>Position latitude</td>
    <td>1..1</td>
    <td>Location.position.latitude</td>
    <td>Latitude with WGS84 datum</td>
  </tr>
  <tr>
    <td>Location of Organization</td>
    <td>1..1</td>
    <td>Location.managingOrganization Reference(Organization)</td>
    <td>The Organization the location belongs to</td>
  </tr>

  
</tbody>
</table>

### HealthcareService (1..*)

Details about the service, including the days, times, dates during which the service is open.

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Name</td>
    <td>0..1</td>
    <td>HealthcareService.name</td>
    <td>Description of service as presented to a consumer while searching</td>
  </tr>
  <tr>
    <td>Provided by</td>
    <td>0..1</td>
    <td>HealthcareService.providedBy Reference(Organization)</td>
    <td>Organization that provides this service</td>
  </tr>
  <tr>
    <td>Location of service</td>
    <td>0..*</td>
    <td>HealthcareService.location Reference(Location)</td>
    <td>Location(s) where service may be provided</td>
  </tr>
  <tr>
    <td>Category</td>
    <td>0..*</td>
    <td>HealthcareService.category</td>
    <td>Broad category of service being performed or delivered</td>
  </tr>
  <tr>
    <td>Type</td>
    <td>0..*</td>
    <td>HealthcareService.type</td>
    <td>Type of service that may be delivered or performed</td>
  </tr>
  <tr>
    <td>Available Times</td>
    <td>0..*</td>
    <td>HealthcareService.availableTime</td>
    <td>Times the Service Site is available</td>
  </tr>
  <tr>
    <td>Times not available</td>
    <td>0..*</td>
    <td>HealthcareService.notAvailable</td>
    <td>Not available during this time due to provided reason</td>
  </tr>
  <tr>
    <td>Coverage area</td>
    <td>0..*</td>
    <td>HealthcareService.coverageArea Reference(Location)</td>
    <td>Location(s) service is intended for/available to</td>
  </tr>
</tbody>
</table>

# Booking through the DoS
For systems that require a booking, these resources are added

## Organization, Location and HealthcareService with Schedule and Slot (Booking)

<plantuml>
@startuml
Organization "1" *-- "many" OrganizationAffiliation : has
Organization "1" *-- "many" Location : exists at
Location "1" *-- "many" HealthcareService : provides
HealthcareService "1" *-- "many" Schedule : offers
Schedule "1" *-- "1" PractitionerRole : relate to
PractitionerRole "1" *-- "many" Practitioner : performs role of
Schedule "1" *-- "many" Slot : has
@enduml
</plantuml>

### Schedule (0..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Actor</td>
    <td>1..*</td>
    <td>Schedule.actor.HealthcareService</td>
    <td>Resource(s) that availability information is being provided for</td>
  </tr>
  <tr>
    <td>Actor</td>
    <td>1..*</td>
    <td>Schedule.actor.PractitionerRole</td>
    <td>Resource(s) that availability information is being provided for</td>
  </tr>
</tbody>
</table>

### Slot (0..*)

The dates and times a service is available to be returned in a search.

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Reference(Schedule)</td>
    <td>1..1</td>
    <td>Slot.schedule</td>
    <td>The schedule resource that this slot defines an interval of status information</td>
  </tr>
  <tr>
    <td>Start</td>
    <td>1..1</td>
    <td>Slot.start</td>
    <td>Date/Time that the slot is to begin</td>
  </tr>
  <tr>
    <td>End</td>
    <td>1..1</td>
    <td>Slot.end</td>
    <td>Date/Time that the slot is to conclude</td>
  </tr>
</tbody>
</table>

### PractitionerRole (0..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Code</td>
    <td>0..*</td>
    <td>PractitionerRole.code</td>
    <td>Roles which this practitioner may perform</td>
  </tr>
</tbody>
</table>

### Practitioner (0..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Practitioner name</td>
    <td>0..1</td>
    <td>Practitioner.name</td>
    <td>The name(s) associated with the practitioner</td>
  </tr>
</tbody>
</table>

### Endpoint (0..*)

<table class="assets">
<thead>
  <tr>
    <th>Source Data item</th>
    <th>Cardinality</th>
    <th>Target FHIR Element</th>
    <th>Notes</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Status</td>
    <td>1..1</td>
    <td>Endpoint.status</td>
    <td>The status of the Endpoint</td>
  </tr>
  <tr>
    <td>Connection type</td>
    <td>1..1</td>
    <td>Endpoint.connectionType</td>
    <td>Protocol/Profile/Standard to be used with this endpoint connection</td>
  </tr>
  <tr>
    <td>Payload type</td>
    <td>1..*</td>
    <td>Endpoint.payloadType</td>
    <td>The type of content that may be used at this endpoint (e.g. XDS Discharge summaries)</td>
  </tr>
  <tr>
    <td>Address</td>
    <td>1..1</td>
    <td>Endpoint.address</td>
    <td>The technical base address for connecting to this endpoint</td>
  </tr>
</tbody>
</table>