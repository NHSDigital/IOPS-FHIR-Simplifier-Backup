## {{page-title}}
### Overview

For high level requirements, see {{pagelink:Home}}.
 

### Use Case

<plantuml>
@startuml

skinparam actorStyle awesome
left to right direction

rectangle "Patient Flag (Reasonable Adjustments)"{
actor Practitioner as pra
usecase "Record" as record <<abstract>>
usecase "Remove Reasonable Adjustment record" as rem <<abstract>>
}


actor Patient as pat

usecase "Consult" as consult <<abstract>>

pat -- consult
pra -- consult
pra -- record
record <.. rem : include

@enduml
</plantuml>

### System Interactions

In the following sequence diagram, a patient and/or practitioner decide to remove the Reasonable Adjustment patient flag and all suppporting resources (Adjustments, Impairments and Underlying Conditions).

<plantuml>
@startuml

skinparam actorStyle hollow

actor        "Patient"            as pat
actor        "Practitioner"       as pra
participant  "FHIR API"           as api
entity       "Patient Flag"       as pfg
entity       "Additional Detail"  as add

  pat ->  pra : Remove
  pra ->  api : Remove
  api ->  pfg : Remove resource
  

loop for each Additional Detail resource
  api ->  add : Remove resource (any)
  add ->  add : Validate
  api <-- add : return
  alt Validation failed
    api -> api : rollback
  end
end

pra <-- api : OperationOutcome

@enduml
</plantuml>


### Queries

Using [FHIR conditional delete](http://hl7.org/fhir/r4/http.html#3.1.0.7.1) capabilities, it is possible to delete the entire Reasonable Adjustment Flag record for a given patient.

Only the top-level PatientFlag of the Reasonable Adjustment needs to be deleted (the server will delete the associated resources). A reson should be given as to why the ReasonableAdjustment has been deleted. The delete statement must include the patient's NHS Number, state that its a Reasonable Adjustment deletion, and give a reason.
```
DELETE [baseURL]\PatientFlag?patient=[NHSNumber]&code=NRAF&reason=[ReasonText]
```

#### Flag endpoint delete

Following the standard FHIR conditional delete ReST pattern `DELETE [baseURL]/[resourceType]` for delete operations, to:

#### Example

To delete a Reasonable Adjustment Flag for a patient with a NHS Number 6574636879 because the adjustments are no longer required
```
DELETE [baseURL]\PatientFlag?patient=6574636879&code=NRAF&reason=NoLongerRequired
```

---

