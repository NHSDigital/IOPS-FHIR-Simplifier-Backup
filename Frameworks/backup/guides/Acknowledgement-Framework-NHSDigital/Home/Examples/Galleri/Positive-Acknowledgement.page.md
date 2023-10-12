## {{page-title}}

### Positive Acknowledgement of Appointment

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send appointment
nhsenglandgps --> grailuk: Send positive acknowledgement
</plantuml>

<br /><br />
## An Example to Send Appointment

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1c}}
</div>
<div id="XML" class="tabcontent">
{{xml:6e7b1dbb-77d2-4ddd-ae0d-e4862a306c1c}}
</div>
</div>

<br /><br />
#### An Example to Receive positive acknowledgement response

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:aa09cccc-2c9b-4238-91d2-66fa6ee845e3}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:aa09cccc-2c9b-4238-91d2-66fa6ee845e3}}
</div>
</div>

### Positive Acknowledgement of Test Report (Cancer Markers Detected)

<plantuml>
autonumber "Message 0 -"
participant "NHS England (GPS)" as nhsenglandgps
participant "GRAIL (UK)" as grailuk
nhsenglandgps <- grailuk: Send test report with cancer markers detected
nhsenglandgps --> grailuk: Send positive acknowledgement
</plantuml>

<br /><br />
#### An Example to Send test report (cancer markers detected)

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:b4409d7c-b613-477c-b623-87e60406c2f0}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:b4409d7c-b613-477c-b623-87e60406c2f0}}
</div>
</div>

#### An Example to Receive test report positive acknowledgement response

<div>
<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:ff09cccc-2c9b-4238-91d2-66fa6ee845d3}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:ff09cccc-2c9b-4238-91d2-66fa6ee845d3}}
</div>
</div>
