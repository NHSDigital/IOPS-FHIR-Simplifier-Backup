## Patient Flag Data Model

A Patient Flag API record is made up of a PatientFlag resource and any other additional resources that provide supplementary information.

<plantuml>
@startuml
skinparam linetype ortho

entity "Patient" as pat {
  *NHS Number : number <<generated>>
}
package "Patient Flags API" {

entity "Patient Flag" as pfg {
  *patient : Patient
  *code : CodeableConcept
  *category : CodeableConcept
}

package "Additional Detail" as AD {

entity "Resource (Any)" as res {
}

}
}

pat ||--o{ pfg : has
pat ||--o{ res : provides
pfg ||..o{ res : details
@enduml
</plantuml>

## Reasonable Adjustments

The RA record is made up of PatientFlag, PatientFlagAdjustment, contained Provenance and Condition resources.  

Authorised healthcare workers can:

- Retrieve a set of top-level Patient Flags (just the Patient Flags with no associated resources)
- Retrieve a specific Reasonable Adjustment Flag with associated resources
- Add a top-level Reasonable Adjustment Flag
- Add a top-level Patient Flag (and associated Adjustment, Impairment or Condition resources)
- Add/remove associated resources (with the dependency that a top-level flag must already be added/removed)
- Remove a top-level Patient Flag (which will remove all associated resources)

The presence of and entitlement to reasonable adjustments is represented by a PatientFlag resource. It can be interpreted as meaning 'this patient has reasonable adjustments'.

Individual adjustments are represented as ProgrammeFlag resource instances. They can be interpreted as meaning e.g.'this patient requires Easy read'.

Patients may record Impairments for which they wish to have reasonable adjustments applied as Condition resources. Patients may optionally request details of underlying conditions are recorded and shared where this enhances healthcare. These too are represented as Condition resources.

Provenance of all resources that make up an RA record must be stored.  This is modelled here as a contained resource, and as such has no lifetime outside of the constituent RA record resources.

<plantuml>
@startuml

skinparam linetype ortho

entity "Patient" as pat {
  *NHS Number : number <<generated>>
}
package "Patient Flags API" {

entity "Patient Flag" as pfg {
  *patient : Patient
  *code : CodeableConcept
  *category : CodeableConcept
  *contained : Provenance (Contained)
}

package "Additional Detail" {

entity "Condition" as cod {
  *patient : Patient
  *code : CodeableConcept
  *category : CodeableConcept
  *contained : Provenance (Contained)
}

entity "Patient Flag Adjustment" as prfg {
  *patient : Patient
  *code : CodeableConcept
  *category : CodeableConcept
  *contained : Provenance (Contained)
}

entity "Provenance" as prov {
  *recorded : Date
  *agent : Agent (backbone)
}
}
}

pat ||--o{ cod : has
pat ||--o| pfg : has
pat ||--o{ prfg : has
cod ||--|| prov : contains
pfg ||--|| prov : contains
prfg ||--|| prov : contains
pfg ||..o{ prfg : details

@enduml
</plantuml>


## Female Genital Mutilation

The FGM record is made up of a PatientFlag resource and a contained Provenance.

Authorised healthcare workers can:

- query to determine if a patient has a FGM family history indicator
- create a FGM family history indicator for a patient
  - must be gender `female`, `unknown` or `indeterminate` according to PDS
  - must be under the age of 18 according to PDS
  - must not already have a FGM family history indicator on FGM-IS
  - must have a verified NHS number
- delete a FGM family history indicator for a patient

The FGM PatientFlag resource is interpreted as:
- an indicator that a child with female genitalia has a family history of FGM
- the date that the FGM assessment was carried out

Provenance of the resource that makes up an FGM record must be stored.  This is modelled here as a contained resource, and as such has no lifetime outside of the constituent FGM record resource.


<plantuml>
@startuml

skinparam linetype ortho

entity "Patient" as pat {
  *NHS Number : number <<generated>>
}
package "Patient Flags API" {

entity "Patient Flag" as pfg {
  *patient : Patient
  *code : CodeableConcept
  *category : CodeableConcept
  *contained : Provenance (Contained)
}

entity "Provenance" as prov {
  *recorded : Date
  *agent : Agent (backbone)
}

}

pat ||--o| pfg : "has"
pfg ||--|| prov : contains

@enduml
</plantuml>

## Child Protection - Information Sharing (CP-IS)

The CP-IS record is made up of a PatientFlag resource and a contained Provenance.The CP-IS service enables practitioners in unscheduled care settings to determine whether a child has an active Child Protection Plan (CPP) or is a Looked-After Child (LAC).

## Purpose


Authorized healthcare workers can:

 Query to determine if a patient has a Child Protection Plan
 * either as part of general PatientFlag query that returns all PatientFlags
 * or query for just Child Protection Plans for the patient & return all associated CarePlan and CareTeam resources


## Interpretation of the CP-IS Flag
The presence of a CP-IS flag indicates:

 - A child is subject to a Child Protection Plan or is a Looked-After Child
 - The responsible Local Authority Care Team overseeing the child's case
 - The start and end dates of the protection plan

<plantuml>
@startuml

skinparam linetype ortho

entity "Patient" as pat {
  * NHS Number : number <<generated>>
}

package "CP-IS API" {

  entity "CP-IS Flag" as flag {
    * patient : Patient
    * category : CodeableConcept
    * code : CodeableConcept (Child Protection Plan)
    * contained : Provenance (Contained)
  }

  entity "CarePlan" as careplan {
    * category: CodeableConcept (CPP | LAC | UC)
    * subject : Patient
  }

  entity "CareTeam" as careteam {
    * name : Local Authority Care Team
    * telecom : Contact Details
    * participant : Social Worker
  }

  entity "Provenance" as prov {
    * recorded : Date
    * agent : Agent (backbone)
  }

}

pat ||--o| flag : "has CP-IS flag"
flag ||--|| prov : contains
flag ||--o| careplan : "linked to"
careplan ||--o| careteam : "involves"

@enduml

</plantuml>

---
