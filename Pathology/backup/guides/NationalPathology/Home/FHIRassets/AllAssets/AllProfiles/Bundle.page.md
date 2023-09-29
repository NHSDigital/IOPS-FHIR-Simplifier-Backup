---
topic: Bundle
---
## Bundle

The Pathology implementation uses the StructureDefinition Bundle which is profiled as below

## UKCore-Bundle ##

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Bundle, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>

{{pagelink:PathologyBundleProstrate-SpecificAntigenTestExample}}

{{pagelink:PathologyBundleRenalFunctionTestsExample}}

</div>

## Conformance Rules ##

Conformance rules to be applied to the UKCore-Bundle profile to represent a valid instance for the National Pathology exchange of information.

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-Bundle profile |
|--
||||To be defined|