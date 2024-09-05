---
subject: https://fhir.nhs.uk/ConceptMap/primarysample
expand: yes
---


## ConceptMap Genomic Specimen Primary Sample
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
<h4><a href='https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/genomics-primarysample/~issues?level=File' target="_blank">Propose a change to  ConceptMap Genomic specimen Primary Sample </a></h4>
</div>

---