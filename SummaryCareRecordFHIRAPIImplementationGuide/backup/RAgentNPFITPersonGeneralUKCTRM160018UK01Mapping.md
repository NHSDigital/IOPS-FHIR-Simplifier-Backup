## R_AgentNPFITPersonGeneral

This page shows the commonly used CMET R_AgentNPFITPersonGeneral (UKCT_RM160018UK01) mapping to FHIR.

This page will be referenced from the appropriate CRETypes pages.

<div class="summary-structure-img">
{{render:PersonGeneral}}
</div>

When using the AgentNPFITPersonGeneral CMET, there is a choice of author format

## When using AgentPersonSDS

Agennt Person SDS (and Person SDS) are fulfilled in FHIR by the use of PractitionerRole & Practitioner

**AgentPersonSDS**

||Mapping|
|--
|**Item**|@classCode|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "AGNT"<br/>FHIR: no mapping|
|||
|**Item**|id@root|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/id/@root|
|**FHIR**|PractitionerRole/identifier/system/@value|
|**Notes**|HL7v3: Fixed to 1.2.826.0.1285.0.2.0.67<br/>FHIR: Fixed to "http://fhir.nhs.net/Id/sds-role-profile-id"|
|**Item**|id@extension|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/id/@extension|
|**FHIR**|PractitionerRole/identifier/value/@value|
|**Notes**|The SDSRole ProfileID|

**PersonSDS**<a name="PersonSDS"></a>

||Mapping|
|--
|**Item**|@classCode|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPersonSDS/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|@determinerCode|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPersonSDS/@determinerCode
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|id@root|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPersonSDS/id/@root|
|**FHIR**|Practitioner/identifier/system/@value|
|**Notes**|HL7v3: Fixed to ".2.826.0.1285.0.2.0.65"<br/>FHIR: Fixed to "https://fhir.nhs.uk/Id/sds-user-id"|
|||
|**Item**|id@extension|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPersonSDS/id/@extension|
|**FHIR**|Practitioner/identifier/value/@value|
|**Notes**|The SDSUserID|
|||
|**Item**|name|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPersonSDS/name|
|**FHIR**|Practitioner/name|
|**Notes**|Name of the author|

**HL7v3**
```xml
<UKCT_MT160018UK01.AgentPersonSDS classCode="AGNT">
   <id root="1.2.826.0.1285.0.2.0.67" extension="123456"></id>
   <agentPersonSDS classCode="PSN" determinerCode="INSTANCE">
    <id root="1.2.826.0.1285.0.2.0.65" extension="RT555"></id>
    <name>BLOGGS Fred</name>
   </agentPersonSDS>
  </UKCT_MT160018UK01.AgentPersonSDS>
```      
**FHIR**      
```xml
<PractitionerRole>
	<id value="83c26c8f-ee72-4534-8891-0136972b2106"/>
	<identifier>
		<system value="http://fhir.nhs.net/Id/sds-role-profile-id"/>
		<value value="123456"/>
	</identifier>
	<practitioner>
		<reference value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
	</practitioner>
</PractitionerRole>

<Practitioner>
	<id value="b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
	<identifier>
		<system value="https://fhir.nhs.uk/Id/sds-user-id"/>
		<value value="RT555"/>
	</identifier>
	<name>
		<family value="BLOGGS"/>
		<given value="Fred"/>
	</name>
</Practitioner>
```
## When using AgentPerson

**AgentPerson**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "AGNT"|
|||
|**Item**|**code@code**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/code/@code|
|**FHIR**|PractitionerRole/code/coding/code/@value|
|**Notes**|A jobRole code|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/code/@codeSystem|
|**FHIR**|PractitionerRole/code/coding/system/@value|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.17.124"<br/>FHIR: Fixed to"https://fhir.nhs.uk/CodeSystem/HL7v3-SDSJobRoleName"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/code/@displayName|
|**FHIR**|PractitionerRole/code/coding/dispaly/@value|
|**Notes**|Display of the code|
|||
|**Item**|**addr**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/addr|
|**FHIR**|organization/address|
|**Notes**|Address of the organisation|
|||
|**Item**|**telecom**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/telecom|
|**FHIR**|organization/telecom|
|**Notes**|Organisation telecom|

**Organization** (if using this option)

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/@classCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "ORG"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/@determinerCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "INSTANCE"|
|||
|**Item**|**code@code**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/code/@code|
|**FHIR**|organization/type/coding/code/@value|
|**Notes**|org type<br/>FHIR:Just use the code |
|||
|**Item**|**name**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/name|
|**FHIR**|organization/name/@value|
|**Notes**||
|||
|**Item**|**desc**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/desc|
|**FHIR**|no mapping|
|**Notes**||
|||
|**Item**|**addr**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganization/addr|
|**FHIR**|organization/address|
|**Notes**||

**OrganizationSDS** (if using this option)

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganizationSDS/@classCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "ORG"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganizationSDS/@determinerCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "INSTANCE"|
|||
|**Item**|**id@root**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganizationSDS/id/@root|
|**FHIR**|organization/identifier/system/@value|
|**Notes**|HL7v3: Fixed to "1.2.826.0.1285.0.1.10" (for org) "1.2.826.0.1285.0.2.0.109" (for workgroup)<br/>FHIR: Fixed to "https://fhir.nhs.uk/Id/ods-organization-code" (for org); workgroup system id not available for workgroups |
|||
|**Item**|**id@extension**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganizationSDS/id/@extension|
|**FHIR**|organization/identifier/value/@value|
|**Notes**|The SDS Org ID, or SDS Workgroup ID|
|||
|**Item**|**name**|
|**HL7v3**|UKCT_MT160018UK01.AgentPerson/representedOrganizationSDS/name|
|**FHIR**|organization/name/@value|
|**Notes**||

**PersonSDS** (see [above](#PersonSDS))

**Person**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPerson/@classCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "PSN"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPerson/@determinerCode|
|**FHIR**|no mapping|
|**Notes**|	Fixed to "INSTANCE"|
|||
|**Item**|**name**|
|**HL7v3**|UKCT_MT160018UK01.AgentPersonSDS/agentPerson/name|
|**FHIR**|Practitioner/name|
|**Notes**|Name of the author|

**HL7v3**
```xml
<UKCT_MT160018UK01.AgentPerson classCode="AGNT">
	<code code="NR0260" codeSystem="2.16.840.1.113883.2.1.3.2.4.17.124" displayName="General Medical Practitioner"/>
	<addr use="WP">ORG ADDRESS</addr>
	<telecom use="WP" value="0177865579"/>
	<representedPerson classCode="PSN" determinerCode="INSTANCE">
		<name>BLOGGS Fred</name>
	</representedPerson>
</UKCT_MT160018UK01.AgentPerson>
```
**FHIR**
```xml
<PractitionerRole>
	<id value="83c26c8f-ee72-4534-8891-0136972b2106"/>
	<practitioner>
		<reference value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
	</practitioner>
    <organization>
        <reference value="a82b49f8-2780-47cc-aa4b-62f79aa4ade9"/>
    </organization>
	<code>
    	<coding>
			<code value="NR0260"/>
			<dispaly value="General Medical Practitioner"/>
			<system value="https://fhir.nhs.uk/CodeSystem/HL7v3-SDSJobRoleName"/>
		</coding>
	</code>
</PractitionerRole>
<Practitioner>
	<id value="b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
	<name>
		<family value="BLOGGS"/>
		<given value="Fred"/>
	</name>
</Practitioner>
<organization>
	<id value="a82b49f8-2780-47cc-aa4b-62f79aa4ade9"/>
    <name value="LEEDS TEACHING HOSPITAL TRUST"/>
	<telecom>
		<system value="phone"/>
		<value value="0177865579"/>
	</telecom>
	<address>
		<line value="ORG ADDRESS"/>
	</address>
</organization>
```
