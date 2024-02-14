## {{page-title}}

Any extension referenced within the profile SHALL be added to the Extensions page and  table, along with the element in which it is to be used and a link to the extension page within the IG.  

If no information on the use of any extensions is needed, then the page SHALL be in the following format: 

If there are only standard UK Core Extensions:

~~~~html
{ {page:Home/ProfilesandExtensions/ProfileExtensionsTemplate.page.md}}

---

~~~~


If there are R5 pre-adopted backport Extensions AND / OR HL7 core defined Extensions:

~~~~html
## Extensions

More information about the extensions can be found using the links below.

<table class="assets" title="Extension list">
<tr>
<th class="width20">Extension</th>
<th class="width20">Context</th>
<th class="width30">Link</th>
<th class="width30">Comment</th>
</tr>
<tr>
<td>bodyPosition</td>
<td>Observation</td>
<td><a href="https://hl7.org/fhir/R4/extension-observation-bodyPosition.html">Core-defined Extension observation-bodyPosition</a></td>
<td></td>
</tr>
<tr>
<td>bodyStructureR5</td>
<td>Observation</td>
<td>{ {pagelink:Extension-UKCore-ObservationBodyStructure}}</td>
<td>This is a pre-adopted R5 element, for more details, see { {pagelink:Library-Extensions-PreAdopt}}.</td>
</tr>
</table>

---
~~~~


---