## {{page-title}}

In the case of using the information about a patient's permissions to build a UI this will require the consuming application to understand what the different levels of access represent. To that end, the following image illustrates what information is available at the different levels for the medical record.

{{ render: permission-levels-medical-record.png }}

The same information from the image in table format:

| Level       | Information available                                                                                                          |
| -----       | ---------------------                                                                                                          |
| `None`      | No access                                                                                                                      |
| `Summary`   | Demographics, Medications, Allergies                                                                                           |
| `Detailed`  | Everything from `Summary` + All read/clinical codes, Immunisations, Health conditions, Test results, Consultations, Referrals |
| `Documents` | Everything from `Detailed` + Documents                                                                                         |
| `Full`      | Everything from `Documents` + Free text                                                                                        |

For the appointments and prescriptions services the information/features available at the different levels are illustrated below.

{{ render: permission-levels-services.png }}

The same information from the image in table format, split into appointments and prescriptions:

### Appointments

| Service        | Level    | Information available                                 |
| -------        | -----    | ---------------------                                 |
| `Appointments` | `None`   | No access                                             |
| `Appointments` | `View`   | View appointments                                     |
| `Appointments` | `Manage` | Everything from `View` + Book and cancel appointments |

### Prescriptions

| Service         | Level    | Information available                                     |
| -------         | -----    | ---------------------                                     |
| `Prescriptions` | `None`   | No access                                                 |
| `Prescriptions` | `View`.  | View appointments                                         |
| `Prescriptions` | `Manage` | Everything from `View` + Request and cancel prescriptions |

The consuming application should use this information to provide the best experience to the patient - that is, only display features and functionality within the UI that the patient has access to.

It might be useful to show the patient that there are additional features and functionality they could access but do not current have permission to do so. For example, the application might render sections of the medical record the patient _could_ have access to but do not currently. This could be represented by displaying the sections but making them appear unavailable, potentially with a message informing the patient that they could request access to that area and directing them to the area of the application where they could make that request.