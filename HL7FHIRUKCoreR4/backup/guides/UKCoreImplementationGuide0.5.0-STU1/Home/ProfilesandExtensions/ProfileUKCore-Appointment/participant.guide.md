## <code>{{page-title}}</code>

Mandatory list of participants involved in the appointment.

`participant.type`

Optional role of participant in the appointment.

This element currently uses the FHIR extensible <a href="https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/79969">Participant Type ValueSet</a> as no UK Core ValueSet has been defined. The ValueSet contains the following concepts:
- secondary performer
- primary performer
- Participation
- admitter
- attender
- callback contact
- consultant
- discharger
- Emergency
- escort
- referrer
- Translator

`participant.actor`

Optional Person, Location/HealthcareService or Device that is participating in the appointment.

The resource being referenced should conform to one of the following:

- {{pagelink:Profile-Location-9738cf88-9ba3-4fc6-8efb-58b9583498f2}}
- {{pagelink:Profile-HealthcareService-83c4b098-a858-4717-b6b8-c1c101d5ea11}}
- {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}
- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}
- {{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}
- <a href="https://simplifier.net/hl7fhirukcorer4/ukcoredevice">UKCore-Device Profile</a>


`participant.required`

Whether this participant is required to be present at the meeting.

This element is optional and must use a value from the CodeSystem below:

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/participantrequired}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/participantrequired}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/participantrequired}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/participantrequired}}
</div>

<br/>

`participant.status`

Mandatory participation status of the actor.

This element must be present and use a value from the CodeSystem below:

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/participationstatus}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/participationstatus}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/participationstatus}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/participationstatus}}
</div>

<br/>

`participant.period`

Optional participation period of the actor.

---
