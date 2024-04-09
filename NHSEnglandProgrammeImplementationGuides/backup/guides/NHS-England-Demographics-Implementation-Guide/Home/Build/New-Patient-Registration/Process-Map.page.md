## {{page-title}}

This page is to aid vendors in creating a new patient within PDS.

[PDS FHIR - NHS Number Allocation Analysis](https://nhsd-confluence.digital.nhs.uk/display/DEMGRPH/PDS+FHIR+-+NHS+Number+Allocation+Analysis)

<table class="assets" title="PDS New Patient Framework, interaction and profile">
<tr>
<th>Framework</th>
<th>FHIR Interaction</th>
<th>FHIR Profile</th>
</tr>
<tr>
<td>n/a</td>
<td><a href="https://hl7.org/fhir/R4/http.html">RESTful API</a></td>
<td>{{pagelink:Profile-England-Patient-PDS}}</td>
</tr>
</table>

<plantuml>
@startuml


title NHS Number Allocation

start
:NHS Number Allocation Request;
switch (Existing PDS record found?)
case ( Found )
  :Response with error code;
case ( Not found )
  :Create PDS record;
endswitch
stop

@enduml
</plantuml>

<plantuml>
@startuml

hide footbox

title "Patient Identity Feed plus Notifications"

participant "PDS Consumer Source" as PIXSource
participant "PDS" as PIXManager

PIXSource -> PIXManager :  PDS Advanced Trace Querys
PIXManager --> PIXSource : Response
opt No matching Patient
  PIXSource -> PIXManager: PDS NHS Number Allocation Request
  PIXManager --> PIXSource : PDS NHS Number Allocation Request Accepted/Rejected
else Matching Patient - Update Demographics
  PIXSource -> PIXManager: PDS Updating patient details
  PIXManager --> PIXSource : Response
end


@enduml
</plantuml>

---

