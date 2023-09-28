---
topic: Profile-Location-9738cf88-9ba3-4fc6-8efb-58b9583498f2
---
## StructureDefinition-UKCore-Location

Defines the UK Core constraints and extensions on the Location resource for the minimal set of data to query and retrieve location information.

## Profile Purpose
This profile can be used to exchange details and position information for a physical place where services are provided and resources and participants may be stored, found, contained, or accommodated. The location includes both incidental locations (a place which is used for healthcare without prior designation or authorisation) and dedicated, formally appointed locations. Locations may be private, public, mobile or fixed and scale from small freezers to full hospital buildings or parking garages.


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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Location, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>SJUH Location</b> -  An example to illustrate a Cardiology department in a hospital<br/>
{{pagelink:ExampleUKCore-Location-SJUH}}
 <br/> 
 <b>General Practice Nurse Clinic location</b> - An example to illustrate a General Practice Nurse Clinic<br/>
 {{pagelink:ExampleUKCore-Location-GeneralPracticeNurseClinic}}
<br/>
</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Location profile:

- To describe care locations such as hospital wards
- To describe locations where patient care has or may take place, including scenes of accidents like by the side of a road.

---
## Profile specific implementation guidance: ##

### Minimal Viable Content

As a minimum either a `Location.identifier` or `Location.name` should be provided.

All other elements are optional.

---