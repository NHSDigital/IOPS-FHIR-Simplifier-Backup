## {{page-title}}

Access to the medical record is represented by five levels:

| level       | description                  |
| -----       | -----------                  |
| `none`      | no access                    |
| `summary`   | summary record access        |
| `detailed`  | detailed coded record access |
| `documents` | documents access             |
| `full`      | full access                  |

Refer to {{pagelink:Home/Build/How-to-get-a-patient-s-permissions}} for details on what each level provides access to.

A request to update the access level for the medical record requires a `POST` request to the API with a body containing JSON.

An example request to increase the access level a patient has to `full` for their current medical record can be seen below.

```json
{
  "permissionType" : "medicalRecord",
  "medicalRecordType": "current",
  "accessLevel" : "full"
}
```
