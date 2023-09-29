## R_AgentNPFITDevice (UKCT_RM120600UK02) Mapping

This page shows the commonly used author role CMET R_AgentNPFITDevice (UKCT_RM120600UK02).

This role is optionally used to describe a Finding author.

**AgentDevice**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|AgentDevice@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "AGNT"|
|||
|**Item**|**id@root**|
|**HL7v3**|AgentDevice.id@root|
|**FHIR**|Device\identifier\value@value|
|**Notes**||
|||
|**Item**|**code@coode**|
|**HL7v3**|AgentDevice.code@code|
|**FHIR**||
|**Notes**|Can't find a mapping|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|AgentDevice.code@codeSystem|
|**FHIR**||
|**Notes**|Can't find a mapping|
|||
|**Item**|**code@displayName**|
|**HL7v3**|AgentDevice.code@displayName|
|**FHIR**||
|**Notes**|Can't find a mapping|

**OrganizationSDS**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|OrganizationSDS@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ORG"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|OrganizationSDS.determinerCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|**id@root**|
|**HL7v3**|OrganizationSDS.id@root|
|**FHIR**|organization/identifier/system@value|
|**Notes**|HL7v3: Fixed to "1.2.826.0.1285.0.1.10" (for org) "1.2.826.0.1285.0.2.0.109" (for workgroup)
FHIR: Fixed to "https://fhir.nhs.uk/Id/ods-organization-code"|
|||
|**Item**|**id@extension**|
|**HL7v3**|OrganizationSDS.id@extension|
|**FHIR**|organization/identifier/value/@value|
|**Notes**||

**Oganization**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|Organization@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ORG"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|Organization.determinerCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|**id@root**|
|**HL7v3**|Organization.id@root|
|**FHIR**|Organization/id/@root|
|**Notes**|HL7v3: Fixed to "1.2.826.0.1285.0.1.10" <br/>
FHIR: Fixed to "https://fhir.nhs.uk/Id/ods-organization-code"|
|||
|**Item**|**id@extension**|
|**HL7v3**|Organization.id@extension|
|**FHIR**|organization/identifier/value/@value|
|**Notes**||
|||
|**Item**|**code@code**|
|**HL7v3**|Organization.code@code|
|**FHIR**|organization\type\code@value|
|**Notes**||
|||
|**Item**|**name**|
|**HL7v3**|Organization.name|
|**FHIR**|organization\name|
|**Notes**||
|||
|**Item**|**desc**|
|**HL7v3**|Organization.desc|
|**FHIR**|no mapping|
|**Notes**||
|||
|**Item**|**telecom**|
|**HL7v3**|Organization.telecom|
|**FHIR**|organization\telecom|
|**Notes**||
|||
|**Item**|**addr**|
|**HL7v3**|Organization.addr|
|**FHIR**|organization\addr|
|**Notes**||

**DeviceSDS**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|DeviceSDS@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "DEV"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|DeviceSDS@determinerCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|**id@root**|
|**HL7v3**|DeviceSDS.id@root|
|**FHIR**|Device.identifier|
|**Notes**|HL7v3: Fixed to "1.2.826.0.1285.0.2.0.107"<br/>
FHIR: (system fix to https://fhir.nhs.uk/Id/SDSDevice) |
|||
|**Item**|**id@extension**|
|**HL7v3**|DeviceSDS.id@extension|
|**FHIR**|device/identifier/value/@value|
|**Notes**||

**Device**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|Device@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "DEV"|
|||
|**Item**|**@determinerCode**|
|**HL7v3**|Device@determinerCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "INSTANCE"|
|||
|**Item**|**id@root**|
|**HL7v3**|Device.id@root|
|**FHIR**||
|**Notes**|FHIR: no system exist for devices - so leave out|
|||
|**Item**|**id@extension**|
|**HL7v3**|Device.id@extension|
|**FHIR**|device\identifier\value\@value|
|**Notes**||
|||
|**Item**|**code**|
|**HL7v3**|Device.code@code|
|**FHIR**|device\type\coding\code|
|**Notes**|FJIR: Just copy over the code & display - leave out system|
|||
|**Item**|**name**|
|**HL7v3**|Device.name|
|**FHIR**|device.deviceName.name|
|**Notes**|FHIR: set the device.deviceName.type to "other"|
|||
|**Item**|**desc**|
|**HL7v3**|Device.desc|
|**FHIR**|device\note|
|**Notes**||
|||
|**Item**|**manufacturerModelName**|
|**HL7v3**|Device.manufacturerModelName|
|**FHIR**|device.deviceName.name|
|**Notes**|FHIR: set the device.deviceName.type to "manufacturer-name"|
|||
|**Item**|**softwareName**|
|**HL7v3**|Device.softwareName|
|**FHIR**|device\version\value@value|
|**Notes**||

**HL7v3 Device in context of a finding**
```xml
<UKCT_MT144043UK02.Finding classCode="OBS" moodCode="EVN">
	<id root="D745F1E0-6DF2-11EA-AE26-C5CB3F0B33D1"/>
	<code code="397686008" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Sense of smell, function">
	<originalText>Sense of smell</originalText>
    </code>
	<statusCode code="completed"/>
	<effectiveTime>
		<low value="20200324171258"/>
	</effectiveTime>
	<author typeCode="AUT" contextControlCode="OP">
		<time value="20160630103358"/>
			<UKCT_MT120601UK02.AgentDevice classCode="AGNT">
				<id root="AAA5F1E0-6DF2-11EA-AE26-C5CB3F0B33D1"/>
				<agentDeviceSDS classCode="DEV" determinerCode="INSTANCE">
					<id root="1.2.826.0.1285.0.2.0.107" extension="7867868687687"/>
				</agentDeviceSDS>
				<representedOrganizationSDS classCode="ORG" determinerCode="INSTANCE">
					<id root="ABC123" extension="1.2.826.0.1285.0.1.10"></id>
				</representedOrganizationSDS>
			</UKCT_MT120601UK02.AgentDevice>
	</author>
</UKCT_MT144043UK02.Finding>
```

**FHIR example**
```xml
<Device>
	<identifier>
		<value value="AAA5F1E0-6DF2-11EA-AE26-C5CB3F0B33D1"/>
	</identifier>
	<identifier>
		<system value="https://fhir.nhs.uk/Id/SDSDevice"/>
		<value value="7867868687687"/>
	</identifier>
	<!-- a link to the owning SDS Organisation -->
	<owner>
		<reference value="urn:uuid:abc5dd89-fc3a-466d-baad-126c0aac46fc"/>
	</owner>
</Device>
```
