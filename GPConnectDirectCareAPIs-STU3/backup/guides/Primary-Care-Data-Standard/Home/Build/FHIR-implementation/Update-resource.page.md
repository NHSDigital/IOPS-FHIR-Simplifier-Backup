## {{page-title}}

To [update](https://www.hl7.org/fhir/STU3/http.html#update) an existing resource, a RESTful **PUT** operation with a request body SHALL be used.

```
PUT [base]/[resourcetype]/[id]
```

The PUT operation will only be used to update existing resources. If the specified resource within the URL does not exist on the provider system an error SHALL be returned.

|Capability|Resource(s)|Field(s)|
|---|---|---|
|**Foundations**|||
|**Access Record**|||
|**Appointments**|`Appointment`|reason, description, comment|

---

### Update example: Modify the appointment booking reason

Refer to [Amend an appointment]() for request and response body examples for a request which updates a resource using the PUT HTTP verb.

---