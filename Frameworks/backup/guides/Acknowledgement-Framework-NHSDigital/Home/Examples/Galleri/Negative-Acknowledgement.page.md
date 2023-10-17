## {{page-title}}

### Negative Acknowledgement of Appointment - Incorrect Data Format

The appointment from GRAIL (UK) should be in a JSON format. However, the appointment message sent to NHS England (GPS) was sent in an XML format. So a negative acknowledgement is sent to GRAIL (UK).

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send appointment
nhsenglandgps --> grailuk: Send negative acknowledgement
</plantuml>

<br /><br />
#### An Example to Send Appointment

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent" style="display:block">
{{xml:f50c58ea-543f-4530-99fa-ceb7b9dbbed5}}
</div>
</div>

<br /><br />
#### An Example to Receive Negative acknowledgement response

<div>
<div class="tab">
<button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
 <button class="tablinks" onclick="openTab(event, 'XML')">XML</button> 
</div>
<div id="XML" class="tabcontent">
{{xml:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1d}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1d}}
</div>
</div>

<br /><br />
### Negative Acknowledgement of Test Result (Cancer Markers Detected) - Missing Mandatory Element 

The test result from GRAIL (UK) should include all FHIR elements that are mandatory (with a minimum cardinality of 1). However, the test result sent to NHS England (GPS) is missing a FHIR element that is mandatory. So a negative acknowledgement is sent to GRAIL (UK).

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send bio-sampling test report
nhsenglandgps --> grailuk: Send negative acknowledgement
</plantuml>

<br /><br />
#### An Example of Sending bio-sampling test report

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:f862ec24-e05a-42d1-aea5-d0a9c092e6ae}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:f862ec24-e05a-42d1-aea5-d0a9c092e6ae}}
</div>
</div>

<br /><br />
#### An Example to Receive Bio Sampling Test Report Negative acknowledgement response

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:cf09cccc-2c9b-4238-91d2-66fa6ee845d3}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:cf09cccc-2c9b-4238-91d2-66fa6ee845d3}}
</div>
</div>
