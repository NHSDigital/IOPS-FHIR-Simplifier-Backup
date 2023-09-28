## {{page-title}}

Where there are no `AllergyIntolerance` resources in the patient record, including none stating ‘No Known Allergies’ it is the responsibility of the provider system to make this clear to consumer systems.

### Presenting no allergy information using a FHIR List

Where the provider system is returning allergy information within a **FHIR List** then the provider system **MUST** return an empty List with an emptyReason FHIR code: “`No content recorded`” and a List.note with the text: "Information not available". This aligns with the implementation used by GPConnect.
``` xml
<list>
  <id>UKCore-NoAllergyData-List-Example</id>
  <meta>
    <profile>https://fhir.hl7.org.uk/StructureDefinition/UKCore-List</profile>
  </meta>
  <status>current</status>
  <mode>snapshot</mode>
  <code>
    <coding>
      <system>http://snomed.info/sct</system>
      <code>886921000000105</code>
      <display>Allergies and adverse reactions</display>
    </coding>
  </code>
  <patient>
    <reference>Patient/UKCore-Patient-RichardSmith-Example</reference>
    <display>Richard Smith</display>
    <identifier>
      <system>https://fhir.nhs.uk/Id/nhs-number</system>
      <value>9912003888</value>
    </identifier>
  </patient>
  <date>2021-07-21T12:00:00+00:00</date>
  <emptyReason>
    <coding>
      <system>https://fhir.hl7.org.uk/CodeSystem/UKCore-ListEmptyReasonCode</system>
      <code>no-content-recorded</code>
      <display>No Content Recorded</display>
    </coding>
  </emptyReason>
  <note>
    <text>Information not available</text>
  </note>
</list>
```
JSON
``` json
{
  "resource": {
    "resourceType": "List",
    "id": "UKCore-NoAllergyData-List-Example",
    "meta": {
      "profile": [
      "https://fhir.hl7.org.uk/StructureDefinition/UKCore-List"
      ]
    },
    "status": "current",
    "mode": "snapshot",
    "code": {
      "coding": [
        {
          "system": "http://snomed.info/sct",
          "code": "886921000000105",
          "display": "Allergies and adverse reactions"
        }
      ]
    },
    "patient": {
      "reference": "Patient/UKCore-Patient-RichardSmith-Example",
      "display": "Richard Smith",
      "identifier": [
        {
          "system": "https://fhir.nhs.uk/Id/nhs-number",
          "value": "9912003888"
        }
      ]
    },
    "date": "2021-07-21T12:00:00+00:00",
    "emptyReason": {
      "coding": [
        {
          "system": "https://fhir.hl7.org.uk/CodeSystem/UKCore-ListEmptyReasonCode",
          "code": "no-content-recorded",
          "display": "No Content Recorded"
        }
      ]
    },
    "note": [
      {
        "text": "Information not available"
      }
    ]
  }
}
```

### Presenting no allergy information using a FHIR Bundle

Where the provider system is returning allergy information within a **FHIR Bundle** then, without extending the FHIR standard, provider systems should return as per the following;

XML
```xml
<Bundle>
	<id value="UKCore-NoAllergyData-Bundle-Example"/>
	<meta>
		<lastUpdated value="2021-07-21T12:00:00+00:00"/>
	</meta>
	<type value="searchset"/>
	<total value="0"/>
	<link>
		<relation value="self"/>
		<url value="https://[base]/AllergyIntolerance?patient%3Aidentifier=9912003888"/>
	</link>
</Bundle>
```

JSON

``` json
{
   "Bundle": {
      "id": {
         "_value": "UKCore-NoAllergyData-Bundle-Example"
      },
      "meta": {
         "lastUpdated": {
            "_value": "2021-07-21T12:00:00+00:00"
         }
      },
      "type": {
         "_value": "searchset"
      },
      "total": {
         "_value": "0"
      },
      "link": {
         "relation": {
            "_value": "self"
         },
         "url": {
            "_value": "https://[base]/AllergyIntolerance?patient%3Aidentifier=9912003888"
         }
      }
   }
}
```

---