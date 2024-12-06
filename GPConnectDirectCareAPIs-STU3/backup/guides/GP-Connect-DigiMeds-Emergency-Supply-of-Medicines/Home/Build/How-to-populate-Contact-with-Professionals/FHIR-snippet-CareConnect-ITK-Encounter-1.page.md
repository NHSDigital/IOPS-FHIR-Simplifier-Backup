## {{page-title}}

```xml
<entry>
	<fullUrl value="urn:uuid:adb353f9-0953-4fb4-a4ab-f0ab04a44dbc"/>
	<resource>
		<Encounter>
			<id value="adb353f9-0953-4fb4-a4ab-f0ab04a44dbc"/>
			<meta>
				<profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-Encounter-1"/>
			</meta>
			<status value="finished"/>
			<subject>
				<reference value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0"/>
				<display value="SMITH, William (Mr)"/>
			</subject>
			<participant>
				<type>
					<coding>
						<system value="http://hl7.org/fhir/v3/ParticipationType"/>
						<code value="PPRF"/>
						<display value="primary performer"/>
					</coding>
				</type>
				<individual>
					<reference value="urn:uuid:0e4c13d4-e61f-48f2-89ee-7cf8f5f3dbb3"/>
					<display value="SMITH, Eric (Mr)"/>
				</individual>
			</participant>
			<period>
				<start value="2018-05-09T10:00:00+00:00"/>
			</period>
			<serviceProvider>
				<reference value="urn:uuid:1226082b-315e-40be-83cf-5d21a964219e"/>
				<display value="Overtown Pharmacy"/>
			</serviceProvider>
		</Encounter>
	</resource>
</entry>
```