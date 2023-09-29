### Resource reference to contained resource

This **SHOULD NOT** be used as an alternative to FHIR RESTful API using resources. This should only be used when the resource is not complete, for example only the name of the patient or medication is known. 
This is not used in EPS.

The use of a contained FHIR resource should be the last option considered. The use of the `#` character.


```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
	<contained>
		<Patient>
			<id value="#1"/>
			<!-- patient details for Joe Bloggs -->
		</Patient>
	</contained>
	<contained>
		<Medication>
			<id value="#2"/>
			<!-- medication details for Atenolol -->
		</Medication>
	</contained>
	<subject>
		<reference value="#1"/>
		<display value="Joe Bloggs"/>
	</subject>
	<medicationReference>
		<reference value="#2"/>
		<display value="Atenolol"/>
	</medicationReference>
</MedicationRequest>
```