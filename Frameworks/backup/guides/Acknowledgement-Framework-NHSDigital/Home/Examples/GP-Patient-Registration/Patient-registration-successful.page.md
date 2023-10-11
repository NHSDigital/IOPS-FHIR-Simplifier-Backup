## {{page-title}}

### Patient registration successful

A patient goes online to register with a GP practice. A GP administrator accepts the patient's request to register.

**As a:** GP Administrator<br />
**I want to:** Accept registration messages from patients not currently registered at the GP Surgery<br />
**So that:** I can register them without additional input from sources outside my GP IT system  
<br /><br />
**Given that:** A registering individual is not currently registered at the GP Surgery<br />
**When:** The registering individual submits the registration application<br />
**Then:** The message is accepted by the GP IT System  

<plantuml>
autonumber "Message 0 -"
participant "GP Central Registration System" as gpcentral
participant "GP Local IT System" as gplocal
gpcentral -> gplocal: Request patient registration
gplocal --> gpcentral: Request successfully received
gplocal --> gpcentral: Patient successfully registered
</plantuml>




<br /><br />

 #### An Example to Request patient registration

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:urn:uuid:6f4256fa-cd14-4f96-899e-008643d84ff8}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:urn:uuid:6f4256fa-cd14-4f96-899e-008643d84ff8}}
</div>


#### An Example to Request successfully received

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:urn:uuid:2adbf7c4-8f21-4159-8681-3f41bc06215c}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:urn:uuid:2adbf7c4-8f21-4159-8681-3f41bc06215c}}
</div>


#### An Example to Patient successfully registered

<div class="tab">
  <button class="tablinks active" onclick="openTab(event, 'JSON')">JSON</button>
  <button class="tablinks" onclick="openTab(event, 'XML')">XML</button>
</div>
<div id="XML" class="tabcontent">
{{xml:urn:uuid:c96c137d-3089-4165-8a2b-f9518d745a64}}
</div>
<div id="JSON" class="tabcontent" style="display:block">
{{json:urn:uuid:c96c137d-3089-4165-8a2b-f9518d745a64}}
</div>
