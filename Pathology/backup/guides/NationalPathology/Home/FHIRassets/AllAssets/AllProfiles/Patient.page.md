---
topic: Patient
---
## UK Core Patient

The Pathology implementation uses the StructureDefinition Patient profiled as UKCore-Patient as below:

## UKCore-Patient

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient, snapshot}}
</div>

 ## Conformance Rules ##

Conformance rules to be applied to the UKCore-Patient profile to represent a valid instance for the National Pathology exchange of information.

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Patient profile |
|--
||||To be defined|

