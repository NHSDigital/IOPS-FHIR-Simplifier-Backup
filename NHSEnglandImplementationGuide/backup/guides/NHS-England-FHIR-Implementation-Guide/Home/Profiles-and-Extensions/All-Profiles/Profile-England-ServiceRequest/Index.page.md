---
topic: Profile-England-ServiceRequest
---

# StructureDefinition-England-ServiceRequest

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'EnglandServiceRequest'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'EnglandServiceRequest'
select
	Profile_Purpose: purpose
```


<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.nhs.uk/StructureDefinition/England-ServiceRequest, snapshot}}
</div>



<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Service Request Category</b> - An example to illustrate a service request category<br>
{{pagelink:Example-England-Bundle-BARSMessageServiceRequestCategory}}
<br><br>
<b> ERS Service Request </b> - An example to illustrate a ERS service request state<br>
{{pagelink:Example-England-Bundle-ERSServiceRequestState}}
<br><br>
<b>Active ERS Advice And Guidance</b> - An example to illustrate a service request for active ERS advice and guidance<br>
{{pagelink:Example-England-ServiceRequest-ActiveERSAdviceAndGuidance}}
<br><br>
<b>Draft ERS Advice And Guidance</b> - An example to illustrate a service request for draft ERS advice and guidance<br>
{{pagelink:Example-England-ServiceRequest-DraftERSAdviceAndGuidance}}
<br><br>
<b>Draft Patient Referral</b> - An example to illustrate a service request for draft patient referral<br>
{{pagelink:Example-England-ServiceRequest-DraftPatientReferral}}
<br><br>
<b>ERS Counselling</b> - An example to illustrate a service request for ERS counselling<br>
{{pagelink:Example-England-ServiceRequest-ERSCounselling}}
<br><br>
<b>ERS Portal Link</b> - An example to illustrate a service request for ERS portal link<br>
{{pagelink:Example-England-ServiceRequest-ERSPortalLink}}
<br><br>
<b>ERS Way Finder</b> - An example to illustrate a service request for ERS way finder <br>
{{pagelink:Example-England-ServiceRequest-ERSWayFinder}}
<br><br>
<b>Referral Follow Up Advice</b> - An example to illustrate a service request for referral follow up advice<br>
{{pagelink:Example-England-ServiceRequest-ReferralFollowUpAdvice}}
</div>
</nocheck>

---

## Profile Specific Implementation Guidance: ##