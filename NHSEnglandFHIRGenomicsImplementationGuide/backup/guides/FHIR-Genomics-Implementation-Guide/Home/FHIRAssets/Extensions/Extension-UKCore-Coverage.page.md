---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Coverage
issue: Extension-UKCore-Coverage
example: Example-UKCore-Extension-Coverage
expand: yes
---


## {{variable:issue}} 

<h2 id='non-fql-header'>Usage</h2>

This extends the Service Request Resource to support the exchange of information describing the method of funding for the Service Request.

<div id='extensionContextofUse'>
<div id='extension-Context-Use-title'>
Context of Use
</div>
<div id='extension-Context-Use-Profiles'>
{{pagelink:Profile-UKCore-ServiceRequest,text:ServiceRequest}}
</div>
</div>


{{page:Home-FHIRAssets-Extensions-ExtensionTemplate}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Coverage</b>- An example to illustrate the extension for a service request, to state the the coverage of the funding for this request.<br>
{{page:Home-Template-UKCoreExamplePageLink}}
<br><br>
</div>



<div id="Feedback" class="tabcontent">

{{page:Home-FeedbackTemplate-FeedbackLink}}

</div>

<h3 id="guidance-coverage">Extension Specific Guidance</h3>

There is a binding within this extension to a {{pagelink:ValueSet-Genomic-Coverage}}.

---