## {{page-title}}

Access to the appointments service is represented by three levels:

| level     | description                                      |
| -----     | -----------                                      |
| `none`    | no access                                        |
| `view`    | view only                                        |
| `manage`  | view, book, amend & cancel existing appointments |

A request to update the access level for the appointments service requires a `POST` request to the API with a body containing JSON.

An example request to increase the access level a patient has to `manage` for the appointments service can be seen below.

```json
{
  "permissionType" : "appointments",
  "accessLevel" : "manage"
}
```