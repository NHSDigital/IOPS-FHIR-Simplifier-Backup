## {{page-title}}


### Entity Model

<plantuml>
@startuml

class Task <<entity>> {
identifier 1..*
status 1..1
intent 1..1
instantiatesCanonical 0..1 : Used to provide supplemental information on the code. 
for : PatientReference
code 1..1
focus: 
requester 1..1: PractitionerReference  or OrganizationReference
owner 0..1: OrganizationReference
reason[x] 0..1 : recommended
}
note right 
Task is used to arrange activities referenced in
[[https://contsys.org/package/7+Concepts+related+to+activities Contsys ISO 13940:2016 Activities]]
end note


class code <<value>> {
[[https://hl7.org/fhir/R4/valueset-task-code.html Task Code]] and UK SNOMED CT : \nDo we have a refset or ecl for these activity codes?

}

class focus <<reference>> {
reference: to FHIR Resource
codeableConcept: Should we also includes UK SNOMED CT?
externally referenced resources may not be easy to resolve
and a SNOMED CT may be sufficient for users. 
}

class PatientReference <<identifier>> {
  identifier: [[https://www.datadictionary.nhs.uk/data_elements/nhs_number.htm NHS Number]] Mandatory if known, when \nsending data to another organisation
}

class PractitionerReference <<identifier>> {
identifier: [[https://www.datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html GeneralMedicalPractitionerPPDCode]] or [[https://www.datadictionary.nhs.uk/data_elements/consultant_code.htm ConsultantCode]].\nMandatory if known, when sending data to another organisation
}

class OrganizationReference <<identifier>> {
  identifier: [[https://www.datadictionary.nhs.uk/attributes/organisation_code.html OrganisationCode]].\nMandatory if known, when sending data to another organisation
}

Task "for" --> PatientReference

Task "requester" --> PractitionerReference
Task "requester" --> OrganizationReference

Task "owner" --> OrganizationReference

Task "code" -u-> code 
Task "focus" -u-> focus

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
