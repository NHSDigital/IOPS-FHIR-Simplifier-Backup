## {{page-title}}

Any profile element that has information relevant to NHS England and is different to HL7 or UK Core SHALL be documented on its own page. The name of the page SHALL be the element naming in camelCase. If the binding to the element differs from HL7 or NHSE IG  then it SHALL be referenced here, along with the relevant page link. Initially, the information in each element comes from the definition or comment or requirement values that existed in the equivelant NHS Digital asset.

The words ‘optional’ or ‘mandatory’ relating to the element are no longer needed as this has been deemed as duplication of either the element cardinality or MVC.  

The page SHALL use the following format: 
~~~html
## `{ {page-title}}`

[information]

---
~~~

---

## Rules

### Referencing Profiles 

All Binding references within a profile SHALL be explicitly shown via the relevant element page, apart from the element `identifier.assigner`. 

Links to active NHS England profiles SHALL be done using pagelink 

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Links to draft profiles SHOULD only be present in IG's in development. An IG that is to be balloted SHOULD have these profiles referenced to base profiles, and these links swapped.
</div>


Links to HL7 resources SHALL be written as:
~~~html
<a href="https://hl7.org/fhir/R4/[Resource].html">[Resource] Resource</a>
~~~

Referencing all profiles SHALL be done using the following sentences:
- For a single resource: 
~~~html
The resource being referenced SHALL conform to { {pagelink:Profile-[profile]}}.
~~~
- For a multiple resources, with at least one NHSE IG profile: 
~~~html
 The resource being referenced SHALL conform to one of the following: 
- { {pagelink:Profile-[profile]}}
- { {pagelink:Profile-[profile]}}
~~~
- Where the reference is to <code>Resource</code>:
~~~html
Where a NHSE IG profile exists the resource being referenced SHALL conform to the profile.
~~~


### Identifier 

If there are no recognised business identifiers, then do not create a page for `identifier`. 

### Slices

If an element has a slice, this SHOULD be identified in the text, for example: 

~~~html
The slice `ServiceRequest.category:genomicsWholeCaseSequencing` has been added to aid in identifying the category of service request for Genomics use cases.
~~~

### Extensions

If an element has an extension, this SHOULD be identified in the text, for example: 

~~~html
`ServiceRequest.priority` has the NHS England extension { {pagelink:Extension-NHS England-PriorityReason}}.
~~~

### Sub Element Guidance

Guidance for a sub element, e.g. [Resource].[element].[subelement], SHOULD be written on a page at the element level.

For example:

~~~html
## <code>performer</code>

The resource referenced in `Procedure.performer.actor` SHALL conform to one the following:
- { {pagelink:Profile-Organization}}
- { {pagelink:Profile-Patient}}
- { {pagelink:Profile-Practitioner}}
- {  {pagelink:Profile-PractitionerRole}}
- { {pagelink:Profile-RelatedPerson}}

The resource referenced in `Procedure.performer.onBehalfOf` SHALL conform to { {pagelink:Profile-Organization}}.

---

~~~

### In line examples 

If there is an inline example to be rendered, to provide an example of the usage of a specific resource element, the example SHOULD be prefixed with a fully qualified description of the usage: 

~~~html
#### Example of `Immunization.vaccineCode` usage:
~~~

And the inline example SHALL be in the following format: 

~~~~html
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'Tree View')">Tree View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{ {table:NHS England-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

<div id="Tree View" class="tabcontent">
  <h3>Tree View</h3>
{ {tree:NHS England-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:NHS England-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:NHS England-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

~~~~

---