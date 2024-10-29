## {{page-title}}

### Entity Model

<plantuml>
@startuml

class Task <<entity>> {
identifier 1..*
status 1..1
intent 1..1
instantiatesCanonical: Used to provide supplemental information on the code, it describes the activity. 
code 1..1
focus: Request or Event resource
for 1..1 : Patient
for.identifier 0..1 : Mandatory for events, optional on APIs
requester 1..1
requester.identifier 0..1 : Mandatory for events, optional on APIs
owner 0..1
owner.identifier 0..1 : Mandatory for events, optional on APIs
reasonCode: recommended
}
note right 
Task is related to [[https://contsys.org/package/7+Concepts+related+to+activities Contsys ISO 13940:2016 Activities]]
end note

class "[[https://www.datadictionary.nhs.uk/data_elements/nhs_number.htm NHS Number]]" as NHSNumber <<identifier>> {

}

class "[[https://www.datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html GeneralMedicalPractitionerPPDCode]]" as GeneralMedicalPractitioner  <<identifier>>

class "[[https://www.datadictionary.nhs.uk/data_elements/consultant_code.htm ConsultantCode]]" as ConsultantCode  <<identifier>>

class "[[https://www.datadictionary.nhs.uk/attributes/organisation_code.html OrganisationCode]]" as OrganisationCode  <<identifier>>

class Code <<value>> {
SNOMED CT - Do we have a refset or ecl for these activity codes?
[[https://hl7.org/fhir/R4/valueset-task-code.html Task Code]]
}

class Focus <<value>> {
SNOMED CT - The code of the FHIR Resource 
FHIR Request or Event resource : A resource may not always be possible
}

Task "for.identifier" --> NHSNumber

Task "requester.identifier" --> ConsultantCode
Task "requester.identifier" --> GeneralMedicalPractitioner
Task "requester.identifier" --> OrganisationCode

Task "code" -u-> Code 
Task "focus" -u-> Focus

@enduml 
</plantuml>

### State Diagram

<plantuml>
@startuml

state stats as "Task.status" {
[*] --> requested

rejected : businessStatus = not-longer-registered
completed : businessStatus = proxy-approved
completed : businessStatus = proxy-rejected
cancelled : businessStatus = proxy-withdrew-request

requested -> rejected
requested -> accepted
accepted -> completed
accepted -> cancelled
requested -> cancelled

completed --> [*]
cancelled --> [*]
}
@enduml
</plantuml>

### Examples

- {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Requested.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Accepted.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Completed.page.md}}
- {{pagelink:Home/FHIR-Assets/Examples/Task-Consent-Verification-Rejected.page.md}}
