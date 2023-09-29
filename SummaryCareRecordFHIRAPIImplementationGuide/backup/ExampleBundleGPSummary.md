#### Example Bundle GP Summary

This page shows examples supported by the specification.

**Note** that the example shows 3 complete sections, and misses the narrative for the rest. The SPINE team should be contacted for the complete list of section codes.

```xml
<Bundle xmlns="http://hl7.org/fhir">
	<id value="f61e545c-d52c-4b62-9668-3dcc6c27fc50"/>
	<identifier>
		<system value="https://tools.ietf.org/html/rfc4122"/>
		<value value="1ff370b6-fc5b-40a1-9721-2a942e301666"/>
	</identifier>
	<type value="document"/>
	<timestamp value="2007-03-15T01:00:00Z"/>
	<entry>
		<fullUrl value="urn:uuid:2880eedf-76f0-4f38-9681-dc158e937da7"/>
		<resource>
			<Composition>
				<id value="2880eedf-76f0-4f38-9681-dc158e937da7"/>
				<identifier>
					<system value="https://tools.ietf.org/html/rfc4122"/>
					<value value="2b5d459b-df79-4a2b-9b0c-95b2a7ee2ca4"/>
				</identifier>
				<status value="final"/>
				<type>
					<coding>
						<system value="http://snomed.info/sct"/>
						<code value="196981000000101"/>
						<display value="General Practice Summary"/>
					</coding>
				</type>
				<category>
					<coding>
						<system value="http://snomed.info/sct"/>
						<code value="163171000000105"/>
						<display value="Care Professional Documentation"/>
					</coding>
				</category>
				<subject>
					<reference value="urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc"/>
				</subject>
				<date value="2007-03-15T01:00:00Z"/>
				<author>
					<reference value="urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106"/>
					<display value="Dr Steve Jones"/>
				</author>
				<title value="General Practice Summary"/>
				<relatesTo>
					<code value="replaces"/>
					<targetIdentifier>
						<value value="D18B57ED-992E-45A2-A6AF-55200D20F48E"/>
					</targetIdentifier>
				</relatesTo>
				<section>
					<title value="General Practice Summary"/>
					<code>
						<coding>
								<code value="Title"/>
						</coding>
					</code>
					<text>
						<status value="generated"/>
						<div xmlns="http://www.w3.org/1999/xhtml">
							<h3>Sourced from the patient's General Practice record. This information has not been verified by the practice prior to sending. This summary 
								may not include all the information pertinent to this patient NB the patient may have opted to leave out items from this summary</h3>
							<h3>Time of summary creation 16.00 15-Mar-2007</h3>
							<h3>Author Dr Steve Jones, The Bridge Street Practice, Bridge Street, Bridge Town, Bridgeshire, 
								BT1 1BT, England, +4401234567890</h3>
							<h3>Date of sending this summary 15-Mar-2007</h3>
						</div>
                    </text>
				</section>
				<section>
					<title value="Allergies and Adverse Reactions"/>
					<code>
						<coding>
								<code value="AllergiesHeader"/>
						</coding>
					</code>					
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Repeat Medication"/>
					<code>
						<coding>
								<code value="RepeatMedsHeader"/>
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
				<section>
					<title value="Acute Medication"/>
					<code>
						<coding>
								<code value="AcuteMedsHeader"/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
						<div xmlns="http://www.w3.org/1999/xhtml">
							<table>
								<thead>
									<tr>
										<th>Date prescribed</th>
										<th>Medication Item</th>
										<th>Dosage instructions</th>
										<th>Quantity or duration</th>
										<th>Reason for medication</th>
										<th>Supporting information</th>
									</tr>
								</thead>
								<tbody>
									<tr>
										<td>13-Jan-07</td>
										<td>Refused consent for upload to national shared electronic record</td>
										<td/>
										<td/>
										<td/>
										<td/>
									</tr>
									<tr>
										<td>12-Nov-06</td>
										<td>Amoxycillin 500mg tablets</td>
										<td>one four times daily</td>
										<td>7 days</td>
										<td/>
										<td>Chest infection - green sputum for 3 days</td>
									</tr>
									<tr>
										<td>16-Nov-06</td>
										<td>erythromycin 500mg tablets</td>
										<td>one four times daily</td>
										<td>7 days</td>
										<td>Allergy to Penicillin</td>
										<td/>
									</tr>
									<tr>
										<td>01-Dec-06</td>
										<td>Paracetamol 500mg tablets</td>
										<td>one or two tablet four times daily as required</td>
										<td>100 tablets</td>
										<td>Right Knee pain</td>
										<td/>
									</tr>
									<tr>
										<td>01-Dec-06</td>
										<td>Codeine 30mg tablets</td>
										<td>one or two tablet four times daily as required</td>
										<td>100 tablets</td>
										<td>Right Knee pain</td>
										<td/>
									</tr>
								</tbody>
							</table>
						</div>
                    </text>
				</section>
				<section>
					<title value="Discontinued Repeat Medication"/>
					<code>
						<coding>
								<code value="DiscRepeatMedsHeader"/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Risks to Care professional or Third Party"/>
					<code>
						<coding>
								<code value="see SPINE team "/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Diagnoses"/>
					<code>
						<coding>
								<code value="DiagnosesHeader"/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Problems and issues"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Clinical Observation and Findings"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Treatments"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Investigations"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Provision of Advice and Information to Patients and Carers"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Personal Preferences"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Social and Personal Circumstances"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Services, Care Professionals and Carers"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Lifestyle"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
				<section>
					<title value="Family History"/>
					<code>
						<coding>
								<code value=""/>
						</coding>
					</code>							
					<text>
						<status value="generated"/>
                        --- We have skipped the narrative for better readability of the resource ---
                    </text>
				</section>
			</Composition>
		</resource>
	</entry>
	<entry>
		<fullUrl value="urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106"/>
		<resource>
			<PractitionerRole>
				<id value="83c26c8f-ee72-4534-8891-0136972b2106"/>
				<identifier>
					<system value="http://fhir.nhs.net/Id/sds-role-profile-id"/>
					<value value="673836492727"/>
				</identifier>
				<practitioner>
					<reference value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				</practitioner>
				<organization>
					<reference value="urn:uuid:a82b49f8-2780-47cc-aa4b-62f79aa4ade9"/>
				</organization>
				<code>
					<coding>
						<code value="R0070"/>
						<dispaly value="Associate Specialist"/>
						<system value="https://fhir.nhs.uk/CodeSystem/HL7v3-SDSJobRoleName"/>
					</coding>
				</code>
			</PractitionerRole>
		</resource>
	</entry>
	<entry>
		<fullUrl value="urn:uuid:a82b49f8-2780-47cc-aa4b-62f79aa4ade9"/>
		<resource>
			<Organization>
				<id value="a82b49f8-2780-47cc-aa4b-62f79aa4ade9"/>
				<identifier>
					<use value="official"/>
					<system value="https://fhir.nhs.uk/Id/ods-organization-code"/>
					<value value="RR8"/>
				</identifier>
				<type>
					<coding>
						<code value=""/>
						<system value=""/>
						<display value=""/>
					</coding>
				</type>
				<name value="LEEDS TEACHING HOSPITAL TRUST"/>
				<telecom>
					<system value="phone"/>
					<value value="0113 243 3144"/>
				</telecom>
				<address>
					<line value="ST. JAMES&#39;S UNIVERSITY HOSPITAL"/>
					<line value="BECKETT STREET"/>
					<city value="LEEDS"/>
					<postalCode value="LS9 7TF"/>
					<country value="ENGLAND"/>
				</address>
			</Organization>
		</resource>
	</entry>
	<entry>
		<fullUrl value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
		<resource>
			<Practitioner>
				<id value="b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				<identifier>
					<system value="https://fhir.nhs.uk/Id/sds-user-id"/>
					<value value="676789689789"/>
				</identifier>
				<name>
					<family value="Jones"/>
					<given value="Steve"/>
					<prefix value="Dr"/>
				</name>
			</Practitioner>
		</resource>
	</entry>
	<entry>
		<fullUrl value="urn:uuid:b6f5dd89-fc3a-466d-baad-126c0aac46fc"/>
		<resource>
			<Patient>
				<id value="b6f5dd89-fc3a-466d-baad-126c0aac46fc"/>
				<identifier>
					<extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
						<valueCodeableConcept>
							<coding>
								<system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1"/>
								<code value="01"/>
								<display value="Number present and verified"/>
							</coding>
						</valueCodeableConcept>
					</extension>
					<system value="https://fhir.nhs.uk/Id/nhs-number"/>
					<value value="9900004948"/>
				</identifier>
			</Patient>
		</resource>
	</entry>
</Bundle>
```

# Author Examples

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!--the Summary Update Author has 2 options - a person registered on SDS, or a person not registered on SDS-->

<!--Person registered on SDS-->
<!--both the person's role and name are need for SCR-->
<!--the Composition.author should link to the PractitionerRole (which then links to the Practitioner)-->
	<entry>
			<!--the fullUrl is a generated UUID to aid bundle navligation (prefixed "urn:uuid")-->
		<fullUrl value="urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106"/>
		<resource>
			<!--the person's role is held on ParctitionerRole-->
			<PractitionerRole>
				<!--id is the logical identifier of this resource - its the same UUID as in fullUrl-->
				<id value="83c26c8f-ee72-4534-8891-0136972b2106"/>
				<identifier>
					<!--the system uri for a SDS Role Profil-->
					<system value="http://fhir.nhs.net/Id/sds-role-profile-id"/>
					<!--the paractitioner's Role Profile identifier-->
					<value value="673836492727"/>
				</identifier>
				<practitioner>
					<!--a link to the Practitioner (where name is held)-->
					<reference value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				</practitioner>
				<!--optionally the organisation of the Practitioner may be included-->
				<organisation>
					<!--link to the organisation-->
					<reference value="urn:uuid:0a8f86ba-4022-4676-90e7-a1f7d1d14310"/>
				</organisation>
			</PractitionerRole>
		</resource>
	</entry>
	<!--the Practitioner (where name is held)-->
	<entry>
		<fullUrl value="urn:uuid:b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
		<resource>
			<Practitioner>
				<id value="b1a41ee5-b88b-4f66-bd83-24343bf63dd8"/>
				<name>
					<family value="Jones"/>
					<given value="Steve"/>
					<prefix value="Dr"/>
				</name>
			</Practitioner>
		</resource>
	</entry>
	<!--the optional organisation-->
	<entry>
		<fullUrl value="urn:uuid:0a8f86ba-4022-4676-90e7-a1f7d1d14310"/>
		<resource>
			<Organization>
				<id value="0a8f86ba-4022-4676-90e7-a1f7d1d14310"/>
				<identifier>
					<!--the system uri for an ODS registered organisation-->
					<system value="https://fhir.nhs.uk/Id/ods-organization-code"/>
					<!--the ODS code of the organisation-->
					<value value="M85011"/>
				</identifier>
				<!--the name of the organisation-->
				<name value="The Bridge Street Practice"/>
		</Organization>
	</resource>
	</entry>
```