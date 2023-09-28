---
topic: Profile-MessageHeader-2af0a75b-3de6-42fa-8c05-03a0c1d142c5
---
## StructureDefinition-UKCore-MessageHeader

Defines the UK Core constraints and extensions on the MessageHeader resource for the minimal set of data to be present in a message header.

## Profile Purpose

This profile carries the header data for a message exchange that is either requesting or responding to an action.

More information on FHIR messaging is available in the <a href="http://hl7.org/fhir/R4/messaging.html">FHIR Standard.</a>

## Extending the MessageHeader Resource
There are two extensions to UK Core currently recommended for the UKCore-MessageHeader Profile. 

- One is a extension which acts as a placeholder to allow the MessageHeader to be extended in the short term as required by local use cases. This will use a code value pair approach without any coded values defined. This extension, if deemed useful will then be made into a more defined extension (with a tighter binding to an agreed ValueSet) when the use cases become clearer. One potential use of this extension is for a replacement for the approach used for ITK3 FHIR documents.
- The other is a HL7 common extension {{pagelink:CommonExtensionmessageheader-response-request}} that is used to indicate the response required to a message. 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important note regarding:{{pagelink:CommonExtensionmessageheader-response-request}}. </h4>This extension is defined as having a root conformance of 1..1 which mandates the use of the extension if added to any profile. Discussion with the FHIR community suggests this may be an error and therefore this extension is not hardcoded in the profile as this is not the desired behaviour. This issue is to be followed up with the FHIR community to try to get this corrected / clarified. 
</div>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

{{pagelink:ExampleUKCore-MessageHeader-Discharge}}

</div>

### Profile Minimum Viable Content

**Each MessageHeader resource must have:**

- An event

**Each MessageHeader resource should support:**

- A sender
- An author
- A destination

---


## Profile specific implementation guidance: ##
