## {{page-title}}
    
  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

<!--An FGM-IS indicator (family history of FGM) has been modelled around a FHIR R4 Flag. Refer to {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-Flag.page.md}} profile for further guidance. 

| Source Data item               | Cardinality |Target FHIR Element                 | Notes         
|--|--|
|Assessment Date|1..1|Flag.period.start|type: <a href='http://hl7.org/fhir/R4/datatypes.html#dateTime'>dateTime</a><br>format: YYYY-MM-DD
|NHS Number|1..1|Flag.identifier:nhsNumber|type: <a href='http://hl7.org/fhir/R4/search.html#token'>token</a><br>system must be "https://fhir.nhs.uk/Id/nhs-number"<br>value must be a verified NHS number<br>note: a resource reference is not required for FGM-IS. E.g. - {{pagelink:Home/Examples/Example---An-active-FGM-flag.page.md}} 
|Family history of FGM indicator|1..1|Flag.code.coding|system must be "http://snomed.info/sct"<br>code must be "902961000000107"<br>display must be "Family history of FGM (female genital mutilation)"
|Status|1..1|Flag.status|See {{pagelink:Home/FHIRAssets/AllAssets/Profiles/UKCore-Flag.page.md}}
|Removal Reason|0..1|reference {{pagelink:Home/FHIRAssets/Extensions.page.md}}|must be set when Flag.status is not 'active'. E.g. {{pagelink:Home/Examples/Example---A-removed-FGM-flag.page.md}} <br>set on PUT /Flag interaction. E.g. {{pagelink:Home/Design/Interactions.page.md}}-->








### <a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization?version=current">UKCore-Organization</a>

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
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/ExtensionLibrary/Extension-UKCore-MainLocation.page.md?version=current">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension (organization-period)</td>
            <td>0..1</td>
            <td><code>0..0</code></td>
            <td>DO NOT USE</td>
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
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-OrganisationRole.page.md?version=current">Extension</a></td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />instanceID</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.UniqueRoleID</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-OrganisationRole.page.md?version=current">Integer</a></td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />roleCode</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.RoleID / RoleName</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-OrganisationRole.page.md?version=current">CodeableConcept</a></td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />typedPeriod</td>
            <td>1..*</td>
            <td><code>0..2</code></td>
            <td>Optional</td>
            <td>Roles.LegalStartDate,<br>Roles.LegalEndDate,<br>Roles.OperationalStartDate,<br>Roles.OperationalEndDate</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-OrganisationRole.page.md?version=current">Extension</a></td>
            <td></td>
        </tr>
       <tr>
            <td>ExtensionEnglandOrganisationRole.<br />active</td>
            <td>1..1</td>
            <td>1..1</td>
            <td>NOT NULL</td>
            <td>Roles.status</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-OrganisationRole.page.md?version=current">Boolean</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension <br />(ExtensionEnglandTypedDateTime)</td>
            <td>Not defined</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.LastChangeDate</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-TypedDateTime.page.md?version=current">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>extension <br />(ExtensionEnglandTypedPeriod)</td>
            <td>Not defined</td>
            <td><code>0..2</code></td>
            <td>Optional</td>
            <td>Organisation.LegalStartDate,<br>Organisation.LegalEndDate,<br>Organisation.OperationalStartDate,<br>Organisation.OperationalEndDate</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-TypedPeriod.page.md?version=current">Extension</a></td>
            <td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.OrganisationCode</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization?version=current#identifier">Identifier</a></td>
            <td>The ODS Organisation Code for the organisation <b>SHALL</b> be used to populate the <code>odsOrganisationCode</code> slice of the <code>identifier</code> element.</td>
        </tr>
        <tr>
            <td>identifier.assigner.value</td>
            <td>0..*</td>
            <td><code>0..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.AssigingAuthorityName</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization?version=current#identifier">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td>0..1</td>
            <td>Optional</td>
            <td>Organisation.StatusName</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td>Status dropped from Final table - publish StatusName only. ACTIVE or INACTIVE</td>
        </tr>
        <tr>
            <td>type</td>
            <td>0..*</td>
            <td><code>2..*</code></td>
            <td>NOT NULL</td>
            <td>Organisation.RefOnly,<br>Organisation.RecordClass,<br>Organisation.RecordClass<br />Description</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td>One each of:<br>
            <a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Terminology/All-CodeSystems/CodeSystem-England-ODSRecordClass.page.md?version=current">CodeSystemEnglandODSRecordClass</a><br>
            <a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Terminology/All-CodeSystems/CodeSystem-England-ODSRecordUseType.page.md?version=current">CodeSystemEnglandODSRecordUseType</a>
            </td>
        </tr>
        <tr>
            <td>name</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Organisation.OrgName</td>
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
            <td>Telephone number is nullified for RefOnly/skeleton records</td>
        </tr>
        <tr>
            <td>address</td>
            <td>0..*</td>
            <td><code>1..*</code></td>
            <td>Country NOT NULL</td>
<td>Organisation.Address1<br>Organisation.Address2<br>Organisation.Address3<br>Organisation.Town<br>Organisation.County<br>Organisation.Postcode<br>Organisation.Country</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#Address">Address</a></td>
            <td>Country is NOT NULL</td>
        </tr>
        <tr>
            <td>address.extension (ExtensionUKCoreAddressKey)</td>
            <td>Not defined</td>
            <td>0..*</td>
            <td>Optional</td>
            <td>Organisation.URPN</td>
            <td><a href="https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/ExtensionLibrary/Extension-UKCore-AddressKey.page.md?version=current">Extension</a></td>
            <td>Publish via R4 only (not STU3 and ORD like for like as not currently published)</td>
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



### <a href="https://simplifier.net/guide/UKCoreImplementationGuideAssetsinDevelopment/Home/ProfilesandExtensions/Profile-UKCore-OrganizationAffiliation?version=current">UKCore-OrganizationAffiliation</a>

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
            <td><code>0..2</code></td>
            <td>Optional</td>
            <td>Relationships.LegalStartDate,<br>Relationships.LegalEndDate,<br>Relationships.OperationalStartDate,<br>Relationships.OperationalEndDate</td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Profiles-and-Extensions/All-Extensions/Extension-England-TypedPeriod.page.md?version=current">Extension</a></td>
            <td>Would be worth slicing?</td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>0..*</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Relationships.UniqueRelID</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#identifier">Identifier</a></td>
            <td></td>
        </tr>
        <tr>
            <td>active</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Relationships.Status</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#boolean">boolean</a></td>
            <td>Set to active/inactive based on both date concepts</td>
        </tr>
        <tr>
            <td>period</td>
            <td>0..1</td>
            <td><code>0..0</code></td>
            <td>DO NOT USE</td>
            <td></td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#period">period</a></td>
            <td>Use ExtensionEnglandTypedPeriod instead</td>
        </tr>
        <tr>
            <td>organization</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Relationships.SourceOrgID / SourceOrgCode</td>
            <td><a href=" https://hl7.org/fhir/R4/datatypes.html#Reference">Reference</a></td>
            <td></td>
        </tr>
        <tr>
            <td>participatingOrganization</td>
            <td>0..1</td>
            <td><code>1..1</code></td>
            <td>NOT NULL</td>
            <td>Relationships.TargetOrgID / TargetOrgCode</td>
            <td><a href=" https://hl7.org/fhir/R4/references.html">Reference</a></td>
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
            <td>Relationships.RelTypeID / Relationships.RelTypeName / RelationshipDefinition.RelDefinition</td>
            <td><a href="https://hl7.org/fhir/R4/datatypes.html#CodeableConcept">CodeableConcept</a></td>
            <td><a href="https://simplifier.net/guide/nhs-england-implementation-guide-stu1/Home/Terminology/All-CodeSystems/CodeSystem-England-ODSRelationship.page.md?version=current">CodeSystemEnglandODSRelationship</a></td>
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
