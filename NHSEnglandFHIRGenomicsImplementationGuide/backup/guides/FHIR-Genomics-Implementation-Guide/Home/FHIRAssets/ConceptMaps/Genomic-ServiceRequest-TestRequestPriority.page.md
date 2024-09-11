---
subject: https://fhir.nhs.uk/ConceptMap/genomics-testrequestpriority
expand: yes
---


## ConceptMap Genomic Test Request Priority
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
<h4><a href='https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/genomics-testrequestpriority/~issues?level=File' target="_blank">Propose a change to  ConceptMap Genomic Test Request Priority </a></h4>
</div>

---