---
topic: Home-Guide-99a4a60b-3137-46ef-8ba3-bf2bf343c4b8
---
## UK Core Implementation Guide 0.2.0 - STU1 ##



</br>
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Project Description and Scope</h4></br>
<ul>
<li>This Implementation Guide is Release 0.2.0 of the UK Core
<li>The Scope of this release is only to provide FHIR assets and guidance to allow the content to be reviewed as part of the Clinical and Technical Assurance Process. This guide MUST not be implemented and the current release 0.1.0 should be used for that purpose. For the full version history see the  Version History link in this Implementation Guide's footer.

</li>
</ul>
  </div>



### How to Read This Guide ###

This Guide is divided into several pages which are listed at the top of each page in the menu bar.
<ul>
<li>{{pagelink:Home-Guide-99a4a60b-3137-46ef-8ba3-bf2bf343c4b8}}:  The home page provides the introduction and background for UK Core.</li>
<li>{{pagelink:Home-Sitemap-90df5111-af19-4c91-a662-4b4a4928117d, text:Guidance}}:  The Guidance page provides the sitemap of UK Core IG.</li>
<ul>
<li>{{pagelink:Guidance-Allergy-544dbad8-07e7-4a45-9f1c-ae7be7ae6a5f}}: This page gives guidance on the UK Core implementation of AllergyIntolerance</li>
<li>{{pagelink:Guidance-Medication-716a0019-0c3a-4ed6-9972-1a5c27ca4257}}: This page gives guidance on the UK Core implementation of Medication Guidance</li>
<li>{{pagelink:Guidance-People-29e2a34a-9f2c-4272-8f9b-d64aeb920acc}}: This set of Profiles relate to the Patient receiving care, the Practitioner (health and care professional) providing care, their PractionerRole, the Organization responsible for delivering care and the Location at which care is delivered.</li>
<li>{{pagelink:Guidance-DataType-65c6bd42-eeed-4df9-85bf-3ebfc1ffa38b}}: This page gives guidance on the representation of constructs like Address, Name, and Telecom etc.</li>
</ul>
<li>Profiles and Extensions: The  header for pages about Extensions and Profiles</li>
<ul>
  <li>{{pagelink:Library-Extensions-38957e9d-909d-485f-adb2-8ee4ace42c75}}: The Extensions which have been defined for the UK Core.</li>
  <li>{{pagelink:Library-Profiles-d78076a0-90d5-4e11-8b6e-64697b0bcfd9}}: The Profiles which have been defined for the UK Core.</li>
</ul>
<li>Terminology: This page lists all the Terminology assets defined as part of this Implementation Guide.</li>
<ul>
  <li>{{pagelink:Library-ConceptMaps-403c0b99-33cf-4694-939e-e4d1d1c65c33}}: This page lists all the ConceptMaps defined as part of this Implementation Guide.</li>
  <li>{{pagelink: Library-ValueSetsAndCodeSystems-7b04b3ad-26b2-4281-b1a3-8edbbe398915}}: This is the list of ValueSets and CodeSystems defined for use within the UK Core.</li>
<li>{{pagelink:Library-ValueSets-acc81862-6764-4488-ac94-449f438f1101}}: This is the list of all ValueSets defined for use within the UK Core.</li>
<li>{{pagelink:Library-CodeSystems-bd2529c5-b66d-44fc-9003-0072559db265}}: This is the list of all CodeSystems defined for use within the UK Core.</li>
</ul></li>
<ul>
</ul>
<li>Examples: The header for examples of UK Core FHIR assets.</li>
<ul>
  <li>{{pagelink:Library-Examples-3bc726b2-ddb5-43b1-806f-55e38d70183c}}: The examples available in this implementation guide</li>
</ul>
<li>{{pagelink:Home-ContactUs-11c3a28f-96ef-4ad8-ae91-7f93e0ff1292}}:  How to Contact the key parties associated with this implementation guide.</li>
<li>{{pagelink:Home-Downloads-15ba699d-87f6-4e83-9e54-5b763c0744e2}}:  List of downloads for this implementation guide</li>
</ul>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Associated Implementation Guides</h4>
Building on the UK Core, further implementation guidance related to medication has developed by NHS Digital:
<ul>
<li><a href="https://simplifier.net/guide/ukcoreimplementationguideformedicines/elementdosage?version=current" target="_blank">Dose Syntax Implementation Guidance for FHIR R4</a></li>
<li><a href="https://simplifier.net/guide/ukcoreimplementationguideformedicines/home?version=current" target="_blank">Implementation Guide for Medicines</a></li>
</div> 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Design and Development Approach</h4>
<ul>
<li>Documentation on the development approach can be found at <a href="https://simplifier.net/guide/hl7fhirukcoredesignanddevelopmentapproach?version=current">UK Core Design and Development Approach</a></li>
</ul>
</div>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4 id="I1">Licensing and Publisher</h4></br>
<ul>
<li> 
Copyright &#169; 2021+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at  http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at  https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by UK Core Development Team and published by HL7 UK.
</ul>
</div> 

---

<table align="center">
  <tr>
    <th>{{render:hl7-uk-logo}}</th>
    <th>{{render:nhs-digital-logo}}</th>
    <th>{{render:NHSx-logo}}</th>
    <th>{{render:DHCW-logo-RGB-Blue}}</th>
    <th>{{render:INTEROpen-logo}}</th>
    <th>{{render:PRSB-logo}}</th>
  </tr>
</table>

---
