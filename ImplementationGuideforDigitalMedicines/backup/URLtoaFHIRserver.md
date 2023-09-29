### {{page-title}}

Using references by URL is the recommended / target solution where FHIR servers are available. These may be future nationally available FHIR servers or locally implemented FHIR servers. When referencing by URL it is recommended that the `reference.display` is populated with appropriate text as per the guidance within this document.

```xml
<MedicationRequest xmlns="http://hl7.org/fhir">
	<subject>
		<reference value="https://acmefhirserver/patient/2245386903"/> 
		<!-- where 2245386903 is the NHS number for Joe Bloggs held as the 'id' -->
		<display value="Joe Bloggs"/>
	</subject>
	<medicationReference>
		<reference value="https://acmefhirserver/medication/87652004"/> 
		<!-- where 87652004 is the dm+d concept code for Atenolol held as the 'id' -->
		<display value="Atenolol"/>
	</medicationReference>
	<!-- other elements of the MedicationRequest resource -->
</MedicationRequest>
```

This method of referencing other FHIR Resources allows for a truly RESTful implementation with end-points handling individual Resources. This is because the referenced Resources are not included within the transaction either in a Bundle or as Contained Resources. For example;

`POST {base}/MedicationRequest`

`GET {base}/MedicationRequest`

---