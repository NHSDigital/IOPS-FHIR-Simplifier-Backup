<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> We would like your feedback</h4>
Please complete this short feedback form <a href="https://forms.office.com/e/4eE3dDACDS">here </a>to help the Interoperability Standards Team produce 
specifications that meet your requirements 
</div>

## Home 

This NHS England FHIR Implementation Guide provides additional guidance, rules and constraints which extends the <a href="https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence?version=current" target="_blank">FHIR UK Core Implementation Guide</a>

The scope of this Implementation Guide is for programmes and products within NHS England. The NHS England programmes and associated FHIR Assets are listed in the tables below.

Please click [here](https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Guidance/Conformance.page.md?version=current) for conformance guidance for NHS England programmes, products and systems. <br>

### NHS England IG Use Cases

For programme specific implementation guidance, please click the table header.

---

<h4>Sprint 2 <a href="https://simplifier.net/guide/nhs-england-ig-clinical-and-technical-assurance-doc-pack?version=1.1.0-sprint-2-review">(Documentation Pack)</a></h4>

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th colspan="1"><a href="https://simplifier.net/guide/gp-connect--patient-facing-services--prescriptions?version=current">GP Connect (Patient Facing) Prescription Ordering Parameters</a></th>
  </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-PFSPrescriptionOrderingParameter, text:CodeSystem-England-PFSPrescriptionOrderingParameter}}
    </td>
   </tr>
  </tbody>
</table>

<table class="regular assets" style="width:100%">
  <thead>
   <tr>
     <th colspan="3"><a href="https://simplifier.net/guide/organisational-data-services?version=current">Organisation Data Service (ODS)</a></th>
   </tr>
  </thead>
  <tbody>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ODSDateTime, text:CodeSystem-England-ODSDateTime}}
    </td>
    <td>
      {{pagelink:Extension-England-TypedDateTime, text:Extension-England-TypedDateTime}}
    </td>
    <td>
      {{pagelink:ValueSet-England-TypedDateTime, text:ValueSet-England-TypedDateTime}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ODSOrganisationRole, text:CodeSystem-England-ODSOrganisationRole}}
    </td>
    <td>
      {{pagelink:Extension-England-OrganisationRole, text:Extension-England-OrganisationRole}}
    </td>
    <td>
      {{pagelink:ValueSet-England-OrganisationRole, text:ValueSet-England-OrganisationRole}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ODSRecordClass, text:CodeSystem-England-ODSRecordClass}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ODSRecordUseType, text:CodeSystem-England-ODSRecordUseType}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ODSRelationship, text:CodeSystem-England-ODSRelationship}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-PeriodType, text:CodeSystem-England-PeriodType}}
    </td>
    <td>
      {{pagelink:Extension-England-TypedPeriod, text:Extension-England-TypedPeriod}}
    </td>
    <td>
      {{pagelink:ValueSet-England-PeriodType, text:ValueSet-England-PeriodType}}
    </td>
   </tr>
  </tbody>
</table>

---

<h4>Sprint 1 <a href="https://simplifier.net/guide/nhs-england-ig-clinical-and-technical-assurance-doc-pack?version=1.0.0-sprint-1-review">(Documentation Pack)</a></h4>

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th colspan="3"><a href="https://simplifier.net/guide/female-genital-mutilation-implementation-guide2?version=current">Female Genital Mutilation (FGM)</a></th>
  </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-FGMRemovalReason, text:CodeSystem-England-FGMRemovalReason}} 
    </td>
	 <td>
      {{pagelink:Extension-England-FlagRemovalReason, text:Extension-England-FlagRemovalReason}} 
    </td>
    <td>
      {{pagelink:ValueSet-England-FlagRemovalReason, text:ValueSet-England-FlagRemovalReason}} 
    </td>
   </tr>
  </tbody>
</table>

<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th colspan="1"><a href="https://simplifier.net/guide/child-protection---information-sharing--cp-is--api-consumer-impl?version=current">Child Protection Information Sharing (CP-IS)</a></th>
  </tr>
 </thead>
 <tbody>
   <tr>
    <td>
     {{pagelink:ValueSet-England-ChildProtectionPlan, text:ValueSet-England-ChildProtectionPlan}}
    </td>
   </tr>
  </tbody>
</table>

<!--
<table class="regular assets" style="width:100%">
 <thead>
   <tr>
     <th class="width33">Female Genital Mutilation (FGM)</th>
     <th class="width33">Child Protection Information Sharing (CP-IS)</th>
     <th class="width34">GP Connect (Patient Facing) Prescription Ordering Parameters</th>
  </tr>
 </thead>
 <tbody>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-FGMRemovalReason, text:CodeSystem-England-FGMRemovalReason}} 
    </td>
    <td>
      {{pagelink:ValueSet-England-ChildProtectionPlan, text:ValueSet-England-ChildProtectionPlan}} 
    </td>
    <td>
      {{pagelink:CodeSystem-England-PFSPrescriptionOrderingParameter, text:CodeSystem-England-PFSPrescriptionOrderingParameter}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:Extension-England-FlagRemovalReason, text:Extension-England-FlagRemovalReason}} 
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:ValueSet-England-FlagRemovalReason, text:ValueSet-England-FlagRemovalReason}} 
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
  </tbody>
</table>

<table class="regular assets" style="width:100%">
  <thead>
   <tr>
     <th class="width100">Organisation Reference Data (ORD)</th>
   </tr>
  </thead>
  <tbody>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ORDDateTime, text:CodeSystem-England-ORDDateTime}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ORDOrganisationRole, text:CodeSystem-England-ORDOrganisationRole}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ORDRecordClass, text:CodeSystem-England-ORDRecordClass}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ORDRecordUseType, text:CodeSystem-England-ORDRecordUseType}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-ORDRelationship, text:CodeSystem-England-ORDRelationship}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:CodeSystem-England-PeriodType, text:CodeSystem-England-PeriodType}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:Extension-England-DateTime, text:Extension-England-DateTime}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:Extension-England-OrganisationRole, text:Extension-England-OrganisationRole}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:Extension-England-TypedPeriod, text:Extension-England-TypedPeriod}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:ValueSet-England-OrganisationRole, text:ValueSet-England-OrganisationRole}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:ValueSet-England-PeriodType, text:ValueSet-England-PeriodType}}
    </td>
   </tr>
   <tr>
    <td>
      {{pagelink:ValueSet-England-TypedDateTime, text:ValueSet-England-TypedDateTime}}
    </td>
   </tr>
  </tbody>
</table>
-->

---

<h3 id="licence-heading">Licence</h3>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="Licence"><i class="fas fa-gavel"></i> Licensing and Publisher</h4>
<ul>
<li>
Copyright© 2023+ NHS England Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by NHS England Interoperability Team.
</ul>
</div>
