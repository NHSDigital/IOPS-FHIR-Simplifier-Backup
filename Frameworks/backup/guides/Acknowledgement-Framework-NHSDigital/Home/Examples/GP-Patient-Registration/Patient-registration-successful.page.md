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

 #### An Example Of Patient Registration Request

<div>
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'XML')">XML</button>
 <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="XML" class="tabcontent" style="display:block">
{{xml:6f4256fa-cd14-4f96-899e-008643d84ff8}}
</div>
<div id="JSON" class="tabcontent">
{{json:6f4256fa-cd14-4f96-899e-008643d84ff8}}
</div>
</div>


#### An Example of Patient Registration Request successfully received

<div>
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'XML')">XML</button>
  <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="XML" class="tabcontent" style="display:block">
{{xml:2adbf7c4-8f21-4159-8681-3f41bc06215c}}
</div>
<div id="JSON" class="tabcontent">
{{json:2adbf7c4-8f21-4159-8681-3f41bc06215c}}
</div>
</div>


#### An Example of Patient successfully registered

<div>
<div class="tab">
<button class="tablinks active" onclick="openTab(event, 'XML')">XML</button>
  <button class="tablinks" onclick="openTab(event, 'JSON')">JSON</button>
</div>
<div id="XML" class="tabcontent" style="display:block">
{{xml:c96c137d-3089-4165-8a2b-f9518d745a64}}
</div>
<div id="JSON" class="tabcontent">
{{json:c96c137d-3089-4165-8a2b-f9518d745a64}}
</div>
</div>
