## {{page-title}}

To [create](https://www.hl7.org/fhir/STU3/http.html#create) a new resource a RESTful **POST** operation with a request body SHALL be used.

```
POST [base]/[resourcetype]
```

When the server creates a new resource and returns a `201` **Created** HTTP status code, it SHALL also return a `Location` header which contains the new `logical Id` and `version Id` of the created resource.

```
Location: [base]/[type]/[id]/_history/[vid]
```

[id] and [vid] are the newly created `logical Id` and `version Id` for the resource version. An `ETag` header with the `version Id` and a `Last-Modified` header will also be included in the response.

### Available for resources[](https://gp-connect-1-6-2.netlify.app/development_fhir_api_guidance#available-for-resources-1)

|Capability|Resource(s)|
|---|---|
|**Foundations**||
|**Access Record**||
|**Appointments**|`Appointment`|

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
	<i class="fas fa-exclamation-triangle text-danger"></i> <b>Important</b>: In workshop discussions with all principal GP system vendors it has been agreed that record locking (inside the GP Community Independence Service (CIS)) will not impact on the ability of clients to query the GP Connect APIs and obtain the latest saved patient data.
</div>

### Create example: Book an appointment for a patient

Refer to [Book an appointment]() for request and response body examples for a create request.


---