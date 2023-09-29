### {{page-title}}

Where a FHIR server is not available or not used within an implementation, the reference by identifier within the same Bundle is the next recommended implementation option.

```xml
<Bundle xmlns="http://hl7.org/fhir">
	<entry>
		<fullUrl value="patient-2245386903"/>
		<resource>
			<Patient>
			<!-- patient details for Joe Bloggs -->
			</Patient>
	 	</resource>
	</entry>
	<entry>
		<fullUrl value="medication-87652004"/>
		<resource>
			<Medication>
			<!-- medication details for Atenolol -->
			</Medication>
		</resource>
	</entry>
	<entry>
		<resource>
			<MedicationRequest>
				<subject>
					<reference value="patient-2245386903"/>
					<display value="Joe Bloggs"/>
				</subject>
				<medicationReference>
					<reference value="medication-87652004"/>
					<display value="Atenolol"/>
				</medicationReference>
				<!-- other elements of the MedicationRequest resource -->
			</MedicationRequest>
		</resource>
	</entry>
</Bundle>
```

The use of a Bundle means an implementation is using a *messaging* approach. If a FHIR `MessageHeader` Resource is included then it becomes an implementation of a FHIR Message.

A typical implementations of a FHIR Messaging end-point would use the `$process-message` operation, e.g.

`POST {base}/$process-message`

The definition of each FHIR Message implemented would be defined outside the FHIR standard.

An alternative RESTful implementation would be to POST to a generic `Bundle` end-point.

`POST {base}/Bundle`

The definition of which Resources are supported by such an end-point would have to be defined outside the FHIR specification.

---