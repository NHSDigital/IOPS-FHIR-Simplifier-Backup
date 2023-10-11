# Home

This is the design and development approach used to produce the NHS England IG. It serves several purposes, for example:

- It is to allow implementers of the NHS England Profiles to understand how and why the NHS England IG has been produced.
- To act as a guide for anyone creating a derived IG to understand the process. 
- To allow interested parties to get involved in these processes.
- To facilitate suggestions for improvement to these processes.

## NHS England Approach to FHIR

Implementers of FHIR need to get consistent guidance from NHS England.

### Why do we need to change our approach?

- Too many profiles for same resource type due to programme level profiles
- Implementers really want one common profile
- Not as per STU3 – 7 profiles of patient
- Inconsistent and multiple ways of representing the same data in FHIR
- We should use common patterns
- Inconsistent and multiple ways of coding the same data in FHIR
- Need agreed coding for all use cases
- Lack of an NHS England wide approach and collaboration between stakeholders across programmes
- Need to have a collaborative approach across all programmes
- Lack of proper quality control and release approaches
- Need a roadmap of what is being released and when.
- All the previous points add more complexity and cost for implementers plus make interoperability harder

### Use cases

### Programme/domain use cases

Each programme/domain SHALL NOT have seperate FHIR assets.

{{render:UseCaseDiagram1}}

<br />

### Event/clinical concept level use cases

Use cases should be at event/clinical concept lebel. FHIR UK Core SHALL be used wherever possible.

{{render:UseCaseDiagram2}}

<br />

### Using NHS England IG for use cases

FHIR UK Core SHALL be used wherever possuble however using NHS England IG for NHS England specific use cases is allowed only by exception.

{{render:UseCaseDiagram3}} 

<br />

### Scope

The NHS England implementation guide conforms to UK Core but provides an additional layer of conformance for NHS England National programmes and systems to aid implementation only where it is deemed appropriate by NHS England national requirements. 

- Applies to new R4 FHIR work
- Currently being used for CP-IS and FGM
- All Existing implementations to be evaluated
- Move to new approach only if appropriate 
- It is a breaking change due to new FHIR assets using different URLs

### How will NHS England IG be developed?

<table class="assets">
  <thead>
      <tr>
        <th width="33%">Curation</th>
        <th width="33%">Assurance</th>
        <th width="34%">Release</th>
      </tr>
  </thead>
  <tbody>
    <tr>
        <td>
            IOPS will manage the NHS England IG ensuring no duplication of profiles; normally maximum of 1 per resource type; and only allowing extensions to UK Core when deemed appropriate 
        </td>
        <td>
            The contents of the NHS England IG will be assured by the NHS England SMEs from IOPS and    programmes using a series of sprints as required C&TA - Teams calls and a 1-week review period
Followed by release of the agreed assured content
        </td>
        <td>
            NHS England IG will follow UK Core (FHIR) statuses IG naming will be in sequences (following FHIR UK Core and FHIR approach) are named by status + sequence number
        </td>
    </tr>
   </tbody>
</table>

### Content for Early Releases

The content for early releases of NHS England IG will primarily contain only FHIR assets and associated implementation guideance. However, future subsequent releases may also include common approaches, frameworks, patterns for exchange, as well as other content deemed appropriate in the future.

### Process

- Programme level IGs allowable but only for extra guidance, use cases etc 
- No programme specific FHIR assets
- Strict C&TA process for NHS England IG and FHIR assets hosted by IOPS
- C&TA to open to all NHS England stakeholders, programmes, boards etc 
- Strict quality control and release process of NHS England IG and FHIR Assets. Controlled release of the NHS England IG with an agreed schedule.

### What does this mean to implementers?

- Fewer profiles to build to 
- More consistency (less re-coding)
- Potential faster implementation 
- More interoperability
- Easier sharing of data
- Potential cost savings

### What does this mean to programmes?

- Potential faster development
- Less duplicate of effort
- Potential cost savings
- Programmes need to track UK Core development (C&TA sprints and ballots) and interact with the FHIR UK Core Technical Implementation Group

### Important points

- Vendors should be instructed to build to UK Core Profiles (with any NHS England extensions) 
- Validation if required, should be done using UK Core and NHS England profiles and extensions during testing, FoTs etc
- Specific programme requirements can still be met

### Alignment with government design principles

- Do the hard work to make it simple - NHS England should be doing the work, not leaving it to external developers to resolve differences between API’s.
- Be consistent, not uniform - We are not building tight profiles but profiling just enough to ensure consistency and aid interoperability. 
- Iterate. Then iterate again - The development processes and C&TA are iterative processes 
- Start with user needs - What do clinical users want - Quote from a clinical lead “a patient is a patient, why do we profile 7 times?”

### Who does what?

<table class="assets">
  <thead>
      <tr>
        <th width="60%">Task</th>
        <th width="20%">IOPS</th>
        <th width="20%">Programme Team</th>
      </tr>
  </thead>
  <tbody>
    <tr>
        <td>Develop UK Core IG and FHIR assets</td>
        <td>Yes</td>
        <td>No</td>
    </tr>
        <tr>
        <td>Track development of UK Core</td>
        <td>Yes</td>
        <td>Yes</td>
    </tr>
        <tr>
        <td>Participate in UK Core C&TA</td>
        <td>Yes</td>
        <td>Yes*</td>
    </tr>
        <tr>
        <td>Develop NHS England IG and FHIR assets</td>
        <td>Yes</td>
        <td>No</td>
    </tr>
        <tr>
        <td>Track development of NHS England IG and FHIR assets</td>
        <td>Yes</td>
        <td>Yes</td>
    </tr>
        <tr>
        <td>Participate in NHS England C&TA</td>
        <td>Yes</td>
        <td>Yes<b>*</b></td>
    </tr>
        <tr>
        <td>Create use case/programme level guidance</td>
        <td>Yes<b>**</b></td>
        <td>Yes<b>**</b></td>
    </tr>
   </tbody>
</table>
<br /><br />
<table class="assets">
    <tr>
        <td><b>*</b></td>
        <td>If subject/scope is appropriate</td>
    </tr>
    <tr>
        <td><b>**</b></td>
        <td>Optional – only if additional guidance is required and can be done by IOPS, the programme team or a joint development</td>
    </tr>
</table>

### How do we build use case specific implementation guides? 

Please click [here](https://simplifier.net/guide/nhs-england-design-and-development-approach/home/management/simplifier-and-github-management/index.page.md?version=current "Simplifier and GitHub Management") to view further guidance on this topic.

### Maturity of standards vs need to deliver

- Standards take time to mature
- Delivery always seems to be needed yesterday 
- We all need to manage this and correctly communicate to implementers

{{render:profilematurityandstabilitydiagram}}

### Evaluating the maturity

Teams are able to evaluate the maturity of profiles and other FHIR assets across both FHIR UK Core and NHS England IG to make appropriate decisions based on current maturity levels.

The maturity level scoring is based on the likelihood that the profile will subject to change in the future.

#### UK Core
<table class="assets">
  <thead>
      <tr>
        <th width="10%">Maturity Level</th>
        <th width="22%">Status</th>
        <th width="65%">Status Definitions</th>
      </tr>
  </thead>
  <tbody>
    <tr>
        <td>Mature</td>
        <td>Balloted - Active</td>
        <td>The FHIR assets have completed the C&TA process and the HL7 UK Ballot process, and all issues raised have been resolved and the FHIR assets updated as appropriate. These FHIR assets are now deemed stable and only minor changes are anticipated. No breaking changes are likely.</td>
    </tr>
        <tr>
        <td>Intermediate</td>
        <td>Clinically & Technically Assured -Active</td>
        <td>The FHIR assets have completed the C&TA process, which means they have been assured by SMEs against example use cases and updated as required. The assets have been made active and are deemed stable and deemed low risk for changes to implementers. The HL7 UK Ballot may make changes to these assets, but although possible it is not likely to be major or breaking changes.</td>
    </tr>
        <tr>
        <td>Initial</td>
        <td>Draft</td>
        <td>These FHIR assets have been created only to allow some initial development / implementation work. These have had some input from SMEs but no formal assurance and therefore are likely to have changes which may be breaking applied during C&TA and the HL7 UK Ballot. Implementations using these assets should feedback and participate in the assurance process. These FHIR assets are still implementable at risk.</td>
   </tbody>
</table>

#### NHS England
<table class="assets">
  <thead>
      <tr>
        <th width="10%">Maturity Level</th>
        <th width="22%">Status</th>
        <th width="60%">Status Definitions</th>
      </tr>
  </thead>
  <tbody>
    <tr>
    </tr>
        <tr>
        <td>Mature</td>
        <td>Clinically & Technically Assured -Active</td>
        <td>The FHIR assets have completed the C&TA process, which means they have been assured by SMEs against example use cases and updated as required. The assets have been made active and are deemed stable and deemed low risk for changes to implementers. Changes may be made to these assets, but although possible it is not likely to be major or breaking changes.</td>
    </tr>
        <tr>
        <td>Initial</td>
        <td>Draft</td>
        <td>These FHIR assets have been created only to allow some initial development / implementation work. These have had some input from SMEs but no formal assurance and therefore are likely to have changes which may be breaking applied during C&TA. Implementations using these assets should feedback and participate in the C&TA process and which will move these to active status.</td>
   </tbody>
</table>

<br><br><br>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="Licence"><i class="fas fa-gavel"></i> Licensing and Publisher</h4>
<ul>
<li>
Copyright© 2023+ NHS England Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by NHS England Interoperability Team.
</ul>
</div>

