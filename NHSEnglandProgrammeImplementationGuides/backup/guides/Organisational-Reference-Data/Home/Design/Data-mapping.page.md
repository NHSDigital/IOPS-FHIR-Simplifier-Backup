## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

This page defines how the data is mapped between relevant FHIR asset elements and the domain fields for ODS.

The relevant FHIR assets included in the mapping tables are Profiles 'UKCore-Organization', 'UKCore-OrganizationAffiliation', and associated Extensions usable for the ODS API. The domain fields are existing elements of data that will be shared with users of the ODS API solution. 

All of the relevant elements for Profiles 'UKCore-Organization' and 'UKCore-OrganizationAffiliation', and relevant Extensions, are listed to illustrate that all of the domain fields for ODS are able to be mapped to existing Profiles and Extensions.

<!--An FGM-IS indicator (family history of FGM) has been modelled around a FHIR R4 Flag. Refer to {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-Flag.page.md}} profile for further guidance. 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Assessment Date|1..1|Flag.period.start|type: <a href='http://hl7.org/fhir/R4/datatypes.html#dateTime'>dateTime</a><br>format: YYYY-MM-DD
|NHS Number|1..1|Flag.identifier:nhsNumber|type: <a href='http://hl7.org/fhir/R4/search.html#token'>token</a><br>system must be "https://fhir.nhs.uk/Id/nhs-number"<br>value must be a verified NHS number<br>note: a resource reference is not required for FGM-IS. E.g. - {{pagelink:Home/Examples/Example---An-active-FGM-flag.page.md}} 
|Family history of FGM indicator|1..1|Flag.code.coding|system must be "http://snomed.info/sct"<br>code must be "902961000000107"<br>display must be "Family history of FGM (female genital mutilation)"
|Status|1..1|Flag.status|See {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-Flag.page.md}}
|Removal Reason|0..1|reference {{pagelink:Home/FHIRAssets/Extensions.page.md}}|must be set when Flag.status is not 'active'. E.g. {{pagelink:Home/Examples/Example---A-removed-FGM-flag.page.md}} <br>set on PUT /Flag interaction. E.g. {{pagelink:Home/Design/Interactions.page.md}}-->








### {{pagelink:UKCore-Organization}}

<table class="regular">
    <thead>
        <tr>
            <th width="15%">Element Name</th>
            <th width="10%">Profile Cardinality</th>
            <th width="10%">Domain Cardinality</th>
            <th width="10%">Domain Optionality</th>
            <th width="10%">Domain Field</th>
            <th width="10%">Type</th>
            <th width="35%">Definition, Constraints and Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>extension (mainLocation)</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/ExtensionLibrary/Extension-UKCore-MainLocation">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (organization-period)</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td></td>
            <td><a href="https://www.hl7.org/fhir/R4/extension-organization-period.html">Extension</a></td>
            <td>Use ExtensionEnglandTypedPeriod instead</td>
        </tr>
        <tr>
            <td>extension <br />(ExtensionEnglandOrganisationRole)</td>
            <td>Not defined</td>
            <td><code>1..*</code></td>
            <td> </td>
            <td> </td>
            <td>{{pagelink:Extension-England-OrganisationRole,text:Extension}}</td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />instanceID</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.UniqueRoleID</td>
            <td>{{pagelink:Extension-England-OrganisationRole,text:Integer}}</td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />roleCode</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.RoleID</td>
            <td>{{pagelink:Extension-England-OrganisationRole,text:CodeableConcept}}</td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />typedPeriod</td>
            <td>1..*</td>
            <td>1..*</td>
            <td>NOT NULL</td>
            <td>Roles.LegalStartDate,<br>Roles.LegalEndDate,<br>Roles.OperationalStartDate,<br>Roles.OperationalEndDate</td>
            <td>{{pagelink:Extension-England-OrganisationRole,text:Extension}}</td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />active</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.status</td>
            <td>{{pagelink:Extension-England-OrganisationRole,text:Boolean}}</td>
            <td></td>
        </tr>
        <tr>
            <td>extension <br />(ExtensionEnglandTypedDateTime)</td>
            <td>Not defined</td>
            <td><code>1..*</code></td>
            <td>NOT NULL</td>
            <td>Organisation.LastChangeDate</td>
            <td>{{pagelink:Extension-England-TypedDateTime,text:Extension}}</td>
            <td></td>
        </tr>
        <tr>
            <td>extension <br />(ExtensionEnglandTypedPeriod)</td>
            <td>Not defined</td>
            <td><code>0..*</code></td>
            <td>Optional</td>
            <td>Organisation.LegalStartDate,<br>Organisation.LegalEndDate,<br>Organisation.OperationalStartDate,<br>Organisation.OperationalEndDate</td>
            <td>{{pagelink:Extension-England-TypedPeriod,text:Extension}}</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.OrganisationCode</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization#identifier">Identifier</a></td>
            <td>The ODS Organisation Code for the organisation <b>SHALL</b> be used to populate the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element.</td>
        </tr>
        <tr>
            <td>identifier.assigner.value</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td>Organisation.AssigingAuthorityName</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization#identifier">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td>Organisation.Status</td>
            <td </td>
            <td> </td>
        </tr>
        <tr>
            <td>type</td>
            <td>0..*</td>
            <td><code>2..*</code></td>
            <td>NOT NULL</td>
            <td>Organisation.RefOnly,<br>Organisation.RecordClass</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>One each of:<br>
            {{pagelink:CodeSystem-England-ODSRecordClass}}<br>
            {{pagelink:CodeSystem-England-ODSRecordUseType}}
            </td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.Name</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td>The name of the organisation <b>SHALL</b> be populated.</td>
        </tr>
        <tr>
            <td>alias</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#string">string</a></td>
            <td></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td>Organisation.TelephoneNumber, Organisation.HTTP</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#ContactPoint">ContactPoint</a></td>
            <td>Telephone number is nullified for RefOnly/skeleton records.<br />system='phone' and system='url'</td>
        </tr>
        <tr>
            <td>address</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
<td>Location.AddrLn1<br>Location.AddrLn2<br>Location.AddrLn3<br>Location.Town<br>Location.County<br>Location.Postcode</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Address">Address</a></td>
            <td></td>
        </tr>
        <tr>
            <td>address.extension (ExtensionUKCoreAddressKey)</td>
            <td>Not defined</td>
            <td>0..*</td>
            <td>Optional</td>
            <td>Location.URPN</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/ExtensionLibrary/Extension-UKCore-AddressKey">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>partOf</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td>Use OrganizationAffiliation instead</td>
        </tr>
        <tr>
            <td>contact</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/backboneelement.html">BackboneElement</a></td>
            <td></td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>



### {{pagelink:UKCore-OrganizationAffiliation}}

<table class="regular">
    <thead>
        <tr>
            <th width="15%">Element Name</th>
            <th width="10%">Profile Cardinality</th>
            <th width="10%">Domain Cardinality</th>
            <th width="10%">Domain Optionality</th>
            <th width="10%">Domain Field</th>
            <th width="10%">Type</th>
            <th width="35%">Definition, Constraints and Notes</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>extension (ExtensionEnglandTypedPeriod)</td>
            <td>Not defined</td>
            <td><code>0..*</code></td>
            <td>Optional</td>
            <td>rel.LegalStart,<br>rel.LegalEnd,<br>rel.OperationalStart,<br>rel.OperationalEnd</td>
            <td>{{pagelink:Extension-England-TypedPeriod,text:Extension}}</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>rel.UniqueRelID</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#identifier">Identifier</a></td>
            <td></td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>rel.Status</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td>Set to active/inactive based on both date concepts</td>
        </tr>
        <tr>
            <td>period</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#period">period</a></td>
            <td>Use ExtensionEnglandTypedPeriod instead</td>
        </tr>
        <tr>
            <td>organization</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation Identifier</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Reference">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>participatingOrganization</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>rel.TargetOrgID</td>
            <td><a href="https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>network</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>rel.TypeID / rel.TypeName</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>{{pagelink:CodeSystem-England-ODSRelationship}}</td>
        </tr>
        <tr>
            <td>specialty</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td></td>
        </tr>
        <tr>
            <td>location</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>healthcareService</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>telecom</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#ContactPoint">ContactPoint</a></td>
            <td></td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>0..*</td>
            <td>0..*</td>
            <td>Optional</td>
            <td></td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
            <td></td>
        </tr>
    </tbody>
</table>
