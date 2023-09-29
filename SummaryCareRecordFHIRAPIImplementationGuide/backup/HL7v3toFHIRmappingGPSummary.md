## Mapping from GP Summary (REPC_RM150007UK05) to FHIR

**Interaction Header**

```xml
<REPC_IN150016UK05 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:mif="urn:hl7-org:v3/mif" xmlns="urn:hl7-org:v3" ITSVersion="XML_1.0" xsi:schemaLocation="urn:hl7-org:v3 file:///C:/MIM4_2/MIM%204.2.00%20(Publish)/Schemas/REPC_IN150016UK05.xsd">
	<id root="D18B57ED-992E-45A2-A6AF-55200D20F48E"/>
	<creationTime value="20200501083313"/>
	<versionCode code="V3NPfIT4."/>
	<interactionId root="2.16.840.1.113883.2.1.3.2.4.12" extension="REPC_IN150016UK05"/>
	<processingCode code="P"/>
	<processingModeCode code="T"/>
	<acceptAckCode code="NE"/>
	<communicationFunctionRcv type="CommunicationFunction" typeCode="RCV">
		<device type="Device" classCode="DEV" determinerCode="INSTANCE">
			<id root="1.2.826.0.1285.0.2.0.107" extension="191566632011"/>
		</device>
	</communicationFunctionRcv>
	<communicationFunctionSnd type="CommunicationFunction" typeCode="SND">
		<device type="Device" classCode="DEV" determinerCode="INSTANCE">
			<id root="1.2.826.0.1285.0.2.0.107" extension="200000000698"/>
		</device>
	</communicationFunctionSnd>
	<ControlActEvent classCode="CACT" moodCode="EVN">
		<author1 type="Participation" typeCode="AUT">
			<AgentSystemSDS type="RoleHeir" classCode="AGNT">
				<agentSystemSDS type="Device" classCode="DEV" determinerCode="INSTANCE">
					<id root="1.2.826.0.1285.0.2.0.107" extension="200000000698"/>
				</agentSystemSDS>
			</AgentSystemSDS>
		</author1>
		<subject typeCode="SUBJ" contextConductionInd="false">
			<!--GPSummary goes in here-->
		</subject>
	</ControlActEvent>
</REPC_IN150016UK05>
```
**Note** Some of the Interaction elements map to the FHIR Bundle as follows (& can be populated at source). The othe Interaction elements will need to be added to the GPSummary before pushing to the SPINE

**REPC_IN150016UK05**

||Mapping|
|--
|**Item**|id@root|
|**HL7v3**|/REPC_IN150016UK05/id/@root|
|**FHIR**|/Bundle/identifier/value/@value|
|**Notes**||
|||
|**Item**|creationTime@value|
|**HL7v3**|/REPC_IN150016UK05/creationTime/@value|
|**FHIR**|/Bundle/timestamp/@value|
|**Notes**||

**Notes on the other Interaction Header items**
<br/>Please liaise with the SPINE team on the Interaction Header

|Element|Notes|
|--
|REPC_IN150016UK05|All attibutes should be boiler-plated|
|versionCode|Boiler-plated to "V3NPfIT4.2"|
|interactionId|Boiler-plated to <br/>root="2.16.840.1.113883.2.1.3.2.4.12" extension="REPC_IN150016UK05"<br/>|
|processingCode|Boiler-plate to "P" for production|
|processingModeCode|Bioler-plate to "T"|
|acceptAckCode|Boiler-plate to "NE"|
|communicationFunctionRcv|Element attribiues boiler-plated|
|device|Element attributes boiler-plated|
|device.id|The extension attributes should be set to the receiver's ASID|
|communicationFunctionSnd|Element attribiues boiler-plated|
|device|Element attributes boiler-plated|
|device.id|The extension attributes should be set to the sender's ASID - this could be part of the Bundle.signature JWT|
|ControlActEvent|Element attributes boiler-plated|
|author1|Element attributes boiler-plated|
|AgentSystemSDS|Element attributes boiler-plated|
|AgentSystemSDS.id|Extension should be populated with the Sender's ASID|

**GPSummary**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/@classCode|
|**FHIR**|No mapping|
|**Notes**|HL7v3: Fixed to "COMPOSITION"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/@moodCode|
|**FHIR**|No mapping|
|**Notes**|HL7v3: Fixed TO "ENV"|
|||
|**Item**|**id@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/id/@root|
|**FHIR**|/Bundle/entry[1]/resource/Composition/identifier/value/@value & /Bundle/entry[1]/resource/Composition/identifier/system/@value|
|**Notes**|A UUID for the Composition.<br/>FHIR: In the FHIR model, the system should be fixed to "https://tools.ietf.org/html/rfc4122" |
|||
|**Item**|**code@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/code/@code|
|**FHIR**|/Bundle/entry[1]/resource/Composition/type/coding/code/@value|
|**Notes**|Fixed to "196981000000101"|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/code/@codeSystem|
|**FHIR**|/Bundle/entry[1]/resource/Composition/type/coding/system/@value|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.15"<br/>FHIR: Fixed to "http://snomed.info/sct"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/code/@displayName|
|**FHIR**|/Bundle/entry[1]/resource/Composition/type/coding/display/@value|
|**Notes**|Fixed to "General Practice Summary"|
|||
|**Item**|**statusCode@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/statusCode/@code|
|**FHIR**|/Bundle/entry[1]/resource/Composition/status/@value|
|**Notes**|HL7v3: Fixed tio "active"<br/>FHIR: Fixed to "final"|
|||
|**Item**|**effectiveTime@value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/effectiveTime/@value|
|**FHIR**|/Bundle/entry[1]/resource/Composition/date/@value|
|**Notes**|Note that in HL7v3 date format is YYYYMMDDHHMMSS; in FHIR as per <http://hl7.org/fhir/R4/datatypes.html#dateTime>, so will need converting|

**author**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/author/@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "AUT"|
|||
|**Item**|**@contextControlCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/author/@contextControlCode|
|**FHIR**|no mapping|
|**Notes**|Hl7v3: Fixed to "OP"|
|||
|**Item**|**time@value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/author/time/@value|
|**FHIR**|no mapping|
|**Notes**|This is the same as the Composition.date|

**For the author CMET choice mapping see [R_AgentNPFITPersonGeneral (UKCT_RM160018UK01)]( RAgentNPFITPersonGeneralUKCTRM160018UK01Mapping)**

**recordTarget**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/recordTarget/@typeCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "RCT"|

**Patient**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/recordTarget/patient/@classCode|
|**FHIR**|no mapping|
|**Notes**|Fixed to "PAT"|
|||
|**Item**|**id@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/recordTarget/patient/id/@root|
|**FHIR**|/Bundle/entry[1]/resource/Composition/subject/reference/identifier/system/@value|
|**Notes**|HL7v3; Fixed to "2.16.840.1.113883.2.1.4.1"<br/>FHIR: Fixed to "https://fhir.nhs.uk/Id/nhs-number"|
|||
|**Item**|**id@extension**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/recordTarget/patient/id/@extension|
|**FHIR**|/Bundle/entry[1]/resource/Composition/subject/reference/identifier/value/@value|
|**Notes**|The NHS Number

**replacementOf**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/replacementOf/@typeCode|
|**FHIR**|/Bundle/entry[1]/resource/Composition/relatesTo/code/@value|
|**Notes**|HL7v3: Fixed to "RPLC"<br/>FHIR: Fixed to "replaces"|

**priorMessageRef**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/replacementOf/priorMessageRef/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "COMPOSITION"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/replacementOf/priorMessageRef/@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ENV"|
|||
|**Item**|**id@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/replacementOf/priorMessageRef/id/@root|
|**FHIR**|/Bundle/entry[1]/resource/Composition/relatesTo/targetIdentifier/value/@value|
|**Notes**|Reference to the GPSummary to be replaced|

**pertinentInformation1**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "PERT"|
|||
|**Item**|**@inversionInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/@inversionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: FIXED to "false"|
|||
|**Item**|**@contextConductionInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/@contextConductionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to ""true"|
|||
|**Item**|**@negationInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/@negationInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**templateId@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/templateId/@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"|
|||
|**Item**|**templateId@extension**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/templateId/@extension|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CSAB_RM-NPfITUK10.pertinentInformation1"|
|||
|**Item**|**seperatableInd@value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/seperatableInd/@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "true"|

**pertinentRootCREType**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/pertinentRootCREType/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CATEGORY"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/pertinentRootCREType/@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ENV"|
|||
|**Item**|**code@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/pertinentRootCREType/code/@code|
|**FHIR**|/Bundle/entry[1]/resource/Composition/category/coding/code/@value|
|**Notes**|Fixed to "163171000000105"|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/pertinentRootCREType/code/@codeSystem|
|**FHIR**|/Bundle/entry[1]/resource/Composition/category/coding/system/@value|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.15"<br/>FHIR: Fixed to "http://snomed.info/sct"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/pertinentInformation1/pertinentRootCREType/code/@displayName|
|**FHIR**|/Bundle/entry[1]/resource/Composition/category/coding/display/@value|
|**Notes**|Fixed to "Care Professional Documentation"|

**excerptFrom**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: FIXED to "XCRPT"|
|||
|**Item**|**@inversionInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/@inversionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**@contextConductionInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/@contextConductionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "true"|
|||
|**Item**|**@negationInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/@negationInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|***seperatableInd@value*|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/seperatableInd/@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**templateId@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/templateId/@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"|
|||
|**Item**|**templateId@extension**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/templateId/@extension|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CSAB_RM-NPfITUK10.excerptFrom"|

**UKCT_MT144051UK01.CareProfessionalDocumentationCRE**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CATEGORY"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "ENV"|
|||
|**Item**|**code@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/code/@code|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "163171000000105"|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/code/@codeSystem|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.15"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/code/@displayName|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "Care Professional Documentation"|

**component**

||Mapping|
|--
|**Item**|**@typeCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/@typeCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "COMP"|
|||
|**Item**|**@inversionInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/@inversionInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**@negationInd**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/@negationInd|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**seperatableInd@value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/seperatableInd/@value|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "false"|
|||
|**Item**|**templateId@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/templateId/@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.18.2"|
|||
|**Item**|**templateId@extension**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/templateId/@extension|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "CSAB_RM-NPfITUK10.component"|

**PresentationText**

||Mapping|
|--
|**Item**|**@classCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/@classCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "OBS"|
|||
|**Item**|**@moodCode**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/@moodCode|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "EVN"|
|||
|**Item**|**id@root**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/id/@root|
|**FHIR**|no mapping|
|**Notes**|HL7v3: a UUID|
|||
|**Item**|**code@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/code/@code|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "PresentationText"|
|||
|**Item**|**code@codeSystem**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/code/@codeSystem|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "2.16.840.1.113883.2.1.3.2.4.17.126"|
|||
|**Item**|**code@displayName**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/code/@displayName|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "Presentation Text"|
|||
|**Item**|**statusCode@code**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/statusCode/@code|
|**FHIR**|no mapping|
|**Notes**|HL7v3: Fixed to "completed"|
|||
|**Item**|**effectiveTime@value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/effectiveTime/@value|
|**FHIR**|Composition.date|
|**Notes**||
|||
|**Item**|**value**|
|**HL7v3**|/REPC_IN150016UK05/ControlActEvent/subject/GPSummary/excerptFrom/UKCT_MT144051UK01.CareProfessionalDocumentationCRE/component/presentationText/value|
|**FHIR**|see below|
|**Notes**|The document XHTML|

**Notes on documemt text**
* In HL7v3 the sections are in a &lt;html&gt;&lt;body&gt;. In FHIR the sections use Composition.section
* In HL7v3 the section headings are in a &lt;h2&gt; tag. In FHIR the heading are in &lt;title&gt; tags
* In HL7v3 the &lt;h2&gt; headings have an @id attribute. In FHIR, use the Composition.section.code.coding@code (there is no display or system)
* other HTML formats are the same in both HL7v3 & FHIR

**Typical HL7v3 text section**

```xml
<h2 id="AllergiesHeader">Allergies and Adverse Reactions</h2>
	<table summary="This table includes information about this patient's allergies and adverse reactions." id="Allergies">
		<thead>
			<tr>
			<th>Date</th>
			<th>Description</th>
			<th>Certainty</th>
			<th>Severity</th>
			<th>Supporting Information</th>
			</tr>
		</thead>
		<tbody>
			<tr class="oddRow">
			<td>02-May-2019</td>
			<td>Adverse reaction to atenolol</td>
			<td/>
			<td/>
			<td>Problem; First</td>
			</tr>
		</tbody>
	</table>
```
**Typical FHIR text section**
```xml
<section>
	<title value="Allergies and Adverse Reactions"/>
	<code>
		<coding>
			<code value="AllergiesHeader"/>
		</coding>
	</code>		
	<text>
		<status value="generated"/>
		<div xmlns="http://www.w3.org/1999/xhtml">
			<table>
				<thead>
					<tr>
						<th>Date</th>
						<th>Description</th>
						<th>Supporting information</th>
					</tr>
				</thead>
				<tbody>
					<tr>
						<td>13-Jan-07</td>
						<td>Refused consent for upload to national shared electronic record</td>
					</tr>
					<tr>
						<td>14-Nov-06</td>
						<td>Allergy to Drug - Penicillin, (probably present) . </td>
						<td>Patient stated that they told that they were were allergic to penicillin by their parents </td>
					</tr>
				</tbody>
			</table>
		</div>
	</text>
</section>
```


### Coded Information (in support of COVID-19)

**If the GPSummary includes coded entries (i.e. to cover the COVID coded values), then for the population of pertinentInformation2; pertinentCREType; component and the Finding or Diagnosis CMET see [CodedEntriesforCOVID-19Mappings](CodedEntriesforCOVID-19Mappings)**
