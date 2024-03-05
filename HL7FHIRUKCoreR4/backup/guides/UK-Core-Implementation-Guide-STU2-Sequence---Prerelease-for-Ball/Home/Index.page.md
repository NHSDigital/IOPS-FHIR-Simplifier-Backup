---
topic: Home-Guide-48666
---
## Home 

---

## {{guide-title}}

<p>
<h3>Project Description and Scope</h3>

The FHIR UK Core Implementation Guide as a project aims to provide UK wide FHIR implementation guidance that has applicability across jurisdictions and care settings.
<br><br>
The guidance includes: 
<ul>
<li>FHIR Resource profiles and extensions</li>
<li>FHIR Terminology components including ValueSets and CodeSystems</li>
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

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Note about the label "STU2" for this FHIR implementation guide (IG):</h4>
The "2" refers to this being a second ballot of the UK Core, as a "Standard for Trial Use" (STU). It is based on, and provides extra UK specific guidance for use of, the international standard FHIR R4. The STU2 label of this Implementation Guide is not in any way related to earlier versions of FHIR itself, with coincidentally similar labels such as FHIR DSTU2 or FHIR STU3.
<br><br>
For additional guidance, see {{pagelink:Guidance-FHIRVersions-25268}}.
</div>

<div markdown="span" class="alert alert-warning" role="alert">
<b>Important note regarding changes from STU1 Sequence:</b>
<ul><li>A summary of changes is available here: <a href="https://simplifier.net/guide/UKCoreVersionHistory/Home/STU2-Sequence/index.page.md?version=current"> Version History</a></li>
<li>The bindings for all SNOMED CT ValueSets have been changed to "preferred".</li>
<li>The bindings for all other UK Core ValueSets have been changed to "extensible".</li>
<li>The datatypes of extensions using codes/concepts, have been unified as valueCodeableConcept.</li>
<li>Minimum viable content table has been used to set MustSupport on each resource.</li>
<li>References to UKCore profiles have been reset to base references, and guidance states that where a UK Core profile exists for the reference, it SHOULD be used.</li>
</ul>
</div>

---

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Implementation Guidance Directory </h4>
The <a href="https://simplifier.net/guide/uk-core-implementation-guidance-directory?version=current">Implementation Guidance Directory</a> 
contains links to other guidance and documentation which is available to assist Implementers of the UK Core. 
This guidance covers items such as:
<ul>
<li>Version history and change control information.</li>
<li>Information around the design and approach of the UK Core.</li>
<li>Information to help identify clinical safety issues.</li>
<li>Further implementation guidance related to medication that has been developed by NHS England.</li>
</div>

### How to Read This Guide ###

This Guide is divided into several pages which are listed at the top of each page in the menu bar.
<ul>
<li>{{pagelink:Home-Guide-48666}}: The home page provides the introduction and background for UK Core.</li>
<li>{{pagelink:Home-Sitemap-21114}}: The Guidance page provides the sitemap of UK Core IG.</li>
<ul>
  <li>{{pagelink:Guidance-DataType-96659}}: This page gives guidance on the representation of constructs like Address, Name, and Telecom etc.</li>
  <li>{{pagelink:Guidance-CodeableConcept-25269}}: This page gives guidance on the processing of CodeableConcept codes such as SNOMED CT concepts and descriptions.</li>
  <li>{{pagelink:Guidance-FHIRVersions-25268}}: This page gives guidance on UK Core and FHIR Versions beyond R4.</li>
  <li>{{pagelink:Guidance-MustSupport-25267}}: This page gives guidance on the the use of MustSupport flags in UK Core.</li>
</ul>
<li>Profiles and Extensions: The  header for pages about Extensions and Profiles</li>
<ul>
  <li>{{pagelink:Library-Extensions-82806}}: The Extensions which have been defined for the UK Core.</li>
  <li>{{pagelink:Library-Profiles-32647}}: The Profiles which have been defined for the UK Core.</li>
</ul>
<li>Terminology: This page lists all the Terminology assets defined as part of this Implementation Guide.</li>
<ul>
  <li>{{pagelink:Library-ConceptMaps-90400}}: This page lists all the ConceptMaps defined as part of this Implementation Guide.</li>
  <li>{{pagelink: Library-ValueSetsAndCodeSystems-38719}}: This is the list of ValueSets and CodeSystems defined for use within the UK Core.</li>
  <li>{{pagelink:Library-ValueSets-59589}}: This is the list of all ValueSets defined for use within the UK Core.</li>
  <li>{{pagelink:Library-CodeSystems-93824}}: This is the list of all CodeSystems defined for use within the UK Core.</li>
</ul>
<li>Examples: The header for examples of UK Core FHIR assets.</li>
<ul>
  <li>{{pagelink:Library-Examples-92798}}: The examples available in this implementation guide</li>
</ul>
<li>{{pagelink:Home-ContactUs-86009}}:  How to Contact the key parties associated with this implementation guide.</li>
<li>{{pagelink:Home-Downloads-64240}}:  List of downloads for this implementation guide</li>
<li>{{pagelink:Home-Glossary-16696}}:  List of abbreviations and external links used in this implementation guide</li>
</ul>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="I1"><i class="fa fa-info-circle"></i> Licensing and Publisher</h4>
<ul>
<li> 
Copyright &#169; 2021+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by UK Core Development Team and published by HL7 UK.
</ul>
</div> 

{{render:ukcorelogos2023}}

---
