## {{page-title}}

1. The first step in the user journey would be to retrieve the prescription reorder requests, this will be retrieved by the get requested prescription reorders endpoint, using the patients NHS number i.e. GET /Task/?patient=`{NHSNumber}`.

    This will return a `Bundle` of `Task` resources linked to the patient. At this stage we have a list of requests the patient could send a cancellation for.
2. At this point the patient would choose a request to send a cancellation for, this must only be possible for a request (`Task` resource) with status of `Requested`. Any other status will return an error.
    
    Once the request to cancel has been selected a JSON Patch must be sent to PATCH /Task/id?{selected id of the request}
    
    The patch must look identical to:

```json
    {
        "op": "replace",
        "path": "/status",
        "value": "cancelled"
    }
```

3. This will then update the status of the request to cancelled.