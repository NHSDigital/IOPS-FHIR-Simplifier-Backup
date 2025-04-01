### What is a NamingSystem?
A FHIR NamingSystem is a URL that acts as a well known "name" for the type of another concept, such as an NHS Number (an identifier) or a SNOMED CT code (codesystem). 

The name is a machine readable unique string for the scheme of an identifier or codesystem. When a concept is used in FHIR, such as an identifier in a Patient resource, there needs to be a way to show that it is from the set of NHS Numbers and not some other type of identifier. This concept type is a URL, that acts as a name, and it is used in `identifier.system` or `coding.system`. FHIR NamingSystem URLs are equivalent to OIDs used in earlier versions of HL7. OIDs can still be used but are deprecated for use in FHIR.


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4 id="I1">Note</h4>
 This guide is a catalogue of the UK naming URLs. Each name entry is held in a FHIR NamingSystem resource.These resources are only needed as documentation within this catalogue. It is only the naming URL itself that is used in actual FHIR data. Software systems only need to use the correct URL, and don’t need to directly deal with the NamingSystem resources.
</div> 

### NamingSystem Index Tables
The index tables list the following information which is explained below:

<table class="assets">
<tr>
<th>Name</th>
<td>A human readable name for the NamingSystem</td>
</tr>
<tr>
<th>URL</th>
<td>A URL that is carried in the <code>coding.system</code> element for NamingSystems of type codesystem or <code>identifier.system</code> for NamingSystems of type identifier within a FHIR instance used for data exchange</td>
</tr>
<tr>
<th>Description</th>
<td>The description of the NamingSystem</td>
</tr>
<tr>
<th>Status</th>
<td>The status of the NamingSystem <ul>
<li>active - a NamingSystem that is still actively maintained</li>
<li>retired - a NamingSystem that is no longer maintained, however is still useable with a FHIR instance for data exchange. For example, for historic information.</li>
</ul></td>
</tr>
<tr>
<th>Kind</th>
<td>The type of NamingSystem which SHALL be a value from: {{render:http://hl7.org/fhir/namingsystem-type}}</td>
</tr>
<tr>

</table>

<br/>

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4 id="I1">Licensing and Publisher</h4>
<ul>
<li> 
Copyright &#169; 2021+ HL7 UK Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at  http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at  https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by UK Core Development Team and published by HL7 UK.
</ul>
</div> 

---
<br/>
{{render:HL7FHIRUKCoreR4/ukcorelogos2023}}
