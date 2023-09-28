---
topic: Profile-RequestGroup
---
# StructureDefinition-UKCore-RequestGroup

<!-- <div  id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This Profile underwent Clinical and Technical Assurance during Sprint 7. This is a new Profile added to UK Core and undergoing review under Ballot 2.
</div> -->

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'UKCoreRequestGroup'
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
	name = 'UKCoreRequestGroup'
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
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/UKCore-RequestGroup, snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>Ciprofloxacin</b> - Example to illustrate the options for Ciprofloxacin when prescribing multiple routes.
  <br>
  {{pagelink:Example-UKCore-RequestGroup-Ciprofloxacin}}
  <br><br>
  <b>Multiple Antibiotics</b> - Example to illustrate the options for multiple antibiotics when prescribing multiple routes.
  <br>
  {{pagelink:Example-UKCore-RequestGroup-MultipleAnitibiotics}}
  <br><br>
  <b>Paracetamol</b> - Example to illustrate the options for Paracetamol when prescribing multiple routes.
  <br>
  {{pagelink:Example-UKCore-RequestGroup-Paracetamol}}
  <br><br>
</div>
<nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core RequestGroup profile:
<br><br>

#### An example of the same drug, different route

This example shows how a request for the same drug through two different routes can be structured, with the decision to the more appropriate route being taken before a dispense is made.

{{render:RequestGroup-Paracetamol}}
- {{pagelink:Example-UKCore-MedicationRequest-ParacetamolIV}}
- {{pagelink:Example-UKCore-MedicationRequest-ParacetamolOral}}
- {{pagelink:Example-UKCore-RequestGroup-Paracetamol}}
- {{pagelink:Example-UKCore-MedicationDispense-ParacetamolOral}}
<br><br><br>

#### An example of different drugs, with a preference to one of them

This example shows how a request can be achieved giving the option for multiple different drugs, with one being preferred option and up to one being allowed to be dispensed. 

{{render:RequestGroup-MultipleAntibiotics}}
- {{pagelink:Example-UKCore-MedicationRequest-Amoxicillin}}
- {{pagelink:Example-UKCore-MedicationRequest-Clarithromycin}}
- {{pagelink:Example-UKCore-MedicationRequest-Doxycycline}}
- {{pagelink:Example-UKCore-RequestGroup-MultipleAnitibiotics}}
- {{pagelink:Example-UKCore-MedicationDispense-Amoxicillin}}
<br><br><br>

#### An example of same drug different doses, where both are dispensed but only one administered

This example shows a request of the same drug each with a different dose and route. This request allows both to be dispensed, with one being administered now and the other that may be dispensed at a later date or disposed.

{{render:RequestGroup-Ciprofloxacin}}
- {{pagelink:Example-UKCore-MedicationRequest-CiprofloxacinIV}}
- {{pagelink:Example-UKCore-MedicationRequest-CiprofloxacinOral}}
- {{pagelink:Example-UKCore-RequestGroup-Ciprofloxacin}}
- {{pagelink:Example-UKCore-MedicationDispense-CiprofloxacinIV}}
- {{pagelink:Example-UKCore-MedicationDispense-CiprofloxacinOral}}
- {{pagelink:Example-UKCore-MedicationAdministration-CiprofloxacinIV}}
<br><br>

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
<td><code>status</code></td>
<td>The current state of the request. For request groups, the status reflects the status of all the requests in the group.</td>
</tr>
<tr>
<td><code>intent</code></td>
<td>Indicates the level of authority/intentionality associated with the request and where the request fits into the workflow chain.</td>
</tr>
<tr>
<td><code>subject</code></td>
<td>The subject for which the request group was created.</td>
</tr>
<tr>
<td><code>action.description</code></td>
<td>A short description of the action used to provide a summary to display to the user.</td>
</tr>
<tr>
<td><code>action.type</code></td>
<td>The type of action to perform (create, update, remove).</td>
</tr>
<tr>
<td><code>action.selectionBehavior</code></td>
<td>Defines the selection behavior for the action and its children.</td>
</tr>
<tr>
<td><code>action.resource</code></td>
<td>The resource that is the target of the action (e.g. CommunicationRequest).</td>
</tr>
<tr>
<td><code>action.action</code></td>
<td>Sub actions.</td>
</tr>
</table>

---
