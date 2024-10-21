---
subject: https://fhir.nhs.uk/ConceptMap/genomics-primary-sample-state
expand: yes
---


## ConceptMap Genomic Specimen Primary Sample State
<fql>
from
	ConceptMap
where
  url=%subject
  select
    Usage:purpose
</fql>

{{render:Home-FHIRAssets-ConceptMaps-ConceptMapTemplate}}

<div id="Feedback" class="tabcontent">
<h4><a href='https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/genomics-primary-sample-state/~issues?level=File' target="_blank">Propose a change to  ConceptMap Genomic specimen Primary Sample State</a></h4>
</div>

---