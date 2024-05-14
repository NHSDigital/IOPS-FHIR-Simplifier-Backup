## {{page-title}}

The expected end-to-end process for the Register with a GP Surgery is detailed below:

<plantuml>
@startuml

scale 1/2

title "Register with a GP Surgery "

participant "Patient" as Pat
participant "Register with a GP Surgery Service" as GPReg
participant "Personal Demographics Service" as PDS
participant "Multicast Notification Service" as MNS
participant "Winning GP Practice" as GPWin
participant "Losing GP Practice" as GPLos
participant "PCRM (NHAIS)" as PCRM

== Trigger GP Registration ==

Pat -> GPReg : Filled GP Reg Form
activate GPReg
Alt Auto Accept
GPReg -> PDS : FHIR Update Patient (mobile, landline, email, address)
activate PDS
PDS -> PDS : Update (address, contact)
deactivate PDS
GPReg -> MNS : Trigger Event (Registration Request)
activate MNS
MNS -> MNS : Create Event (Registration Request)
MNS -> GPWin : Event Notification (ASID, Type, NHS No, ODS Code)
activate GPWin
deactivate MNS
else Not Auto Accept
GPReg -> GPWin : Email
deactivate GPReg
end

== Create Patient ==

Alt NHSNo
GPWin -> PDS : FHIR Get Patient (NHS No)
activate PDS
PDS --> GPWin : Response (Name, DoB, Gender, Contact)
deactivate PDS
else Search
GPWin -> PDS : FHIR Search Patient (Demographic Details)
activate PDS
PDS --> GPWin : Response (Name, DoB, Gender, Contact)
deactivate PDS
end
deactivate GPWin

== BAU ==

GPWin -> PCRM : GPLinks (Patient Accepted)
activate PCRM
PCRM -> PCRM : Exception Check
PCRM -> PDS : HL7v3 Update (NHS No)
deactivate PCRM
GPWin -> GPLos : GP2GP (Get Record)
activate GPWin
activate GPLos
GPLos -> GPWin : GP2GP (Transfer Record)
deactivate GPLos
deactivate GPWin

@enduml
</plantuml>