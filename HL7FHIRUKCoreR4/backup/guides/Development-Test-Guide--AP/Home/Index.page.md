---
topic: Home-Guide
---
## UK Core Development and Testing Implementation Guide ##

<p>
<h3>Project Description and Scope</h3>

The FHIR UK Core Implementation Guide as a project aims to provide UK wide FHIR implementation guidance that has applicability across jurisdictions and care settings.
<br><br>
The guidance includes: 
<ul>
<li>FHIR resource components including Profiles and Extensions</li>
<li>FHIR terminology components including ValueSets and CodeSystems</li>
<li>Other general guidance useful to FHIR implementers in the UK</li>
</ul>
</p>
<p>
The guidance does not form the basis for a completely described deployable service in and of itself but is the basis from which other FHIR implementation guides can be derived.
</p>
<p>
The FHIR UK Core Implementation Guide shows only the differences between the base FHIR resources and the UK Core Profiles, and does not repeat base guidance. For this reason, it is expected to be used in conjunction with <a href="https://hl7.org/fhir/R4/">https://hl7.org/fhir/R4/</a>. 
<br><br>
The FHIR UK Core will never contradict the base FHIR standard but will restrict and extend resources, including amending of any ValueSets and CodeSystems, as necessary to bring in line the UK requirements. The content is relevant to the UK as a whole (4 Nations) although some nation specific CodeSystems are included and referenced in ValueSets. 
<br><br>
Any derived profiles will follow similar guidance, and will only show the differences between the base FHIR UK Core profile and the derived profile itself.
</p>

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Note about the label "STU3" for this FHIR implementation guide (IG)</h4>
The "3" refers to this being a third ballot of the UK Core, as a "Standard for Trial Use" (STU). It is based on, and provides extra UK specific guidance for use of, the international standard FHIR R4. The STU3 label of this Implementation Guide is not in any way related to earlier versions of FHIR itself, with coincidentally similar labels such as FHIR DSTU2 or FHIR STU3.
</div>

---

<div markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-flask"></i> Experimental changes in this IG </h4>
<ul>
<li>Balloted info boxes removed.</li>
<li>STU2 note updated to state STU3.</li>
<li>Numeric id removed from page topics, and all links updated.</li>
<li>Automatic handling of Footer version links.</li>
<li>Different icons in callout boxes on Home page.</li>
<li>UK Naming Systems added to Guidance.</li>
<li>UK Core Access IG contents added to Guidance.</li>
<li>UK Core Access IG content added to relevant Profiles.</li>
<li>UK Core Extensions callout box converted to paragraph.</li>
<li>Profiles page has a new thick line seperator added between tabs & profile specific guidance</li>
<li>Profiles page has thick line seperators auto added after any specific elements (mvc, extensions, bindings, contraints), and auto added between elements & access ig contents.</li>
<li>Profiles page has Minimum Viable Content as a sub page.</li>
<li>Profiles page uses yaml subject, tree/table/xml/json rendering updated to use subject.</li>
<li>Profiles page uses new Simplifier diff/hybrid/snap buttons.</li>
<li>Profiles page includes new FQL based usage tab.</li>
<li>Profiles page sub page list now floats with the page as it scrolls.</li>
<li>Profiles page floating sub page list has separators between page specific guidance, elements, access ig contents.</li>
<li>Profiles page floating sub page list has profile link automatically added.</li>
<li>Profiles tree has "intelligent" expansion of elements.</li>
<li>All ValueSets page auto hides expansion tables, and auto adds a show / hide link on the "This value set contains xyz concepts" line.</li>
<li>Automatically alter SNOMED CT concept IDs in ValueSet tables to links that redirect to NHS TermBrowser.</li>
<li>Automatically alter SNOMED CT concept IDs in Example tables to links that redirect to NHS TermBrowser.</li>
<li>Title of UK Core Biopsy State sub page corrected.</li>
<li>New Examples Index page added, in line with Extensions Index, Profiles Index, ValueSets And CodeSystems.</li>
<li>Removed "(US Core style)" wording from Extensions Index, Profiles Index, ValueSets And CodeSystems, and Examples Index.</li>
<li>Speed testing of new Simplifier diff/hybrid/snap buttons.</li>
<li>Speed testing of new Simplifier tabs.</li>
<li>CSS testing of new Simplifier tabs.</li>
<li>CSS for new Simplifier diff/hybrid/snap buttons.</li>
<li>Corrected issues with alphabetical sorting on Extensions Index, Profiles Index, ValueSets And CodeSystems.</li>
<li>Added CSS styling for CodeSystem tables.</li>
<li>Added NHSE IG style /\ and \/ sort buttons to ValueSet and CodeSystem tables.</li>
<li>Automatically alter UK Core canonical url's in Examples, for url[0] and system[0] (Extension and CodeSystem), to be anchors that redirect to relevant page.</li>
<li>Automatically alter HL7 Terminology canonical url's in Examples, for system[0] to be anchors that redirect to relevant page.</li>
<li>Automatically alter UK Core canonical url's in profile trees / detail panels for References/Bindings/Extensions to redirect to relevant page.</li>
</div>

---

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-folder-open-o"></i> Implementation Guidance Directory </h4>
The <a href="https://simplifier.net/guide/uk-core-implementation-guidance-directory?version=current">Implementation Guidance Directory</a> contains links to other guidance and documentation which is available to assist Implementers of the UK Core. This guidance covers items such as:
<ul>
<li>Version history and change control information.</li>
<li>Information around the design and approach of the UK Core.</li>
<li>Information to help identify clinical safety issues.</li>
<li>Further implementation guidance related to medication that has been developed by NHS England.</li>
</div>

### How to Read This Guide ###

This Guide is divided into several pages which are listed at the top of each page in the menu bar.
<ul>
<li>{{pagelink:Home-Guide}}: The home page provides the introduction and background for UK Core.</li>
<li>{{pagelink:Guidance-Sitemap}}: The Guidance page provides the sitemap of UK Core IG.</li>
<ul>
  <li>{{pagelink:Guidance-DataType}}: This page gives guidance on the representation of constructs like Address, Name, and Telecom etc.</li>
  <li>{{pagelink:Guidance-CodeableConcept}}: This page gives guidance on the processing of CodeableConcept codes such as SNOMED CT concepts and descriptions.</li>
</ul>
<li>Profiles and Extensions: The  header for pages about Extensions and Profiles</li>
<ul>
  <li>{{pagelink:Library-Extensions}}: The Extensions which have been defined for the UK Core.</li>
  <li>{{pagelink:Library-Profiles}}: The Profiles which have been defined for the UK Core.</li>
</ul>
<li>Terminology: This page lists all the Terminology assets defined as part of this Implementation Guide.</li>
<ul>
  <li>{{pagelink:Library-ConceptMaps}}: This page lists all the ConceptMaps defined as part of this Implementation Guide.</li>
  <li>{{pagelink: Library-ValueSetsAndCodeSystems}}: This is the list of ValueSets and CodeSystems defined for use within the UK Core.</li>
  <li>{{pagelink:Library-ValueSets}}: This is the rendering of all ValueSets defined for use within the UK Core.</li>
  <li>{{pagelink:Library-CodeSystems}}: This is the rendering of all CodeSystems defined for use within the UK Core.</li>
</ul>
<li>Examples: The header for examples of UK Core FHIR assets.</li>
<ul>
  <li>{{pagelink:Library-Examples-Index}}: This is the list of examples available in this implementation guide</li>
  <li>{{pagelink:Library-Examples-All}}: This is the rendering of all examples available in this implementation guide</li>
</ul>
<li>{{pagelink:Home-ContactUs}}:  How to Contact the key parties associated with this implementation guide.</li>
<li>{{pagelink:Home-Downloads}}:  List of downloads for this implementation guide</li>
<li>{{pagelink:Home-Glossary}}:  List of abbreviations and external links used in this implementation guide</li>
</ul>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="I1"><i class="fa fa-legal"></i> Licensing and Publisher</h4>
<ul>
<li> 
Copyright &#169; 2021+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by UK Core Development Team and published by HL7 UK.
</ul>
</div> 

{{render:ukcorelogos2023}}

---
