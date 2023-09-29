### Example HL7v3 with FHIR Mapping

This example shows a HL7v3 GPSummary document with FHIR mappings in comments. It also shows where the HL7v3 GPSummary uses fixed values that can be "boiler-plated".

There is a slight complication around authorship, as options are allowed in the HL7v3 message.

```xml
GPSummary classCode="COMPOSITION" moodCode="EVN">
	<!--You need to generate an UPPER case UUID (this is the document reference)-->
	<!--same as /Bundle/entry/resource/Composition/identifier/value/@value-->
	<id root="988B2951-FCEA-4CE4-B2A9-B54797BF4049"/>
	<!--this can be fixed as shown-->
	<!--same as element in  /Bundle/entry/resource/Composition/type/coding-->
	<code code="196981000000101" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="General Practice Summary"/>
	<!--same as /Bundle/entry/resource/Composition/date/@value-->
	<effectiveTime value="20200501093311"/>
	<!--fix as shown-->
	<!--equivalent to /Bundle/entry/resource/Composition/status/@value-->
	<statusCode code="active"/>
	<!--fix as shown-->
	<author typeCode="AUT" contextControlCode="OP">
		<!--use the document date-->
		<!--same as /Bundle/entry/resource/Composition/date/@value-->
		<time value="20200501093311"/>
		<!--at this point there's a choice of AgentPerson (shown here) & AgentPersonSDS-->
		<!--fixed as shown-->
		<UKCT_MT160018UK01.AgentPerson classCode="AGNT">
			<!--fix codeSystem as shown-->
			<!--the JobRole-->
			<!--same as /Bundle/composition/author/reference@value [reference to] -->
			<!--/Bundle/entry/resource/PractitionerRole/code/coding-->
			<code code="NR0260" codeSystem="2.16.840.1.113883.2.1.3.2.4.17.124" displayName="General Medical Practitioner"/>
			<!--same as /Bundle/composition/author/reference@value [reference to]-->
			<!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]-->
			<!--/Bundle/entry/resource/organization/address-->
			<addr use="WP">Fulford Grange, Rawdon, Leeds, West Yorkshire, LS19 7BY.</addr>
			<!--same as /Bundle/composition/author/reference@value [reference to]-->
			<!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]-->
			<!--/Bundle/entry/resource/organization/telecom-->			
			<telecom use="WP" value="0177865579"></telecom>
			<!--fixed as shown-->
			<agentPerson classCode="PSN" determinerCode="INSTANCE">
				<!--same as /Bundle/composition/author/reference@value [reference to]-->
				<!--/Bundle/entry/resource/PractitionerRole/practitioner/reference/@value [reference to]-->
				<!--/Bundle/entry[4]/resource/Practitioner/name-->	
				<name>EMISWebCR1 50004</name>
			</agentPerson>
			<!--At this point there's a choice of (4) organisation representations / person representations-->
			<!--All 4 are shown here - 3 are commented-->
			<!--for representedOrganization-->
			<!--fixed attributes as shown-->
<!--			<representedOrganization classCode="ORG" determinerCode="INSTANCE">
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]--><!--
				--><!--/Bundle/entry/resource/organization/address--><!--	
				<addr>SOME ADDRESS</addr>
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]--><!--
				--><!--/Bundle/entry/resource/organization/type--><!--	
				<code code="001"/>
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]--><!--
				--><!--/Bundle/entry/resource/organization/name--><!--					
				<name>ORG NAME</name>
				--><!--there is no mapping for desc--><!--
				<desc></desc>
			</representedOrganization>-->
			<!--for representedOrganizationSDS-->
			<!--fix attributes as shown-->
<!--			<representedOrganizationSDS classCode="ORG" determinerCode="INSTANCE">
				--><!--for a SDS Organization fix root as shown--><!--
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]--><!--
				--><!--/Bundle/entry/resource/organization/identifier--><!--	
				<id root="1.2.826.0.1285.0.1.10" extension="R786786"></id>
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/organization/reference/@value [reference to]--><!--
				--><!--/Bundle/entry/resource/organization/name--><!--				
				<name>ORG NAME</name>
			</representedOrganizationSDS>-->
			<!--for representedPersonSDS-->
			<!--fix attributes as shown-->
<!--			<representedPersonSDS classCode="PSN" determinerCode="INSTANCE">
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/identifier--><!--
				<id root="1.2.826.0.1285.0.2.0.65" extension="47766"></id>
				--><!--same as /Bundle/composition/author/reference@value [reference to]--><!--
				--><!--/Bundle/entry/resource/PractitionerRole/practitioner/reference/@value [reference to]--><!--		
				--><!--/Bundle/entry/resource/Practitioner/name--><!--
				<name>A NAME</name>
			</representedPersonSDS>-->
			<!--for representedPerson-->
			<!--fix attributes as shown-->
			<representedPerson classCode="PSN" determinerCode="INSTANCE">
				<!--same as /Bundle/composition/author/reference@value [reference to]-->
				<!--/Bundle/entry/resource/PractitionerRole/practitioner/reference/@value [reference to]-->
				<!--/Bundle/entry/resource/Practitioner/name-->
				<name>A NAME</name>
			</representedPerson>
		</UKCT_MT160018UK01.AgentPerson>
	</author>
	<!--fix attributes as shown-->
	<excerptFrom typeCode="XCRPT" inversionInd="false" contextConductionInd="true" negationInd="false">
		<!--fix as shown-->
		<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAT_RM-NPfITUK10.excerptFrom"/>
		<!--fix as shown-->
		<seperatableInd value="false"/>
		<!--fix as shown-->
		<UKCT_MT144051UK01.CareProfessionalDocumentationCRE classCode="CATEGORY" moodCode="EVN">
			<!--fix as shown-->
			<code code="163171000000105" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Care Professional Documentation"/>
			<!--fix as shown-->
			<component typeCode="COMP" inversionInd="false" negationInd="false">
				<!--fix as shown-->
				<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
				<!--fix as shown-->
				<seperatableInd value="false"/>
				<!--fix as shown-->
				<presentationText classCode="OBS" moodCode="EVN">
					<value>
						<!--This is the text-->
						<!--in FHIR this is presented in multiple Composition.section-->
						<!--every <h2> is a Composition.section-->
						<!--Information below <h2> comes in Composition.section.text-->
						<html xmlns="xhtml:NPfIT:PresentationText">
							<body>
								<h2 id="Title">General Practice Summary</h2>
								<h3 id="Disclaimer">Sourced from the patient's General Practice record. This summary
                                                may not include all the information pertinent to this patient.</h3>
								<p id="CreateTime">Summary Created: 01-May-2020 09:33</p>
								<p id="Practice">EMISWebCR1 50004, Fulford Grange, Rawdon, Leeds, West Yorkshire,
                                                LS19 7BY.</p>
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
								<h2 id="AcuteMedsHeader">Acute Medications (For the 12 month period 01-May-2019 to
                                                01-May-2020)</h2>
								<table summary="This table includes information about this patient's acute medications." id="AcuteMeds">
									<thead>
										<tr>
											<th>Type</th>
											<th>Date</th>
											<th>Medication Item</th>
											<th>Dosage Instructions</th>
											<th>Quantity</th>
										</tr>
									</thead>
									<tbody>
										<tr class="oddRow">
											<td>Acute Medication</td>
											<td>Prescribed: 16-May-2019</td>
											<td>Paracetamol 500mg tablets</td>
											<td>One To Be Taken Every 4-6 Hours Up To Four Times A Day</td>
											<td>28 tablet</td>
										</tr>
										<tr class="oddRow">
											<td/>
											<td colspan="4">***Date Cancelled: 16-May-2019***</td>
										</tr>
										<tr class="evenRow">
											<td>Acute Medication</td>
											<td>Prescribed: 09-May-2019</td>
											<td>Aspirin 75mg dispersible tablets</td>
											<td>One To Be Taken Each Day</td>
											<td>1 tablet</td>
										</tr>
									</tbody>
								</table>
							</body>
						</html>
					</value>
					<!--no mapping to FHIR - generate a UPPERCASE UUID-->
					<id root="8FD642AD-E640-4E40-AD6F-0888045377A9"/>
					<!--fix as shown-->
					<code code="PresentationText" codeSystem="2.16.840.1.113883.2.1.3.2.4.17.126" displayName="Presentation Text"/>
					<!--fix as shown-->
					<statusCode code="completed"/>
					<!--use /Bundle/entry/resource/Composition/date/@value-->
					<effectiveTime value="20200501093312"/>
				</presentationText>
			</component>
		</UKCT_MT144051UK01.CareProfessionalDocumentationCRE>
	</excerptFrom>
	<!--This can be all boilerplated-->
	<!--fix as shown-->
	<pertinentInformation1 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
		<!--fix as shown-->
		<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
		<!--fix as shown-->
		<seperatableInd value="true"/>
		<!--fix as shown-->
		<pertinentRootCREType classCode="CATEGORY" moodCode="EVN">
			<!--fix as shown-->
			<code code="163171000000105" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Care Professional Documentation"/>
		</pertinentRootCREType>
	</pertinentInformation1>
	<!--ONLY DO THIS BIT IF THERE ARE CODED ENTRIES-->
	<!--fix as shown-->
	<pertinentInformation2 typeCode="PERT" inversionInd="false" contextConductionInd="true" negationInd="false">
		<!--fix as shown-->
		<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.pertinentInformation1"/>
		<!--fix as shown-->
		<seperatableInd value="true"/>
		<!--fix as shown-->
		<pertinentCREType classCode="CATEGORY" moodCode="EVN">
			<!--This is an example of a coded entry - these are documented elsewhere-->
			<!--In FHIR coded entries are referenced from Composition.section.entry & live within the Bundle-->
			<code code="185361000000102" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Medication"/>
			<component typeCode="COMP" contextConductionInd="true">
				<templateId root="2.16.840.1.113883.2.1.3.2.4.18.2" extension="CSAB_RM-NPfITUK10.component"/>
				<seperatableInd value="false"/>
				<UKCT_MT144040UK01.AcuteMedication classCode="SBADM" moodCode="RQO">
					<id root="2ED85475-6314-460B-A069-B3D03FDD388F"/>
					<code code="222671000000103" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Acute medication"/>
					<statusCode code="completed"/>
					<effectiveTime value="20190516"/>
					<pertinentInformation1 typeCode="PERT" contextConductionInd="true">
						<seperatableInd value="false"/>
						<pertinentDosageInstructions classCode="OBS" moodCode="EVN">
							<value>One To Be Taken Every 4-6 Hours Up To Four Times A Day</value>
							<code code="DI" codeSystem="2.16.840.1.113883.2.1.3.2.4.17.30" displayName="Dose Instructions"/>
						</pertinentDosageInstructions>
					</pertinentInformation1>
					<component typeCode="COMP">
						<seperatableInd value="false"/>
						<medicationQuantity classCode="SPLY" moodCode="RQO">
							<quantity unit="1">
								<translation value="28.000">
									<originalText>tablet</originalText>
								</translation>
							</quantity>
							<code code="246205007" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Quantity"/>
						</medicationQuantity>
					</component>
					<consumable typeCode="CSM" contextControlCode="OP">
						<manufacturedProduct classCode="MANU">
							<manufacturedManufacturedMaterial classCode="MMAT" determinerCode="KIND">
								<code code="322236009" codeSystem="2.16.840.1.113883.2.1.3.2.4.15" displayName="Paracetamol 500mg tablets"/>
							</manufacturedManufacturedMaterial>
						</manufacturedProduct>
					</consumable>
				</UKCT_MT144040UK01.AcuteMedication>
			</component>
		</pertinentCREType>
	</pertinentInformation2>
	<!--the Patient-->
	<!--fixed as shown-->
	<recordTarget typeCode="RCT">
		<!--fixed as shown-->
		<patient classCode="PAT">
			<!--the NHS Number-->
			<!--same as /Bundle/entry/resource/Composition/subject/reference/@value [reference to]-->
			<!--/Bundle/entry/resource/Patient/identifier-->
			<!--NOTE that in FHIR you need to put in the verificationStatus of the NHS Number-->
			<id root="2.16.840.1.113883.2.1.4.1" extension="5558796812"/>
		</patient>
	</recordTarget>
	<!--the document being replaced-->
	<!--fixed as shown-->
	<replacementOf typeCode="RPLC">
		<!--fixed as shown-->
		<priorMessageRef classCode="COMPOSITION" moodCode="EVN">
			<!--the id (/GPSummary/id/@root) (/Bundle/entry[1]/resource/Composition/identifier/value/@value)-->
			<!--of the document being replaced-->
			<id root="C30444A6-DFF3-4E8E-94F0-B00592EC7280"/>
		</priorMessageRef>
	</replacementOf>
</GPSummary>
```