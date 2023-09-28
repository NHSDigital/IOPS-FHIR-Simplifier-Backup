## <code>{{page-title}}</code>

If the Task.focus is a request resource and the task is seeking fulfillment (i.e. is asking for the request to be actioned), this element identifies any limitations on what parts of the referenced request should be actioned.

`restriction.repetitions`

Optionally indicates the number of times the requested action should occur.

`restriction.period`

Optionally indicates over what time-period fulfillment is sought.

`restriction.recipient`

For requests that are targeted to more than on potential recipient/target, optionally indicates for whom is fulfillment sought.

The resource being referenced should conform to one of the following:

- <a href="https://www.hl7.org/fhir/r4/group.html">Group Resource</a>
- {{pagelink:Profile-Organization-3826477b-c49f-45cd-a6a4-a179826dd3a8}}
- {{pagelink:Profile-Patient-fa365b29-79b9-4024-9b49-729ac15e401c}}
- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}
- {{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}

---
