## {{page-title}}

Any profile element that has information relevant to the UKCore and is different to HL7 SHALL be documented on its own page. The name of the page SHALL be the element naming in camelCase. If the binding to the element differs from HL7 then it SHALL be referenced here, along with the relevant page link.  

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

Links to active UKCore profiles SHALL be done using pagelink 

Links to draft profiles SHALL be written as 
~~~html
[UKCore-CarePlan (draft)](https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/Profile-UKCore-CarePlan)
~~~

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Links to draft profiles SHOULD only be present in IG's in development. An IG that is to be balloted SHOULD have these profiles referenced to base profiles, and these links swapped.
</div>


Links to HL7 resources SHALL be written as:
~~~html
[[Resource] Resource](https://hl7.org/fhir/R4/[Resource].html)
~~~

Referencing all profiles SHALL be done using the following sentences:
- For a single resource: 
~~~html
Where possible, it is expected that the resource being referenced SHOULD conform to  { {pagelink:Profile-[profile]}}.
~~~
- For a multiple resources, with at least one UK Core profile: 
~~~html
Where possible, it is expected that the resource being referenced SHOULD conform to one of the following UK Core profiles:
- { {pagelink:Profile-[profile]}}
- { {pagelink:Profile-[profile]}}
~~~
- Where the reference is to <code>Resource</code>:
~~~html
Where a UK Core profile exists the resource being referenced SHOULD conform to the profile.
~~~


### Identifier 

If there are no recognised business identifiers, then do not create a page for `identifier`. 

### Slices

If an element has a slice, this SHOULD be identified in the text, included it's discriminatorfor example: 

~~~html
The slice `ServiceRequest.category:genomicsWholeCaseSequencing` has been added to aid in identifying the category of service request for Genomics use cases.
~~~

### Extensions

If an element has an extension, this SHOULD be identified in the text, for example: 

~~~html
`ServiceRequest.priority` has the UKCore extension { {pagelink:Extension-UKCore-PriorityReason}}.
~~~

### Sub Element Guidance

Guidance for a sub element, e.g. [Resource].[element].[subelement], SHALL be written on a page at the element level.

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

~~~html
<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Table View" class="tabcontent" style="display:block">
  <h3>Table View</h3>
{ {table:UKCore-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{ {xml:UKCore-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{ {json:UKCore-Immunization-Sn-AstraZenecaVaccine-Example}}
</div>

~~~

If a profile element contains more than one inline example they SHALL each be contained within their own parent div.


### Non-unique sub headings

Where an element contains a heading for specific guidance, such as Display / Propogation / Consumer / Provider, with the same name as is used on another element, this guidance must have an unique id attribute, based on the element and heading:

~~~html
<h3 id="clinical-codes-display">Display</h3>

<h3 id="original-term-text-display">Display</h3>
~~~

---