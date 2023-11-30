## {{page-title}}

The list below contains the element differences between the HL7 FHIR R4 and NHS England IG.

### Base Resource Definitions

View further information about <a href="https://www.hl7.org/fhir/R4/resource.html" Target="_blank">FHIR base resource definitions</a>.

<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
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
        <td>In the NHS England IG the format is the following, with the NamingSystem id in PascalCase:<br/><br/><code>NamingSystem-England-[Name]</code>.</td>
    </tr>
    </tbody>
</table>

### DomainResource Resource

View further information about <a href="https://www.hl7.org/fhir/R4/domainresource.html" Target="_blank">FHIR domain resources</a>.


<table class="assets">
  <thead>
      <tr>
        <th width="15%">Element name</th>
        <th width="10%">Base Cardinality</th>
        <th width="10%">NHS England IG Cardinality</th>
        <th width="15%">Type</th>
        <th width="50%">Definition, Constraints and Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
        <td>name</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>In NHS England IG the format is PascalCase:<br/><br/><code> England[Name]</code>.</td>
    </tr>
    <tr>
        <td>status</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England IG these are defined as: 
        <ul>
        <li>draft - NamingSystem in development</li>
        <li>active - NamingSystem that have been approved via Clinical and Technical Assurance</li>
        <li>retired - NamingSystem that is no longer required</li>
        </ul></td>
    </tr>
    <tr>
        <td>kind</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For the NHS England IG these are defined as: 
        <ul>
        <li>codesystem - The naming system is used to define concepts and symbols to represent those concepts; e.g. UCUM, LOINC, NDC code, local lab codes, etc.</li>
        <li>identifier - The naming system is used to manage identifiers (e.g. license numbers, order numbers, etc.).</li>
        <li>root - The naming system is used as the root for other identifiers and naming systems.</li>
        </ul></td>
    </tr>
        <td>date</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>dateTime</td>
        <td>Only the date, without time, is populated in NHS England IG.</td>
    </tr>
    <tr>
        <td>publisher</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all NHS England NamingSystems, where the base URL is <code>https://*.nhs.uk/</code>, this will be <code>NHS England</code>.</td>
    </tr>
    <tr>
        <td>contact</td>
        <td>0..*</td>
        <td>1..*</td>
        <td>ContactDetail</td>
        <td>For the NHS England NamingSystem these are defined as: 
         <ul>
        <li>Contact details for the publisher SHALL be added.</li>
        <li>Contact details for the team responsible for the NamingSystem MAY be added, where appropriate.</li>
        </ul>
See the {{pagelink:Publisher--Contact---Copyright}} for details of how this SHALL be populated for all NHS England NamingSystem, where the base URL is <code> https://*.nhs.uk/</code>.<BR>
<BR>
If additional contact details SHALL be added, then the rank value SHALL be automatically increased by "1".
For example now in the above context the rank value is "1" but if additonal contact will be added then the rank value MUST be "2".

</td>
    </tr>
    <tr>
        <td>responsible</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>For all NHS England NamingSystems, where the base URL is <code>https://*.nhs.uk/</code>, this will be <code>NHS England</code>.</td>
    </tr>
    <tr>
        <td>type</td>
        <td>0..1</td>
        <td>0..0</td>
        <td>string</td>
        <td>Not needed as we don't manage a list of types</code>.</td>
    </tr>
        <td>description</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>markdown</td>
         <td>The NHS England IG mandates the use of this element.</td>
    </tr>
    </tr>
        <td>useContext</td>
        <td>0..*</td>
        <td>0..0</td>
        <td>UsageContext</td>
         <td>Not needed as we don't manage a list of use contexts.</td>
    </tr>
    </tr>
        <td>jurisdiction</td>
        <td>0..*</td>
        <td>0..0</td>
        <td>CodeableConcept</td>
         <td>Not needed as it's within realm of England only.</td>
    </tr>
    </tr>
        <td>usage</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
         <td>A description of how and where the NamingSystem is used.</td>
    </tr>
        </tr>
        <td>uniqueId</td>
        <td>1..*</td>
        <td>1..*</td>
        <td>BackboneElement</td>
         <td>Unique identifiers used for system.</td>
    </tr>
    </tbody>
</table>