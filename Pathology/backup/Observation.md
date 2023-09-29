## Observation

The Pathology implementation uses the StructureDefinition Observation Profiled as UKCore-Observation as below:

## UKCore-Observation ##

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation, snapshot}}

 ## Conformance Rules ##

Conformance rules to be applied to the UKCore-Observation profile to represent a valid instance for the National Pathology exchange of information.

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Observation profile |
|--
||||To be defined|