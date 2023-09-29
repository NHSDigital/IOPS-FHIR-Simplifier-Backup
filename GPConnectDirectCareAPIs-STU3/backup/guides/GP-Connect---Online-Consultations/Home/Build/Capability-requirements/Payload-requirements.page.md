## {{page-title}}

## Composition

<table class="nhsd-!t-margin-bottom-6" data-responsive>
  <tbody>
    <tr>
        <td id="GPCM-SD-OC-001">GPCM-SD-OC-001</td>
        <td>a Composition resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Composition-1">CareConnect-Composition-1</a> resource <strong>MUST</strong> be present in the payload</td>
    </tr>
    </tbody>
</table>

The following requirements describe how the Composition resource is populated:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody>
        <tr>
            <td id="GPCM-SD-OC-002">GPCM-SD-OC-002</td>
            <td><code>Composition.status</code> <strong>MUST</strong> contain fixed value
                <strong><code>final</code></strong></td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-003">GPCM-SD-OC-003</td>
            <td><code>Composition.type</code> <strong>MUST</strong> contain the SNOMED code <code>149951000000107</code>
                (Patient information received using general practice online consultation system (finding))</td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-004">GPCM-SD-OC-004</td>
            <td><code>Composition.date</code> <strong>MUST</strong> contain the date/time the message was created</td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-005">GPCM-SD-OC-005</td>
            <td><code>Composition.confidentiality</code> <strong>MUST</strong> contain the fixed value <code>N</code>
                (Normal), or <code>R</code> (Restricted) if the consultation is classed as confidential</td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-006">GPCM-SD-OC-006</td>
            <td><code>Composition.title</code> <strong>MUST</strong> contain the fixed value
                <code>Online consultation report</code></td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-007">GPCM-SD-OC-007</td>
            <td><code>Composition.text</code> <strong>MUST</strong> contain a summary of request in the following
                format:<br>
                <code>Online consultation report for {Patient Name}, NHS Number {NHS Number}, Version {Version Number}</code>
            </td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-008">GPCM-SD-OC-008</td>
            <td><code>Composition.subject</code> <strong>MUST</strong> contain a reference to Patient resource profiled
                to <a
                    href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1">CareConnect-Patient-1</a>
            </td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-009">GPCM-SD-OC-009</td>
            <td><code>Composition.author</code> <strong>MUST</strong> contain a reference to one or more of the
                following resources: <ul>
                    <li>a Practitioner resource profiled to <a
                            href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1">CareConnect-Practitioner-1</a>
                    </li>
                    <li>a Patient resource profiled to <a
                            href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1">CareConnect-Patient-1</a>
                    </li>
                    <li>a RelatedPerson resource profiled to <a
                            href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-RelatedPerson-1">CareConnect-RelatedPerson-1</a>
                    </li>
                    <li>a Device resource profiled to <a
                            href="https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Device-1">ITK-Device-1</a></li>
                </ul>
            </td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-010">GPCM-SD-OC-010</td>
            <td><code>Composition.custodian</code> <strong>MUST</strong> contain a reference to the sender Organization
                resource profiled to <a
                    href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1">CareConnect-Organization-1</a>
            </td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-011">GPCM-SD-OC-011</td>
            <td><code>Composition.relatesTo</code> <strong>MUST</strong> contain the UUID of the previous message if a
                replacement document is being sent</td>
        </tr>
        <tr>
            <td id="GPCM-SD-OC-012">GPCM-SD-OC-012</td>
            <td><code>Composition.section.entry</code> <strong>MUST</strong> reference a binary document which provides
                a report of the full online consultation in PDF format profiled to <a
                    href="https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Attachment-Binary-1">ITK-Attachment-Binary-1</a>
            </td>
        </tr>
    </tbody>
</table>

### Additional input elements

Message senders MAY include additional binary documents in the payload as each expressed as an additional instance of the composition.section as described.

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-013">GPCM-SD-OC-013</td>
      <td>where binary documents are included in the payload in addition to the Online Consultation Report, the <em>message receiver</em> <strong>MUST</strong> process these according ensuring all attachments remain in the context of the encounter information delivered to downstream systems</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-014">GPCM-SD-OC-014</td>
      <td>when displaying the Online Consultation Report in the practice workflow/task list, the <em>message receiver</em> <strong>MUST</strong> display <code>Online consultation report for {Patient Name}, NHS Number {NHS Number}, Version {Version Number}</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-015">GPCM-SD-OC-015</td>
      <td>the <em>message receiver</em> <strong>MUST</strong> make any attachments included with the Consultation Report available to the end user</td>
    </tr>
  </tbody></table>


---

## Patient resource

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-016">GPCM-SD-OC-016</td>
      <td>the payload <strong>MUST</strong> contain a patient resource describing the patient</td>
    </tr>
  </tbody></table>

The CareConnect-Patient-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-017">GPCM-SD-OC-017</td>
      <td>the NHS Number of the patient <strong>MUST</strong> be specified in the <code>nhsNumber</code> slice of the <code>identifier</code> element</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-018">GPCM-SD-OC-018</td>
      <td>the name of the patient <strong>MUST</strong> be present in the single instance of the <code>name</code> element where <code>name.use</code> is set to <code>official</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-019">GPCM-SD-OC-019</td>
      <td>the date of birth of the patient <strong>MUST</strong> be specified in <code>YYYY-MM-DD</code> format in the <code>birthDate</code> element. Birth time is not required</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-020">GPCM-SD-OC-020</td>
      <td>values specified in the patient resource for surname, date of birth and NHS Number <strong>MUST</strong> match those specified in MESH metadata <code>Mex_To</code> (for the MESH API) or <code>To_DTS</code> field (for the MESH client) as described in MESH message configuration</td>
    </tr>
  </tbody></table>

---

## Organization resource

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-021">GPCM-SD-OC-021</td>
      <td>the payload <strong>MUST</strong> contain an organization resource describing the sender organisation (the originating organisation)</td>
    </tr>
  </tbody></table>

The CareConnect-Organization-1 resource present in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-021">GPCM-SD-OC-021</td>
      <td>the payload <strong>MUST</strong> contain an organization resource describing the sender organisation (the originating organisation)</td>
    </tr>
  </tbody></table><table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-022">GPCM-SD-OC-022</td>
      <td>the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element <strong>MUST</strong> contain the ODS code</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-023">GPCM-SD-OC-023</td>
      <td>the <code>name</code> element <strong>MUST</strong> contain the name of the organisation</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-024">GPCM-SD-OC-024</td>
      <td>the <code>telecom</code> element <strong>MUST</strong> contain the telephone number of that organization. i.e. where <code>telecom.system</code> is set to a fixed value of <code>phone</code>, and <code>telecom.value</code> contains the telephone number</td>
    </tr>
  </tbody></table>

---

## Practitioner resource

The CareConnect-Practitioner-1 resource present in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-025">GPCM-SD-OC-025</td>
      <td>the SDS User ID of the practitioner <strong>MUST</strong> be present in the <code>sdsUserID</code> slice of the <code>identifier</code> element</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-026">GPCM-SD-OC-026</td>
      <td>the name of the practitioner <strong>MUST</strong> be present in the single instance of the <code>name</code> element where <code>name.use</code> is set to <code>official</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-027">GPCM-SD-OC-027</td>
      <td>telephone contact details <strong>MUST</strong> be present if available in the <code>telecom</code> element. i.e. <code>telecom.system</code> is set to a fixed value of <code>phone</code>, and <code>telecom.value</code> contains the telephone number</td>
    </tr>
  </tbody></table>

---

## RelatedPerson resource

The CareConnect-RelatedPerson-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-028">GPCM-SD-OC-028</td>
      <td>the name of the related person <strong>MUST</strong> be present in the single instance of the <code>name</code> element</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-029">GPCM-SD-OC-029</td>
      <td>the date of birth of the related person <strong>MUST</strong> be specified in <code>YYYY-MM-DD</code> format in the <code>birthDate</code> element. Birth time is not required</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-030">GPCM-SD-OC-030</td>
      <td>telephone contact details <strong>MUST</strong> be present if available in the <code>telecom</code> element</td>
    </tr>
  </tbody></table>

---

## Device resource

The ITK-Device-1 resource present in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-031">GPCM-SD-OC-031</td>
      <td>a SNOMED code describing the type of device <strong>MUST</strong> be present in the <code>type</code> element</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-032">GPCM-SD-OC-032</td>
      <td>the manufacturer of the device <strong>MUST</strong> be present in the <code>manufacturer</code> element</td>
    </tr>
  </tbody></table>

---

## Encounter resource

The CareConnect-Encounter-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-033">GPCM-SD-OC-033</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>finished</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-034">GPCM-SD-OC-034</td>
      <td>the <code>type</code> element <strong>MUST</strong> contain a valid SNOMED code for the type encounter being sent, for example <code>149971000000103</code> (Encounter using general practice online consultation system (procedure))</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-035">GPCM-SD-OC-035</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient who is the subject of the encounter</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-036">GPCM-SD-OC-036</td>
      <td>the <code>participant</code> element <strong>SHOULD</strong> reference the <code>Practitioner</code> profile or the <code>RelatedPerson</code> profile if applicable</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-037">GPCM-SD-OC-037</td>
      <td>the <code>priority</code> element <strong>SHOULD</strong> reference a priority code, by default this value should be <code>R</code> meaning routine</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-038">GPCM-SD-OC-038</td>
      <td>the <code>period</code> element <strong>SHOULD</strong> be populated with the start and end time of the encounter captured in the source system</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-039">GPCM-SD-OC-039</td>
      <td>the <code>serviceProvider</code> element <strong>SHOULD</strong> contain a reference to the organisation responsible for the encounter</td>
    </tr>
  </tbody></table>

---

## List resource

The CareConnect-List-1 in the payload is populated as follows:

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-040">GPCM-SD-OC-040</td>
      <td>a <code>List</code> containing references to all Observation resources that are captured <strong>MUST</strong> be populated if coded Observations are being sent. The <code>List</code> resource in FHIR is used to manage collections of resources.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-041">GPCM-SD-OC-041</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>current</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-042">GPCM-SD-OC-042</td>
      <td>the <code>mode</code> element <strong>MUST</strong> contain a fixed value of <code>snapshot</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-043">GPCM-SD-OC-043</td>
      <td>the <code>title</code> element <strong>MUST</strong> contain the <code>display</code> element from the <code>code</code> field</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-044">GPCM-SD-OC-044</td>
      <td>the <code>code</code> element <strong>MUST</strong> contain <code>826501000000100</code> - Miscellaneous record</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-045">GPCM-SD-OC-045</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient against whom the data was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-046">GPCM-SD-OC-046</td>
      <td>the <code>entry.item</code> element <strong>MUST</strong> be populated to reference each <code>Observation</code> in the message</td>
    </tr>
  </tbody></table>

---

## Observation resource

Each CareConnect-Observation-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-047">GPCM-SD-OC-047</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>preliminary</code> if unchecked by a clinician, or <code>final</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-048">GPCM-SD-OC-048</td>
      <td>the <code>category</code> element <strong>SHOULD</strong> contain high level category that represents the data in the <code>Observation</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-049">GPCM-SD-OC-049</td>
      <td>the <code>code</code> element <strong>MUST</strong> contain a clinical code that represents the data in the <code>Observation</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-050">GPCM-SD-OC-050</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient against whom the data was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-051">GPCM-SD-OC-051</td>
      <td>the <code>issued</code> element <strong>MUST</strong> contain an audit trail timestamp representing when the data was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-052">GPCM-SD-OC-052</td>
      <td>to ensure the <code>Observation</code> can be identified as patient entered data, the <code>performer</code> element <strong>MUST</strong> contain a reference to patient resource of the patient completing the Online Consultation</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-053">GPCM-SD-OC-053</td>
      <td>the <code>value[x]</code> element <strong>SHOULD</strong> contain the value of the <code>Observation</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-054">GPCM-SD-OC-054</td>
      <td>the <code>component</code> element <strong>SHOULD</strong> be populated if recording a pair of results</td>
    </tr>
  </tbody></table>

---

## Questionnaire resource

The CareConnect-Questionnaire-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-055">GPCM-SD-OC-055</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>active</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-056">GPCM-SD-OC-056</td>
      <td>the <code>version</code> element <strong>SHOULD</strong> contain the business version of the questionnaire</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-057">GPCM-SD-OC-057</td>
      <td>the <code>name</code> element <strong>SHOULD</strong> contain the name of the questionnaire</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-058">GPCM-SD-OC-058</td>
      <td>the <code>title</code> element <strong>SHOULD</strong> contain the title of the questionnaire</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-059">GPCM-SD-OC-059</td>
      <td>the <code>date</code> element <strong>SHOULD</strong> contain the date the questionnaire was last updated</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-060">GPCM-SD-OC-060</td>
      <td>the <code>description</code> element <strong>SHOULD</strong> contain a human readable description of the questionnaire</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-061">GPCM-SD-OC-061</td>
      <td>the <code>effectivePeriod</code> element <strong>SHOULD</strong> contain the period when the questionnaire is expected to be used</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-062">GPCM-SD-OC-062</td>
      <td>the <code>item</code> elements <strong>MUST</strong> be completed to contain the questions and sections of the questionnaire</td>
    </tr>
  </tbody></table>

---

## QuestionnaireResponse resource

The CareConnect-QuestionnaireResponse-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-063">GPCM-SD-OC-063</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>completed</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-064">GPCM-SD-OC-064</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient against whom the data was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-065">GPCM-SD-OC-065</td>
      <td>the <code>authored</code> element <strong>SHOULD</strong> contain an audit trail timestamp representing when the data was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-066">GPCM-SD-OC-066</td>
      <td>a set of <code>item</code> elements <strong>MUST</strong> contain the full online consultation questionnaire details</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-067">GPCM-SD-OC-067</td>
      <td>the <code>item.linkId</code> element <strong>MUST</strong> contain a pointer specific to the questionnaire</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-068">GPCM-SD-OC-068</td>
      <td>the <code>item.text</code> element <strong>MUST</strong> contain the question being asked</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-069">GPCM-SD-OC-069</td>
      <td>the <code>item.answer.value[x]</code> element <strong>MUST</strong> contain the answer being given by the patient</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-070">GPCM-SD-OC-070</td>
      <td>the <code>item.answer.value[x].valueReference</code> element <strong>SHOULD</strong> contain a reference to a resource, if applicable</td>
    </tr>
  </tbody></table>

---

## ReferralRequest resource

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-071">GPCM-SD-OC-071</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>unknown</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-072">GPCM-SD-OC-072</td>
      <td>the <code>intent</code> element <strong>MUST</strong> contain a fixed value of <code>order</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-073">GPCM-SD-OC-073</td>
      <td>the <code>priority</code> element <strong>SHOULD</strong> reference a priority code. A mapping is applied to the priority codes to align it to the e-Referral Service priority types. This <strong>MUST</strong> be populated where the source system has a referral priority which matches the e-Referral Service priority codes or can be mapped to those priority codes. If there is a priority code for the referral but it is incompatible with the e-Referral Service priorities, this element <strong>MUST</strong> be excluded and the priority <strong>MUST</strong> be supplied in the note element.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-074">GPCM-SD-OC-074</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient who is the subject of the referral</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-075">GPCM-SD-OC-075</td>
      <td>the <code>context</code> element <strong>SHOULD</strong> reference the <code>Encounter</code> within which the referral was recorded</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-076">GPCM-SD-OC-076</td>
      <td>the <code>requester</code> element <strong>SHOULD</strong> reference the details of the person, practitioner or organisation responsible for the decision to refer the patient or, if is not attributed specifically, then populate with the recorder</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-077">GPCM-SD-OC-077</td>
      <td>the <code>requester.agent</code> element <strong>MUST</strong> reference one of the following: <ul><li>a Practitioner resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1">CareConnect-Practitioner-1</a></li><li>an Organization resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1">CareConnect-Organization-1</a></li><li>a Patient resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1">CareConnect-Patient-1</a></li><li>a RelatedPerson resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-RelatedPerson-1">CareConnect-RelatedPerson-1</a></li><li>a Device resource profiled to <a href="https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Device-1">ITK-Device-1</a></li></ul></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-078">GPCM-SD-OC-078</td>
      <td>the <code>recipient</code> element <strong>SHOULD</strong> be populated with the practitioner and/or organisation the patient has been referred to, if that is recorded in a suitable coded format</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-079">GPCM-SD-OC-079</td>
      <td>the <code>reasonCode</code> element <strong>SHOULD</strong> be populated with the source system’s main coded entry for the referral</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-080">GPCM-SD-OC-080</td>
      <td>the <code>description</code> element <strong>SHOULD</strong> be populated with a free text description associated with the referral</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-081">GPCM-SD-OC-081</td>
      <td>the <code>supportingInfo</code> element <strong>SHOULD</strong> contain a reference to the referral letter(s) and any other supporting documents or resources which are not covered by other more specific elements, for instance this could include reference to linked observations</td>
    </tr>
  </tbody></table>

---

## DocumentReference resource

The CareConnect-DocumentReference-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-082">GPCM-SD-OC-082</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of either <code>current</code>, <code>superseded</code> or <code>entered-in-error</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-083">GPCM-SD-OC-083</td>
      <td>the <code>type</code> element <strong>MUST</strong> contain a coded entry that references the type of document, this <strong>SHOULD</strong> be taken from SNOMED refset 1127551000000109. Other classifications should be sent as <code>text</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-084">GPCM-SD-OC-084</td>
      <td>the <code>subject</code> element <strong>MUST</strong> reference the <code>Patient</code> profile representing the Patient who is the subject of the document</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-085">GPCM-SD-OC-085</td>
      <td>the <code>author</code> element <strong>SHOULD</strong> reference one of the following: <ul><li>a Practitioner resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1">CareConnect-Practitioner-1</a></li><li>an Organization resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1">CareConnect-Organization-1</a></li><li>a Patient resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1">CareConnect-Patient-1</a></li><li>a RelatedPerson resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-RelatedPerson-1">CareConnect-RelatedPerson-1</a></li><li>a Device resource profiled to <a href="https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Device-1">ITK-Device-1</a></li></ul></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-086">GPCM-SD-OC-086</td>
      <td>the <code>content</code> element <strong>MUST</strong> contain details about the document being referenced</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-087">GPCM-SD-OC-087</td>
      <td>the <code>context</code> element <strong>SHOULD</strong> contain details about the clinical context of the document being referenced</td>
    </tr>
  </tbody></table>

---

## AllergyIntolerance resource

The CareConnect-AllergyIntolerance-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-088">GPCM-SD-OC-088</td>
      <td>the <code>extension[encounter]</code> element <strong>SHOULD</strong> contain a reference to an associated encounter</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-089">GPCM-SD-OC-089</td>
      <td>the <code>extension[allergyEnd]</code> element <strong>MUST</strong> contain the date the allergy or intolerance was recorded as resolved, if the <code>clinicalStatus</code> is set to <code>resolved.</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-090">GPCM-SD-OC-090</td>
      <td>the <code>extension[allergyEnd].endReason</code> element <strong>MUST</strong> contain the reason why the allergy or intolerance has been resolved. In exceptional cases where for legacy data there is no endReason recorder in the system then this <strong>MUST</strong> be populated with the text ‘No information available’.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-091">GPCM-SD-OC-091</td>
      <td>the <code>clinicalStatus</code> element <strong>MUST</strong> be populated with <code>active</code> for all active allergies, or <code>resolved</code> for resolved allergies.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-092">GPCM-SD-OC-092</td>
      <td>the <code>verificationStatus</code> element <strong>MUST</strong> contain a fixed value of <code>unconfirmed</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-093">GPCM-SD-OC-093</td>
      <td>the <code>type</code> element <strong>SHOULD</strong> be set to <code>allergy</code> for reactions which are allergenic in nature (immunological), a value of <code>intolerance</code> <strong>MAY</strong> be used to indicate adverse reactions (not immunologic in nature). Where the type is unknown the type element may be omitted.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-094">GPCM-SD-OC-094</td>
      <td>the <code>category</code> element <strong>MUST</strong> use <code>medication</code> for all drug allergy types, <code>environment</code> for all non-drug allergies. The other values in the ValueSet (food and biologic) <strong>MUST NOT</strong> be used.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-095">GPCM-SD-OC-095</td>
      <td>the <code>criticality</code> element <strong>SHOULD</strong> used to distinguish between life-threatening (high) and non-life-threatening (low) potential as well as unable-to-assess. It <strong>MAY</strong> be used in addition to severity within the reaction element to express severity - for example, systems that support a severity of life-threatening <strong>MAY</strong> set criticality to high.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-096">GPCM-SD-OC-096</td>
      <td>the <code>criticality</code> element <strong>SHOULD</strong> used to distinguish between life-threatening (high) and non-life-threatening (low) potential as well as unable-to-assess. It <strong>MAY</strong> be used in addition to severity within the reaction element to express severity - for example, systems that support a severity of life-threatening <strong>MAY</strong> set criticality to high.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-097">GPCM-SD-OC-097</td>
      <td>the <code>code</code> element <strong>MUST</strong> contain the causative agent such as food, drug or substances that has caused or may cause an allergy, intolerance or adverse reaction in this patient.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-098">GPCM-SD-OC-098</td>
      <td>the <code>patient</code> element <strong>MUST</strong> contain a reference to the Patient who has, or had, the allergy or intolerance specified.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-099">GPCM-SD-OC-099</td>
      <td>the <code>onset.DateTime</code> element <strong>SHOULD</strong> contain a date when allergy/intolerance first manifested. Currently restricted to values of dateTime for GP Connect.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-100">GPCM-SD-OC-100</td>
      <td>the <code>assertedDate</code> element <strong>MUST</strong> contain a the datetime the record was believed to be true.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-101">GPCM-SD-OC-101</td>
      <td>the <code>recorder</code> element <strong>MUST</strong> contain a reference to who recorded the allergy.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-102">GPCM-SD-OC-102</td>
      <td>the <code>asserter</code> element <strong>SHOULD</strong> contain a reference to the source of the information about the allergy.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-103">GPCM-SD-OC-103</td>
      <td>the <code>lastOccurrence</code> element <strong>SHOULD</strong> contain the date and/or time of the last known occurrence of a reaction event.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-104">GPCM-SD-OC-104</td>
      <td>the <code>note</code> element <strong>SHOULD</strong> contain all text associated with the AllergyIntolerance including user-entered notes and qualifiers is grouped together and expressed in this field, which ensures unmapped coded values or qualifiers are not lost. <strong>MUST</strong> be used to contain any textual data relevant to the allergy.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-105">GPCM-SD-OC-105</td>
      <td>the <code>reaction.manifestation</code> element <strong>SHOULD</strong> contain the reaction resulting from the allergy/intolerance as a code.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-106">GPCM-SD-OC-106</td>
      <td>the <code>reaction.description</code> element <strong>SHOULD</strong> contain the textual description of the manifestation where no code is available.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-107">GPCM-SD-OC-107</td>
      <td>the <code>reaction.severity</code> element <strong>SHOULD</strong> contain severities of <code>Mild</code>, <code>Moderate</code>, <code>Severe</code> are mapped directly to the ValueSet. Map life threatening to <code>Severe</code> and populate criticality with <code>high</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-108">GPCM-SD-OC-108</td>
      <td>the <code>reaction.exposureRoute</code> element <strong>SHOULD</strong> contain the route by which exposure to the substance causing the reaction occurred. Utilise the dm+d route codes.</td>
    </tr>
  </tbody></table>

---

## FamilyMemberHistory resource

The CareConnect-FamilyMemberHistory-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-109">GPCM-SD-OC-109</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of either <code>partial</code>, <code>completed</code>, <code>entered-in-error</code>, or <code>health-unknown</code></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-110">GPCM-SD-OC-110</td>
      <td>the <code>patient</code> element <strong>MUST</strong> contain a reference to the Patient that the history is about.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-111">GPCM-SD-OC-111</td>
      <td>the <code>relationship</code> element <strong>MUST</strong> contain a coded entry describing the nature of the relationship between the patient and the related person being described in the family history.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-112">GPCM-SD-OC-112</td>
      <td>the <code>reasonReference</code> element <strong>SHOULD</strong> reference one of the following: <ul><li>a QuestionnaireResponse resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-QuestionniareResponse-1">CareConnect-QuestionnaireResponse-1</a></li><li>an Observation resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Observation-1">CareConnect-Observation-1</a></li><li>a AllergyIntolerance resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-AllergyIntolerance-1">CareConnect-AllergyIntolerance-1</a></li></ul></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-113">GPCM-SD-OC-113</td>
      <td>the <code>note</code> element <strong>SHOULD</strong> contain all text associated with the related person.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-114">GPCM-SD-OC-114</td>
      <td>the <code>condition</code> element <strong>SHOULD</strong> contain the details of the condition that the related person had.</td>
    </tr>
  </tbody></table>

---

## Task resource

The CareConnect-Task-1 in the payload is populated as follows:

<table class="requirement-box">
    <tbody><tr>
      <td id="GPCM-SD-OC-115">GPCM-SD-OC-115</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>requested</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-116">GPCM-SD-OC-116</td>
      <td>the <code>statusReason</code> element <strong>SHOULD</strong> contain a code to identify the reason for the current status.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-117">GPCM-SD-OC-117</td>
      <td>the <code>intent</code> element <strong>MUST</strong> contain a fixed value of either <code>proposal</code>, <code>plan</code>, or <code>order</code>, to distinguish whether the task is a proposal, plan or full order.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-118">GPCM-SD-OC-118</td>
      <td>the <code>priority</code> element <strong>SHOULD</strong> contain a fixed value of either <code>normal</code>, <code>urgent</code>, <code>asap</code>, or <code>stat</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-119">GPCM-SD-OC-119</td>
      <td>the <code>code</code> element <strong>SHOULD</strong> contain codes to identify what the task involves. These will typically be specific to a particular workflow.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-120">GPCM-SD-OC-120</td>
      <td>the <code>for</code> element <strong>SHOULD</strong> contain a reference to the Patient.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-121">GPCM-SD-OC-121</td>
      <td>the <code>context</code> element <strong>SHOULD</strong> contain a reference to the Encounter which this task originated.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-122">GPCM-SD-OC-122</td>
      <td>the <code>requester.agent</code> element <strong>SHOULD</strong> reference one of the following: <ul><li>a Practitioner resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1">CareConnect-Practitioner-1</a></li><li>an Organization resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1">CareConnect-Organization-1</a></li><li>a Patient resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1">CareConnect-Patient-1</a></li><li>a RelatedPerson resource profiled to <a href="https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-RelatedPerson-1">CareConnect-RelatedPerson-1</a></li><li>a Device resource profiled to <a href="https://fhir.nhs.uk/STU3/StructureDefinition/ITK-Device-1">ITK-Device-1</a></li></ul></td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-123">GPCM-SD-OC-123</td>
      <td>the <code>owner</code> element <strong>SHOULD</strong> contain a reference a resource responsible for the task execution.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-124">GPCM-SD-OC-124</td>
      <td>the <code>reason</code> element <strong>SHOULD</strong> contain details explaining why the task is needed.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-125">GPCM-SD-OC-125</td>
      <td>the <code>note</code> element <strong>SHOULD</strong> contain comments made about the task.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-126">GPCM-SD-OC-126</td>
      <td>the <code>restriction</code> element <strong>SHOULD</strong> be populated if there are any limitations on what parts of the referenced request should be actioned.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-127">GPCM-SD-OC-127</td>
      <td>the <code>input</code> element <strong>SHOULD</strong> contain additional information that may be needed in the execution of the task.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-128">GPCM-SD-OC-128</td>
      <td>the <code>output</code> element <strong>SHOULD</strong> contain any outputs produced by the task.</td>
    </tr>
  </tbody></table>

---

## Consent resource

The CareConnect-Consent-1 in the payload is populated as follows:


<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-129">GPCM-SD-OC-129</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of either <code>proposed</code>, <code>active</code>, or <code>rejected</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-130">GPCM-SD-OC-130</td>
      <td>the <code>category</code> element <strong>SHOULD</strong> contain a classification of the type of consent found in the statement.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-131">GPCM-SD-OC-131</td>
      <td>the <code>patient</code> element <strong>MUST</strong> contain a reference to the Patient the consent applies to.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-132">GPCM-SD-OC-132</td>
      <td>the <code>period</code> element <strong>SHOULD</strong> contain a the period this consent applies to.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-133">GPCM-SD-OC-133</td>
      <td>the <code>consentingParty</code> element <strong>SHOULD</strong> contain a reference to who is agreeing to the policy and exceptions.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-134">GPCM-SD-OC-134</td>
      <td>the <code>action</code> element <strong>SHOULD</strong> contain any actions controlled by this consent.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-135">GPCM-SD-OC-135</td>
      <td>the <code>source[x]</code> element <strong>SHOULD</strong> reference the source from which the consent was taken.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-136">GPCM-SD-OC-136</td>
      <td>the <code>policy</code> element <strong>SHOULD</strong> contain any policies covered by this consent.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-137">GPCM-SD-OC-137</td>
      <td>the <code>purpose</code> element <strong>SHOULD</strong> contain the context of activities for which the agreement is made.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-138">GPCM-SD-OC-138</td>
      <td>the <code>datePeriod</code> element <strong>SHOULD</strong> contain timeframe for data controlled by this consent.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-139">GPCM-SD-OC-139</td>
      <td>the <code>data</code> element <strong>SHOULD</strong> contain the data controlled by this consent.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-140">GPCM-SD-OC-140</td>
      <td>the <code>except</code> element <strong>SHOULD</strong> contain any exceptions to the base policy of this consent. An exception can be an addition or removal of access permissions.</td>
    </tr>
  </tbody></table>

---

## Location resource

The CareConnect-Location-1 in the payload is populated as follows:

<table class="nhsd-!t-margin-bottom-6" data-responsive>
    <tbody><tr>
      <td id="GPCM-SD-OC-168">GPCM-SD-OC-168</td>
      <td>the <code>identifier</code> element <strong>MUST</strong> contain a Site ODS code to identify the organization at site level.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-169">GPCM-SD-OC-169</td>
      <td>the <code>status</code> element <strong>MUST</strong> contain a fixed value of <code>active</code>.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-170">GPCM-SD-OC-170</td>
      <td>the <code>name</code> element <strong>MUST</strong> contain the name of the location used by humans.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-171">GPCM-SD-OC-171</td>
      <td>the <code>type</code> element <strong>SHOULD</strong> contain the type of function being performed at this location.</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-172">GPCM-SD-OC-172</td>
      <td>the <code>telecom</code> element <strong>MUST</strong> contain the telephone number of that location. i.e. where <code>telecom.system</code> is set to a fixed value of <code>phone</code>, and <code>telecom.value</code> contains the telephone number</td>
    </tr>
    <tr>
      <td id="GPCM-SD-OC-173">GPCM-SD-OC-173</td>
      <td>the <code>address</code> element <strong>SHOULD</strong> contain the physical address of the location</td>
    </tr>
  </tbody></table>

---