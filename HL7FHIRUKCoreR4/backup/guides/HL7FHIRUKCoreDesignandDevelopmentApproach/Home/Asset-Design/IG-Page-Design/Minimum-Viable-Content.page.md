## {{page-title}}

The minimum viable content (MVC) is any element in which has information that the provider and consumer systems SHOULD send or collect. Note, if mandatory data elements (e.g. 1..1 or 1..*) are present then these SHALL be included in the MVC.  

MVC SHALL be determined by use cases, and by analysis of the MustSupport flags used by other FHIR IG's, such as US Core, Aus Base, Wales DHCW, NHSE IG, HL7 EU Lab.

~~~~html
<h3>Minimum Viable Content</h3>

A minimum viable content that all provider and consumer systems SHALL support are the following elements.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>[element]</code></td>
<td>[reason].</td>
</tr>
</table>

---
~~~~

If a profile is derived, it SHALL include a { {pagelink}} to the parent profile as per the examples below:

~~~html
### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding { {pagelink:Profile-Observation,text:UKCore-Observation}} table.
~~~

or

~~~html
### Minimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding { {pagelink:Profile-Observation,text:UKCore-Observation}} table, along with the following.
~~~

or

~~~html
###M inimum Viable Content

The minimum viable content that all provider and consumer systems SHALL support are the elements within the corresponding { {pagelink:Profile-Observation,text:UKCore-Observation}} and { {pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} tables, along with the following.
~~~

---