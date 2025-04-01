## {{page-title}}

To [delete](https://www.hl7.org/fhir/STU3/http.html#delete) an existing resource, a RESTful **DELETE** operation with no request body SHALL be used.

```
DELETE [base]/[resourcetype]/[id]
```

|Capability|Resource(s)|
|---|---|
|**Foundations**||
|**Access Record**||
|**Appointments**||

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <i class="fas fa-exclamation-triangle text-danger"></i> <b>Important</b>: GP Connect clients and servers are currently not expected to utilise the ability to delete a resource using the RESTful DELETE operation. However, this section is included as implementers should ensure that their implementation choices don’t preclude the use of this HTTP verb in future release.
</div>

---