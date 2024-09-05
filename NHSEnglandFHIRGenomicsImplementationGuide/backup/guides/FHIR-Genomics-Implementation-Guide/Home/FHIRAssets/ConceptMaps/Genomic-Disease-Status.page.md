---
subject: https://fhir.nhs.uk/ConceptMap/genomics-disease-status
expand: yes
---


## ConceptMap Genomic Disease Status
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
<h4><a href='https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/genomics-disease-status/~issues?level=File' target="_blank">Propose a change to  ConceptMap Genomic Disease Status </a></h4>
</div>

---