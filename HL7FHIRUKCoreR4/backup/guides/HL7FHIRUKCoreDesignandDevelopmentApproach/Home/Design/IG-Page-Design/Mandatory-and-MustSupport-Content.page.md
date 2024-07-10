## {{page-title}}

The MustSupport content is any element in which has information that the provider and consumer systems SHOULD send or collect and SHALL have a `MustSupport` flag AND `short` set. Note, if mandatory root level data elements (e.g. 1..1 or 1..*) are present then these SHALL have MustSupport` flag AND `short` and be included in the table.  

This SHALL be determined by use cases, and by analysis of the MustSupport flags used by other FHIR IG's, such as US Core, Aus Base, Wales DHCW, NHSE IG, HL7 EU Lab.

If a profile is not derived, the MustSupport section can be rendered via a template

~~~~html
{ {page:Home/ProfilesandExtensions/ProfileMustSupportTemplate.page.md}}
~~~~

If a profile is derived, it SHALL include a { {pagelink}} to the parent profile as per the examples below, and include a table of elements.

~~~html
### Mandatory and Must Support Data Elements

The following elements, in addition to those in the corresponding { {pagelink:Profile-Observation,text:UKCore-Observation}} parent profile, are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the { {pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity SHALL be present.</td>
</tr>
</table>

~~~

or

~~~html
The following elements, in addition to those of the the corresponding { {pagelink:Profile-Observation,text:UKCore-Observation}} and { {pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} parent profiles, are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the { {pagelink:Guidance-MustSupport}}.

<table class="assets" title="MustSupport element list">
<tr>
<th class="width30">Element</th>
<th class="width70">Reason</th>
</tr>
<tr>
<td><code>Observation.value[x]</code></td>
<td>A quantity SHALL be present.</td>
</tr>
</table>
~~~

This section must end with:

~~~~html
</div>

---
~~~~