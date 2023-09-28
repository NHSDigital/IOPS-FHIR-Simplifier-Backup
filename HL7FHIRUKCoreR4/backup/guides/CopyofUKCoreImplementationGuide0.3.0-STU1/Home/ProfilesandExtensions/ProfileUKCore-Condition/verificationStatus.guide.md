## <code>{{page-title}}</code>

The verification status to support the clinical status of the condition.

Is Modifier	true (Reason: This element is labelled as a modifier because the status contains the code refuted and entered-in-error that mark the Condition as not currently valid.)

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h3>Important Note</h3>
This note is to highlight that there is the potential for clinical risk associated with some of the values in the FHIR Standard required condition-ver-status ValueSet (see table below) bound to this element therefore:

- Senders - **MUST ACCEPT** that any risk associated with using this element lies with the sender and that unless the receiver can support all of these values the sender **MUST NOT** use this element. 
- Receivers - in the scenario where an implementation is not mature enough to send this element but does receive it, it **MUST** degrade to text any instances other than where the value is `confirmed`.
</div>
 


<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://terminology.hl7.org/CodeSystem/condition-ver-status}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://terminology.hl7.org/CodeSystem/condition-ver-status}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://terminology.hl7.org/CodeSystem/condition-ver-status}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://terminology.hl7.org/CodeSystem/condition-ver-status}}
</div>
<br/>



---