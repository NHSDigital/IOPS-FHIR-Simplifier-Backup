## MessageHeader

The Pathology implementation uses the StructureDefinition MessageHeader profiled as UKCore-MessageHeader as below:

## UKCore-MessageHeader ##

<div class="tab">
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks active" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
  <button class="tablinks" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, diff}}
</div>

<div id="Hybrid View" class="tabcontent" style="display:block">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, hybrid}}
</div>

<div id="Snapshot View" class="tabcontent">
  <h3>Snapshot View</h3>
 {{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader, snapshot}}
</div>


## Conformance Rules ##

Conformance rules to be applied to the UKCore-MessageHeader profile to represent a valid instance for the National Pathology exchange of information.

| Source Data Item |Cardinality| Target FHIR Element | Additional Conformance on the UKCore-MessageHeader profile |
|--
|Event Type|1..1|MessageHeader.eventType.system|Must contain the value http://snomed.info/sct|
|Event Type|1..1|MessageHeader.eventType.code|Must contain the value 371528001|
|Event Type|1..1|MessageHeader.eventType.display|Must contain the value Pathology report|

