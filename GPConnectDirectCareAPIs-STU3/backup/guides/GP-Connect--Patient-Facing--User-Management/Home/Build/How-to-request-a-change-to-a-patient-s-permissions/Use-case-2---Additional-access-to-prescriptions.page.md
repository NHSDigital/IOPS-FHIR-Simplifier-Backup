## {{page-title}}

Access to the prescriptions service is represented by three levels:

| level     | description                                        |
| -----     | -----------                                        |
| `none`    | no access                                          |
| `view`    | view only                                          |
| `manage`  | view, order, amend & cancel existing prescriptions |

A request to update the access level for the prescriptions service requires a `POST` request to the API with a body containing JSON.

An example request to increase the access level a patient has to `manage` for the prescriptions service can be seen below.

```json
{
  "permissionType" : "prescriptions",
  "accessLevel" : "manage"
}
```