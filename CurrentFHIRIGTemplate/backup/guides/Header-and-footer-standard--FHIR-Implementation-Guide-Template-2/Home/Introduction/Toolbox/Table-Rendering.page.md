## {{page-title}}

- In the Simplifier editor, tables can be generated via HTML, Markdown or FQL.
- The styling in this guide (applied via both the HTML master and CSS stylesheet) aims to provide consistency regardless of how the table has been created.
- You do not need to reference any CSS classes when creating tables, styling is automatically applied.
- When in the Simplifier editor, you need to "Preview" the page to view the tables with styling applied.
- Tables that are especially wide will have a horizontal overflow scrollbar automatically applied.

---

### See below for some examples:


#### FQL generated Table

@```
from
	StructureDefinition
select
	name, type, kind, url
order by
	name
```

---

### Markdown Generated Table

| One         | Two                       |
| ----------- | ------------------------  |
| 1.0         | A description             |
| 2.0         | Another description       |
                                                          

---

#### Wide HTML Table

<table>
  <thead>
      <tr>
        <th width="700">Element name</th>
        <th width="500">Base Cardinality</th>
        <th width="500">UK Core Cardinality</th>
        <th width="800">Type</th>
        <th width="2500">Definition, Constraints and Notes</th>
        <th width="700">Element name</th>
        <th width="500">Base Cardinality</th>
        <th width="500">UK Core Cardinality</th>
        <th width="800">Type</th>
        <th width="2500">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>Logical id of this artifact.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>Logical id of this artifact.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
    </tr>
  </tbody>
</table>

---

### Long HTML Table

<table>
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">UK Core Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>Logical id of this artifact.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
    </tr>
    <tr>
        <td>meta</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>Meta</td>
        <td>Metadata about the resource.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- versionId</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>id</td>
        <td>Changes each time the content of the resource changes.<br/><br/>The version can be globally unique, or scoped by the Logical Id of the resource. Version identifiers are generally either a serially incrementing id scoped by the logical id, or a uuid, though neither of these approaches is required. There is no fixed order for version ids - clients cannot assume that a versionId that comes after another one either numerically or alphabetically represents a later version. The same versionId can never be used for more than one version of the same resource.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- lastUpdated</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>instant</td>
        <td>If populated, this value changes each time the content of the resource changes. It can be used by a system or a human to judge the currency of the resource content.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- source</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>uri</td>
        <td>A uri that identifies the source system of the resource.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- profile</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>canonical</td>
        <td>An assertion that the content conforms to a resource profile.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- security</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Coding</td>
        <td>Security labels applied to this resource. These tags connect resources in specific ways to the overall security policy and infrastructure. Security tags can be updated when the resource changes, or whenever the security sub-system chooses to.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- tag</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Coding</td>
        <td>Tags applied to this resource. Tags are used to relate resources to process and workflow. Applications are not required to consider the tags when interpreting the meaning of a resource.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>implicitRules</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>uri</td>
        <td>A set of rules under which this content was created.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>language</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>code</td>
        <td>Language of the resource content.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>text</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>Narrative</td>
        <td>Text summary of the resource, for human interpretation.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>contained</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Resource</td>
        <td>Contained, inline Resources.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>extension</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Extension</td>
        <td>Additional content defined by implementations.<br/><br/>See the <a href="#vs_extension">ValueSetExtensions</a> section for details of extensions that may be considered for use in UK Core value sets.</td>
    </tr>
    <tr>
        <td width="15%">modifierExtension</td>
        <td width="10%">0..*</td>
        <td width="10%">0..*</td>
        <td width="15%">Extension</td>
        <td width="50%">Extensions that cannot be ignored.</td>
    </tr>
    <tr>
        <td>url</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>uri</td>
        <td>Canonical identifier for this value set, represented as a URI (globally unique).<br/><br/>In the UK Core the format is:<br/><br/>&quot;<a href=""></a>https://fhir.hl7.org.uk/ValueSet/UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
    </tr>
    <tr>
        <td>identifier</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Identifier</td>
        <td>Additional identifier for the ValueSet, for example an OID.<br/><br/>If this is an OID, this should be in the following format:<br/><br/><pre>    &lt;identifier&gt;
        &lt;system value=&quot;urn:ietf:rfc:3986&quot;/&gt;
        &lt;value value=&quot;urn:oid:2.16.840.1.113883.2.1.3.2.4.16.21&quot;/&gt;
    &lt;/identifier&gt;</pre><br/><br/>Further guidance may be needed in due course.</td>
    </tr>
    <tr>
        <td>version</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Business version of the value set.<br/><br/>This will follow the  <a href="https://semver.org/" Target="_blank">Semantic Versioning standard</a> &lsqb;major.minor.patch&rsqb;.</td>
    </tr>
    <tr>
        <td>name</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Computer readable name, this should reflect the name in the url element.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
    </tr>
    <tr>
        <td>title</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Human readable name, this should reflect the name in the url element.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UK Core &lsqb;Business Names&rsqb;&quot; (initial letters in upper case, a space between each word).</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>The publication status as defined in <a href="https://hl7.org/fhir/valueset-publication-status.html">https://hl7.org/fhir/valueset-publication-status.html</a> &lsqb;draft &vert; active &vert; retired &vert; unknown&rsqb;.<br/><br/>UK Core CodeSystems in development have a status of &quot;draft&quot;.<br/><br/>UK Core CodeSystems that have been approved via Clinical and Technical Assurance have a status of &quot;active&quot;.<br/><br/>UK Core CodeSystems that are no longer required in the UK Core have a status of &quot;retired&quot;.</td>
    </tr>
    <tr>
        <td>experimental</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>boolean</td>
        <td>Boolean value to indicate that this value set is authored for testing purposes and is not intended to be used for genuine usage.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>date</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>The date (and optionally time) when the value set was published or last changed. The date must change when the business version or status changes.<br/><br/>Just the date without time is populated in the UK Core.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Name of the publisher (organization or individual).<br/><br/>For all UK Core value sets, where the base URL is <code>https://fhir.hl7.org.uk</code>, this will be &quot;HL7 UK&quot;.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>Contact details for the publisher.<br/><br/>See the <a href="#vs_template">template</a> for details of how this must be populated for all UK Core value sets, where the base URL is <code> https://fhir.hl7.org.uk/</code>.</td>
    </tr>
    <tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>A free text natural language description of the of the value set from a consumer's perspective. The textual description specifies the span of meanings for concepts to be included within the Value Set Expansion, and also may specify the intended use and limitations of the Value Set.<br/><br/>The general format should be as follows:<br/><br/>&quot;A set of codes that define &lsqb;description&rsqb;&quot;.<br/><br/>In the UK Core there is a preference to use the words &quot;define&quot; or &quot;describe&quot; and more rarely, &quot;identify&quot;.<br/><br/>For a value set containing a SNOMED CT Reference Set:<br/><br/>&quot;A set of codes that describe &lsqb;description&rsqb;. Selected from the &lsqb;RefSet display value&rsqb; of the SNOMED CT UK coding system.&quot;<br/><br/>For a value set containing a SNOMED hierarchy:<br/><br/>&quot;A set of codes that define &lsqb;description&rsqb;. Selected from the SNOMED CT UK coding system.&quot;<br/><br/>For a value set containing a complex set of SNOMED Reference Sets and/or hierarchies and/or individual concepts:<br/><br/>&quot;A set of codes from the SNOMED CT UK coding system that: &lsqb;description of RefSet/hierarchy1&rsqb;; &lsqb;description of RefSet/hierarchy2&rsqb;; etc.&quot;<br/><br/>Where the value set includes nullFlavor(s) in addition to other sets of codes, for the nullFlavor section:<br/><br/>&quot;Where no &lsqb;MainCodeSystem(s)&rsqb; coded information is available, a specific code from the nullFlavor CodeSystem can be used instead to indicate this.&quot;<br/><br/>For complicated descriptions, particularly where a complex set of SNOMED references is used, and where inclusion of a carriage return / line feed can make the content more presentable in Simplifier, the sequence &#13; can be inserted to start a new line and &#13;&#13; can be inserted to leave a line break before the next line starts.<br/><br/>See also the <a href="#vs_examples">Example ValueSets from the UK Core</a> section.</td>
    </tr>
    <tr>
        <td>useContext</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>UsageContext</td>
        <td>Context the content is intended to support. This is a code from extensible ValueSet <a href="https://hl7.org/fhir/valueset-usage-context-type.html">https://hl7.org/fhir/valueset-usage-context-type.html</a>, as well as a choice of CodeableConcept/Quantity/Range.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>jurisdiction</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>CodeableConcept</td>
        <td>A legal or geographic region in which the code system is intended to be used (if applicable).<br/><br/>Not currently used in the UK Core but there may be a use case for derived assets.</td>
    </tr>
    <tr>
        <td>immutable</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>boolean</td>
        <td>Indicates whether or not any change to the content logical definition may occur. If this is set to 'true', then no new versions of the content logical definition can be created. Normally immutability is set to 'false', which is the default assumption if it is not populated.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>purpose</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>markdown</td>
        <td>Explanation of why this value set is needed and why it has been designed as it has.<br/><br/>Not generally used in UK Core ValueSets but may have a use case in providing useful information not already evident from other content in a ValueSet.</td>
    </tr>
    <tr>
        <td>copyright</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
        <td>A copyright statement relating to the value set and/or its contents.<br/><br/>All UK Core ValueSets must contain the following:<br/><br/>&quot;Copyright &#169; &lsqb;YYYY&rsqb;+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at  <a href=""></a>http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7  The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at  <a href=""></a>https://www.hl7.org/fhir/license.html.&quot;, where &lsqb;YYYY&rsqb;=year of creation of the value set.<br/><br/>For UK Core ValueSets that contain SNOMED CT codes, the copyright statement must additionally include:<br/><br/>&quot;This value set includes content from SNOMED CT, which is copyright &#169; 2002+ International Health Terminology Standards Development Organisation (IHTSDO), and distributed by agreement between IHTSDO and HL7. Implementer use of SNOMED CT is not covered by this agreement.&quot;.<br/><br/>For UK Core ValueSets that contain dm+d codes, the copyright statement must additionally include:<br/><br/>&quot;Copyright &#169; NHS Digital&quot;</td>
    </tr>
    <tr>
        <td>compose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>BackboneElement</td>
        <td>A set of criteria that define the contents of the value set by including or excluding codes selected from the specified code system(s) that the value set draws from. This is also known as the Content Logical Definition (CLD).<br/><br/>See the following sections for details on how to populate this:<br/><br/>- <a href="#ukcore_cld">Content Logical Definition – ValueSets containing UK Core CodeSystems</a>, and<br/><br/>- <a href="#snomed_cld">Content Logical Definition – ValueSets containing SNOMED concepts</a>.</td>
    </tr>
    <tr>
        <td>- lockedDate</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>date</td>
        <td>The Locked Date is the effective date that is used to determine the version of all referenced Code Systems and Value Set Definitions included in the compose that are not already tied to a specific version.<br/><br/>With a defined lockedDate the value set is considered &quot;Locked&quot;. Otherwise, the value set may have different expansions as underlying code systems and/or value sets evolve. The interpretation of lockedDate is often dependent on the context - e.g. a SNOMED CT derived value set with a lockedDate will have a different expansion in USA than in UK. If a value set specifies a version for include and exclude statements, and also specifies a locked date, the specified versions need to be available that date, or the value set will not be usable.<br/><br/>Not currently used in the UK Core.</td>
    </tr>
    <tr>
        <td>- inactive</td>
        <td>0..1</td>
        <td>0..1</td>
        <td>boolean</td>
        <td>Whether inactive codes (codes that are not approved for current use) are in the value set.<br/><br/>If inactive = true, inactive codes are to be included in the expansion.<br/><br/>If inactive = false, the inactive codes will not be included in the expansion.<br/><br/>If absent, the behaviour is determined by the implementation, or by the applicable expansion parameters (but generally, inactive codes would be expected to be included).<br/><br/>Not currently used in the UK Core but a default value of &quot;true&quot; can be assumed.</td>
    </tr>
  </tbody>
</table>

---

### Matrix table

<table>
  <thead>
      <tr>
        <th style="width:22%;">Dataset</th>
        <th style="width:6%;transform: rotate(+90deg);">New medicine Service</th>
        <th style="width:6%;transform: rotate(-90deg);">Medication Review</th>
        <th style="width:6%;transform: rotate(-90deg);">Appliance Use Review</th>
        <th style="width:6%;transform: rotate(-90deg);">Vaccination Administration</th>
        <th style="width:6%;transform: rotate(-90deg);">CPCS Emergency Supply</th>
        <th style="width:6%;transform: rotate(-90deg);">CPCS Minor Illness</th>
        <th style="width:6%;transform: rotate(-90deg);">Smoking Cessation</th>
        <th style="width:6%;transform: rotate(-90deg);">Hypertension Case Finding</th>
        <th style="width:6%;transform: rotate(-90deg);">CVD</th>
        <th style="width:6%;transform: rotate(-90deg);">Contraception</th>
        <th style="width:6%;transform: rotate(-90deg);">STT</th>
        <th style="width:6%;transform: rotate(-90deg);">Palliative</th>
        <th style="width:6%;transform: rotate(-90deg);">Hepatitis C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>Logical id of this artifact.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
        <td>id</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>id</td>
        <td>Logical id of this artifact.<br/><br/>In the UK Core the format is:<br/><br/>&quot;UKCore-&lsqb;BusinessNames&rsqb;&quot; (initial letters in upper case, no spaces between words).</td>
    </tr>
  </tbody>
</table>

---