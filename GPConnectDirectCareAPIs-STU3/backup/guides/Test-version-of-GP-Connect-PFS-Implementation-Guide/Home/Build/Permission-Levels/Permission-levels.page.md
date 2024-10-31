## {{page-title}}

The level of detail returned is in accordance with the patient's permission level that is set at their GP practice. 

These are outlined in accordance with GP IT Futures requirements surrounding access level, which can be found [here.](https://gpitbjss.atlassian.net/wiki/spaces/DCSDCS/pages/1391134394/View+Record+-+Citizen+-+Standard+v1.0.2)

It is the providers responsibility to ensure that the correct level of data is returned.

There are certain elements to a patient's medical record that the providers must ensure are not surfaced as part of a patient facing request due to them being deemed clinically unsafe, no matter the patient's access level. 

Provider must ensure the following are never returned as part of PFS:

* consultations with draft status (i.e. an `Encounter` with status unknown)

* diary entries

* unfiled test results

* any section of the Patient's record flagged not to share via PFS or redacted, further guidance can be found [here.](https://simplifier.net/guide/GP-Connect-Patient-Facing-Access-Record/Home/Design/Redactions?version=current)

* unreviewed documents


There are four levels of access available:

* Summary level

* Detail coded

* Full access

* Full access + documents

{{ render: permission-levels-medical-record.png }}

The same information from the image in table format:

| Level       | Information available                                                                                                          |
| -----       | ---------------------                                                                                                          |
| `None`      | No access                                                                                                                      |
| `Summary`   | Demographics, Medications, Allergies                                                                                           |
| `Detailed`  | Everything from `Summary` + All read/clinical codes, Immunistations, Health conditions, Test results, Consultations, Referrals |
| `Documents` | Everything from `Detailed` + Documents                                                                                         |
| `Full`      | Everything from `Documents` + Free text                                                                                        |

