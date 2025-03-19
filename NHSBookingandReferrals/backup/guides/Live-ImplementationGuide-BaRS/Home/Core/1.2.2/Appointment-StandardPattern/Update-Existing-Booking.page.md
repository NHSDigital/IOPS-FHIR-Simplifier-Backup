---
topic: core-StandardPattern-appointment-update-1.2.2
---

### Update

To update an appointment:

* Perform a GET operation using the id of the appointment to /Appointment/{id}
* Ammend or append the resource as required.
* Perform a PUT operation using the id of the appointment to /Appointment/{id} or POST against /$process-message, with a corresponding FHIR bundle (BaRS Applications only)

In this example a placeholder was created, and updated when the slot is selected. This is a hypothetical scenario.

resource returned:
```json
{
	"resourceType": "Appointment",
    "id":"aca94bdb-2e38-4399-9ece-2ba083ce65b5"
	"meta": {
		"lastUpdated": "2024-01-11T15:01:30.8185338+00:00",
		"profile": [
			"https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment"
		]
	},
	"status": "waitlist",
	"description": "Reason for calling",
	"created": "2024-10-08T15:01:30+00:00",
	"participant": [
		{
			"actor": {
				"reference": "urn:uuid:788660eb-d2c9-4773-abd4-318484673fb2"
			},
			"status": "accepted"
		}
	]
}
```

Request Body

```json
{
	"resourceType": "Appointment",
    "id":"aca94bdb-2e38-4399-9ece-2ba083ce65b5"
	"meta": {
		"lastUpdated": "2024-01-11T15:01:30.8185338+00:00",
		"profile": [
			"https://fhir.hl7.org.uk/StructureDefinition/UKCore-Appointment"
		]
	},
	"status": "booked",
    "slot": [
        {
            "reference": "urn:uuid:deb4c4b3-870b-4599-84df-5e54cef7afda"
        }
    ],
	"description": "Reason for calling",
	"start": "2024-02-12T12:30:30+00:00",
	"end": "2024-02-12T12:40:30+00:00",
	"created": "2024-10-08T15:01:30+00:00",
	"participant": [
		{
			"actor": {
				"reference": "urn:uuid:788660eb-d2c9-4773-abd4-318484673fb2"
			},
			"status": "accepted"
		}
	]
}
```
<img src="https://raw.githubusercontent.com/NHSDigital/NHSDigital-FHIR-BookingAndReferrals/main/BaRS-Images/SequenceDiagrams/BaRS_Foundation_Update.drawio.svg" ></img>

Once the appointment is updated, the Receiver is responsible for managing the pointer in the central Registry, as described {{pagelink:core-StandardPattern-document-reference-1.2.2, text: here}}.
