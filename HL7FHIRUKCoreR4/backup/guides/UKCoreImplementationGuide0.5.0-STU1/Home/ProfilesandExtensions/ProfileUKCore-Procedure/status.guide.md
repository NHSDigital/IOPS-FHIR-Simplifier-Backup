## <code>{{page-title}}</code>
A code specifying the state of the procedure. Generally, this will be the in-progress or completed state.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h3>Important Note</h3> 
This element is labelled as a modifier because the status contains codes that mark the resource as not currently valid. Therefore:

- Implementers **MUST NOT** process the `Procedure.code` element in isolation but **MUST** also process the `Procedure.status` and `Procedure.statusReason` elements as they may modify the context of the procedure information.</div>

This element **MUST** be present and use a value from the list below:

<br/>
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/event-status}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/event-status}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/event-status}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/event-status}}
</div>
<br/>	

The `unknown` code is not to be used to convey other statuses. The `unknown` code should be used when one of the statuses applies, but the authoring system doesn't know the current state of the procedure.

---