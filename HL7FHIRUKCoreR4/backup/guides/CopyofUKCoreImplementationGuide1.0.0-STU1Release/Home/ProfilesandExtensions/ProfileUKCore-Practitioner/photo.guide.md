## photo

A photograph relating to a practitioner. This can be included as either:

- An attachment encoded as base64Binary with a relevant MIME contentType: image/png, image/jpg or image/jpeg preferred.

e.g. 
```
"photo": [
    {
      "contentType": "image/png",
      "data":"{base64Binary} "
    }
]
```
and/or

- URL where the data can be found.

If both are used the URL MUST point to the same data as that encoded in the attachment.