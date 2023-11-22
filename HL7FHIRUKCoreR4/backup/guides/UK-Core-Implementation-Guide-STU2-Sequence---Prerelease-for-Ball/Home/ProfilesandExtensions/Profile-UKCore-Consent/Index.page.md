---
topic: Profile-Consent-15646
---

# StructureDefinition-UKCore-Consent

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreConsent'
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
	name = 'UKCoreConsent'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-Consent, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>For Information Access</b> - An example to illustrate a patient giving consent for information access.<br/>
{{pagelink:Example-UKCore-Consent-ForInformationAccess}}
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Consent profile:

- Privacy Consent Directive: Agreement to collect, access, use or disclose (share) information. 
- Medical Treatment Consent Directive: Consent to undergo a specific treatment (or record of refusal to consent). 
- Research Consent Directive: Consent to participate in research protocol and information sharing required. 
- Advance Care Directives: Consent to instructions for potentially needed medical treatment (e.g. DNR).

---

## Profile Specific Implementation Guidance: ##

<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Consent.status</code></td>
<td>Indicates the current state of this consent.</td>
</tr>
<tr>
<td><code>Consent.scope</code></td>
<td>A selector of the type of consent being presented: ADR, Privacy, Treatment, Research.</td>
</tr>
<tr>
<td><code>Consent.category</code></td>
<td>The classification of the consent statement - for indexing/retrieval</td>
</tr>
<tr>
<td><code>Consent.patient</code></td>
<td>The patient/healthcare consumer to whom this consent applies.
</td>
</tr>
<tr>
<td><code>Consent.dateTime</code></td>
<td>When this consent was issued / created / indexed.
</td>
</tr>
<tr>
<td><code>Consent.performer</code></td>
<td>Who is agreeing to the policy and rules</td>
</tr>
<tr>
<td><code>Consent.organization</code></td>
<td>The custodian of the consent</td>
</tr>
<tr>
<td><code>Consent.source[x]</code></td>
<td>The source from which this consent is taken</td>
</tr>
</table>

---
