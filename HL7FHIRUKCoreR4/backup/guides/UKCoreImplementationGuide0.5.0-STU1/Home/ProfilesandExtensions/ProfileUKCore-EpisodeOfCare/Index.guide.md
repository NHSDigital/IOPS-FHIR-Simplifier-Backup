---
topic: Profile-EpisodeOfCare-8410fd46-fa56-4bf8-8db5-82e67587e005
---
## StructureDefinition-UKCore-EpisodeOfCare

Defines the UK Core constraints and extensions on the EpisodeOfCare resource for the minimal set of data to query and retrieve episode of care information.

## Profile Purpose
This profile allows exchange of information about an association between a patient and an organisation / healthcare provider(s) during which time encounters may occur. The managing organisation assumes a level of responsibility for the individual during this time.

## Relationship to Encounter

The EpisodeOfCare Resource contains information about an association of a Patient with a Healthcare Provider for a period of time under which related healthcare activities may occur.

In many cases, this represents a period of time where the Healthcare Provider has some level of responsibility for the care of the patient regarding a specific condition or problem, even if not currently participating in an encounter.

These resources are typically known in existing systems as:

- **EpisodeOfCare:** Case, Program, Problem, Episode
- **Encounter:** Visit, Contact.

<br/>

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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-EpisodeOfCare, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

{{pagelink:ExampleUKCore-EpisodeOfCare-SmokingCessationTherapy-050}}

</div>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core EpisodeOfCare profile:

- Query for information about an episode of care associated with a patient
- Record or update information about an episode of care for a patient

### Profile Minimum Viable Content  ###

**Each EpisodeOfCare resource must have:**
- A status
- A subject
- A type

**Each EpisodeOfCare resource should support:**
- A diagnosis
- A referralRequest


## Profile specific implementation guidance: ##

---
