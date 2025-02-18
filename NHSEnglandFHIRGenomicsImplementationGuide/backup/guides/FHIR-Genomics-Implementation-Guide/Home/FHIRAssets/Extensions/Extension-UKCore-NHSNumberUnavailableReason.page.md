---
subject: https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-NHSNumberUnavailableReason
issue: Extension-UKCore-NHSNumberUnavailableReason
example: Example-UKCore-Extension-NHSNumberUnavailableReason
expand: yes
---

## {{variable:issue}}


<h2 id='non-fql-header'>Usage</h2>
This extends the Patient resource to support the exchange of information about the reason why a patient does not have an NHS Number.

<div id='extensionContextofUse'>
<div id='extension-Context-Use-title'>
Context of Use
</div>
<div id='extension-Context-Use-Profiles'>
{{pagelink:Profile-UKCore-Patient,text:Patient}}
</div>
</div>

{{page:Home-FHIRAssets-Extensions-ExtensionTemplate}}


<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>NHS Number Unavailable Reason</b>- An example of the extension which states the reason a patient's NHS number is unavailable.<br>
{{page:Home-Template-UKCoreExamplePageLink}}
<br><br>
</div>

<div id="Feedback" class="tabcontent">

{{page:Home-FeedbackTemplate-FeedbackLink}}

</div>

<h3 id="guidance-nhsnumberunavailablereason">Extension Specific Guidance</h3>

There is a binding within this extension to a {{pagelink:ValueSet-Genomic-NHSNumber-Unavailable-Reason}}.

---