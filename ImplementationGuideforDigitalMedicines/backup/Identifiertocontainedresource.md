### {{page-title}}

The use of a contained FHIR resource should be the last option considered. 

For resources like `Patient` this could introduce duplication within the complete FHIR payload.

`[Resource].text` elements should not be populated when using contained resources. When resources are contained inside another resource then all text should be represented in the `[Resource].text` element, including data from the contained resources. This would make the `[Resource].text` element a concatination of many strings, likely unreadable and confusing.

```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
	<contained>
		<Patient>
			<id value="patient-2245386903"/>
			<!-- patient details for Joe Bloggs -->
		</Patient>
	</contained>
	<contained>
		<Medication>
			<id value="medication-87652004"/>
			<!-- medication details for Atenolol -->
		</Medication>
	</contained>
	<subject>
		<reference value="#patient-2245386903"/>
		<display value="Joe Bloggs"/>
	</subject>
	<medicationReference>
		<reference value="#medication-87652004"/>
		<display value="Atenolol"/>
	</medicationReference>
	<!-- other elements of the MedicationRequest resource -->
</MedicationRequest>
```

This method of referencing other FHIR Resources still allows for a truly RESTful implementation with end-points handling individual Resources. For example;

`POST {base}/MedicationRequest`

`GET {base}/MedicationRequest`

**Note:** Off-the-shelf FHIR validators will not be able to validate the content of the Contained Resources so will need to be customised.

---
