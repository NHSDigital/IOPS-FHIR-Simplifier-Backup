## {{page-title}}

### Patient registration successful

A patient goes online to register with a GP practice. A GP administrator accepts the patient's request to register.

**As a:** GP Administrator<br />
**I want to:** Accept registration messages from patients not currently registered at the GP Surgery<br />
**So that:** I can register them without additional input from sources outside my GP IT system  
<br /><br />
**Given that:** A registering individual is not currently registered at the GP Surgery<br />
**When:** The registering individual submits the registration application<br />
**Then:** The message is accepted by the GP IT System  

<plantuml>
autonumber "Message 0 -"
participant "GP Central Registration System" as gpcentral
participant "GP Local IT System" as gplocal
gpcentral -> gplocal: Request patient registration
gplocal --> gpcentral: Request successfully received
gplocal --> gpcentral: Patient successfully registered
</plantuml>




<br /><br />

#### Message 1 - Request patient registration
```xml
<Bundle xmlns="http://hl7.org/fhir">
	<id value="urn:uuid:6f4256fa-cd14-4f96-899e-008643d84ff8" />
	<type value="message" />
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader" />
		<resource>
			<MessageHeader>
				<meta>
					<versionId value="1" />
				</meta>
				<id value="urn:uuid:772c0a20-f72f-45f0-abf0-c1c667c52bc8" />
				<extension url="http://hl7.org/fhir/StructureDefinition/messageheader-response-request">
					<valueCode value="always" />
				</extension>
				<eventCoding>
					<system value="https://fhir.nhs.uk/CodeSystem/message-event" />
					<code value="patient" />
					<display value="Patient Demographics" />
				</eventCoding>
				<destination>
					<name value="Leeds GP Family Practice EMIS System" />
					<endpoint value="https://emis.leedsgpfamilypractice.com/api/patient/register" />
					<receiver>
						<reference value="urn:uuid:fb1d6acf-3ab0-4433-a425-c0b6f054779c" />
						<display value="Leeds GP Family Practice" />
					</receiver>
				</destination>
				<source>
					<name value="NHSD GP Registration System" />
					<version value="0.0.1" />
					<contact>
						<system value="email" />
						<value value="helpdeskemail@nhs.net" />
					</contact>
					<endpoint value="https://gpregistration.digital.nhs.net/api" />
				</source>
			</MessageHeader>
		</resource>
	</entry>
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Patient" />
		<resource>
			<Patient>
				<meta>
					<versionId value="3" />
				</meta>
				<extension url="http://hl7.org/fhir/StructureDefinition/patient-birthPlace">
					<valueAddress>
						<country value="FRA" />
					</valueAddress>
				</extension>
				<extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-BirthSex">
					<valueCode value="F" />
				</extension>
				<extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-EthnicCategory">
					<valueCodeableConcept>
						<coding>
							<system value="https://fhir.hl7.org.uk/CodeSystem/UKCore-EthnicCategoryEngland" />
							<code value="N" />
							<display value="Black or Black British - African" />
						</coding>
					</valueCodeableConcept>
				</extension>
				<extension url="http://hl7.org/fhir/StructureDefinition/patient-interpreterRequired">
					<valueBoolean value="true" />
				</extension>
				<identifier>
					<system value="https://fhir.nhs.uk/Id/nhs-number" />
					<value value="9999999999" />
				</identifier>
				<name>
					<use value="usual" />
					<family value="Bryson" />
					<given value="Bill" />
					<given value="Bob" />
				</name>
				<name>
					<use value="old" />
					<family value="Smith" />
					<given value="Bill" />
					<given value="Bob" />
				</name>
				<telecom>
					<system value="email" />
					<value value="bill@bryson.com" />
					<rank value="1" />
				</telecom>
				<telecom>
					<system value="phone" />
					<value value="0161123456" />
					<rank value="2" />
				</telecom>
				<telecom>
					<system value="phone" />
					<value value="07819194455" />
					<rank value="3" />
				</telecom>
				<gender value="male" />
				<birthDate value="1990-01-01" />
				<address>
					<use value="home" />
					<type value="physical" />
					<line value="Flat 1" />
					<line value="28 Ashbrook Close" />
					<city value="Ossett" />
					<postalCode value="WF5 9DU" />
				</address>
				<contact>
					<relationship>
						<coding>
							<system value="http://terminology.hl7.org/CodeSystem/v2-0131" />
							<code value="EP" />
							<display value="Emergency contact person" />
						</coding>
					</relationship>
					<name>
						<use value="usual" />
						<family value="Doe" />
						<given value="John" />
					</name>
					<telecom>
						<system value="phone" />
						<value value="07123476234" />
						<rank value="1" />
					</telecom>
				</contact>
				<communication>
					<language>
						<coding>
							<system value="https://fhir.hl7.org.uk/CodeSystem/UKCore-HumanLanguage" />
							<code value="q4" />
							<display value="British Sign Language" />
						</coding>
					</language>
				</communication>
				<generalPractitioner>
					<reference value="urn:uuid:f21e741d-2f77-44e0-bfdd-cb4278fe93a6" />
					<display value="GP surgery" />
				</generalPractitioner>
			</Patient>
		</resource>
	</entry>
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization" />
		<resource>
			<Organization>
				<meta>
					<versionId value="4" />
				</meta>
				<id value="urn:uuid:f21e741d-2f77-44e0-bfdd-cb4278fe93a6" />
				<identifier>
					<system value="https://fhir.nhs.uk/Id/ods-organization-code" />
					<value value="AB123" />
				</identifier>
				<name value="GP surgery" />
				<address>
					<line>Flat 1</line>
					<line>28 Ashbrook Close</line>
					<city>Ossett</city>
					<postalCode>WF5 9DU</postalCode>
				</address>
			</Organization>
		</resource>
	</entry>
		<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Organization" />
		<resource>
			<Organization>
				<meta>
					<versionId value="5" />
				</meta>
				<id value="urn:uuid:fb1d6acf-3ab0-4433-a425-c0b6f054779c" />
				<identifier>
					<system value="https://fhir.nhs.uk/Id/ods-organization-code" />
					<value value="AB555" />
				</identifier>
				<name value="Leeds GP family practice" />
				<address>
					<line>Floor 5</line>
					<line>10 Bond Street</line>
					<city>Ossett</city>
					<postalCode>WF2 5BA</postalCode>
				</address>
			</Organization>
		</resource>
	</entry>
</Bundle>
```
<br />

#### Message 2 - Request successfully received
```xml
<Bundle xmlns="http://hl7.org/fhir">
	<id value="urn:uuid:2adbf7c4-8f21-4159-8681-3f41bc06215c" />
	<type value="message" />
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader" />
		<resource>
			<MessageHeader>
				<meta>
					<versionId value="1" />
				</meta>
				<id value="urn:uuid:7c451367-d637-4fe7-9eab-140e743b88b3" />
				<extension url="http://hl7.org/fhir/StructureDefinition/messageheader-response-request">
					<valueCode value="never" />
				</extension>
				<eventCoding>
					<system value="https://fhir.nhs.uk/CodeSystem/message-event" />
					<code value="patient" />
					<display value="Patient Demographics" />
				</eventCoding>
				<destination>
					<name value="NHS England GP Registration System" />
					<endpoint value="https://gpregistration.digital.nhs.net/api" />
					<receiver>
						<reference value="urn:uuid:0971b53c-7b9e-4d6e-afd2-e9408c5c3a6c" />
						<display value="NHS England GP Registration System" />
					</receiver>
				</destination>
				<source>
					<name value="Leeds GP Family Practice EMIS System" />
					<version value="0.0.5" />
					<contact>
						<system value="email" />
						<value value="helpdeskemail@emis.net" />
					</contact>
					<endpoint value="https://emis.leedsgpfamilypractice.com/api/patient/register" />
				</source>
				<response>
					<identifier value="6f4256fa-cd14-4f96-899e-008643d84ff8" />
					<code value="ok" />
					<details>
						<reference value="urn:uuid:6b7617b1-a988-41bc-967a-0a8ba0fa36f1" />
					</details>
				</response>
			</MessageHeader>
		</resource>
	</entry>
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome" />
		<resource>
			<OperationOutcome>
				<meta>
					<versionId value="3" />
				</meta>
				<id value="urn:uuid:8283e341-67ae-48e7-b3ae-2c6a0a824b2c" />
				<issue>
					<severity value="information" />
					<code value="informational" />
					<details>
						<coding>
							<system value="https://fhir.nhs.uk/CodeSystem/AcknowledgementFrameworkResponseCode" />
							<code value="TECHNICAL_SUCCESS" />
							<display value="Request successfully received" />
						</coding>
					</details>
				</issue>
			</OperationOutcome>
		</resource>
	</entry>
</Bundle>
```

<br />

#### Message 3 - Patient successfully registered
```xml
<Bundle xmlns="http://hl7.org/fhir">
	<id value="urn:uuid:c96c137d-3089-4165-8a2b-f9518d745a64" />
	<type value="message" />
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-MessageHeader" />
		<resource>
			<MessageHeader>
				<meta>
					<versionId value="1" />
				</meta>
				<id value="urn:uuid:7c451367-d637-4fe7-9eab-140e743b88b3" />
				<extension url="http://hl7.org/fhir/StructureDefinition/messageheader-response-request">
					<valueCode value="never" />
				</extension>
				<eventCoding>
					<system value="https://fhir.nhs.uk/CodeSystem/message-event" />
					<code value="patient" />
					<display value="Patient Demographics" />
				</eventCoding>
				<destination>
					<name value="NHS England GP Registration System" />
					<endpoint value="https://gpregistration.digital.nhs.net/api" />
					<receiver>
						<reference value="urn:uuid:0971b53c-7b9e-4d6e-afd2-e9408c5c3a6c" />
						<display value="NHS England GP Registration System" />
					</receiver>
				</destination>
				<source>
					<name value="Leeds GP Family Practice EMIS System" />
					<version value="0.0.5" />
					<contact>
						<system value="email" />
						<value value="helpdeskemail@emis.net" />
					</contact>
					<endpoint value="https://emis.leedsgpfamilypractice.com/api/patient/register" />
				</source>
				<response>
					<identifier value="6f4256fa-cd14-4f96-899e-008643d84ff8" />
					<code value="ok" />
					<details>
						<reference value="urn:uuid:6b7617b1-a988-41bc-967a-0a8ba0fa36f1" />
					</details>
				</response>
			</MessageHeader>
		</resource>
	</entry>
	<entry>
		<fullUrl value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-OperationOutcome" />
		<resource>
			<OperationOutcome>
				<meta>
					<versionId value="3" />
				</meta>
				<id value="urn:uuid:8283e341-67ae-48e7-b3ae-2c6a0a824b2c" />
				<issue>
					<severity value="information" />
					<code value="informational" />
					<details>
						<coding>
							<system value="https://fhir.nhs.uk/CodeSystem/AcknowledgementFrameworkResponseCode" />
							<code value="BUSINESS_SUCCESS" />
							<display value="Business request successfully actioned" />
						</coding>
					</details>
				</issue>
			</OperationOutcome>
		</resource>
	</entry>
</Bundle>
```