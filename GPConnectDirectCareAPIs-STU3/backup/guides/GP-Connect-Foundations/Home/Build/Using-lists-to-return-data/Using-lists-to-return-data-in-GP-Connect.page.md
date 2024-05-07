## {{page-title}}

The `List` resource in FHIR is used to manage collections of resources.

In GP Connect it is used to organise data returned by a query into groups of resources that can then be processed more easily. For each clinical area query, GP Connect will return a list that identifies the data returned for that query. This is considered to be the primary list relating to that area.

- When an API call returns data for more than one clinical area, the list will identify which data has been returned for which clinical area.
- Where there are no items returned, the primary list will be returned empty.
- Where the return includes warning codes for example, to indicate when clinical data is excluded, those codes will be included in any list profile the item would have been present in.

When either problems or consultations are requested then in addition to the primary list the response will contain further secondary lists which detail resources that are contained in the requested consultations or have been linked to the problems that are returned. All the information needed to process the data from these clinical areas will be contained in these primary and secondary lists. The secondary lists related to each area are contained in the table below.

The list containing resolved allergies is a special case as it is a list where the resources are contained within it. This is a safety precaution intended to reduce the risk of resolved allergies being confused with active allergies. It means resolved allergies can only be referenced in context to the list and do not exist independently outside the list. Where resolved allergies are returned as part of a problems or consultations call the primary list **MUST** also be returned so that the resolved allergies can be referenced from the problems and consultations lists in the context of that list.

Further details about how the allergies lists work can be found on the {{pagelink:Home/Design/Allergies-Guidance}}.

In GP Connect we also use lists to represent the structure of consultations. This is a separate topic that is documented in the page {{pagelink:Home/Design/Consultations-guidance}}.

In this version of the GP Connect specification there are 10 types of primary lists that contain the data returned in response to a query that are listed in the table below.

### Primary lists in the query response

| Clinical area                   | SNOMED Code      | SNOMED Preferred Term           | List.title                      |
| -------------                   | -----------      | ---------------------           | ----------                      |
| Allergies and adverse reactions | 886921000000105  | Allergies and adverse reactions | Allergies and adverse reactions |
| Allergies that have been ended  | 1103671000000101 | Ended allergies                 | Ended allergies                 |
| Consultations                   | 1149501000000101 | List of consultations           | List of consultations           |
| Diary Entries                   | 714311000000108  | Patient recall administration   | Patient recall administration   |
| Immunisations                   | 1102181000000102 | Immunisations                   | Immunisations                   |
| Investigations                  | 887191000000108  | Investigations and results      | Investigations and results      |
| Medications and medical devices | 933361000000108  | Medications and medical devices | Medications and medical devices |
| Outbound Referrals              | 792931000000107  | Outbound referral               | Outbound referral               |
| Problems                        | 717711000000103  | Problems                        | Problems                        |
| Uncategorised data              | 826501000000100  | Miscellaneous record            | Uncategorised data              |

### Secondary lists in the query response

There are also 21 secondary lists that will contain data that is linked to problems or contained in consultations. These are defined in this [codeSystem](https://fhir.hl7.org.uk/STU3/CodeSystem/GPConnect-SecondaryListValues-1) and are detailed in the table below.

| List.title                                                                | Code                                                                    | Display                                                                   |
| ----------                                                                | ----                                                                    | -------                                                                   |
| Consultations - allergies contained in consultations                      | consultations-allergies-contained-in-consultations                      | Consultations - allergies contained in consultations                      |
| Consultations - allergies that have been ended contained in consultations | consultations-allergies-that-have-been-ended-contained-in-consultations | Consultations - allergies that have been ended contained in consultations |
| Consultations - diary entries contained in consultations                  | consultations-diary-entries-contained-in-consultations                  | Consultations - diary entries contained in consultations                  |
| Consultations - documents contained in consultations                      | consultations-documents-contained-in-consultations                      | Consultations - documents contained in consultations                      |
| Consultations - immunisations contained in consultations                  | consultations-immunisations-contained-in-consultations                  | Consultations - immunisations contained in consultations                  |
| Consultations - investigations contained in consultations                 | consultations-investigations-contained-in-consultations                 | Consultations - investigations contained in consultations                 |
| Consultations - medications contained in consultations                    | consultations-medications-contained-in-consultations                    | Consultations - medications contained in consultations                    |
| Consultations - outbound referrals in consultations                       | consultations-outbound-referrals-in-consultations                       | Consultations - outbound referrals in consultations                       |
| Consultations - problems contained in consultations                       | consultations-problems-contained-in-consultations                       | Consultations - problems contained in consultations                       |
| Consultations - uncategorised data contained in consultations             | consultations-uncategorised-data-contained-in-consultations             | Consultations - uncategorised data contained in consultations             |
| Problems - allergies related to problems                                  | problems-allergies-related-to-problems                                  | Problems - allergies related to problems                                  |
| Problems - allergies that have been ended related to problems             | problems-allergies-that-have-been-ended-related-to-problems             | Problems - allergies that have been ended related to problems             |
| Problems - consultations related to problems                              | problems-consultations-related-to-problems                              | Problems - consultations related to problems                              |
| Problems - diary entries related to problems                              | problems-diary-entries-related-to-problems                              | Problems - diary entries related to problems                              |
| Problems - documents related to problems                                  | problems-documents-related-to-problems                                  | Problems - documents related to problems                                  |
| Problems - immunisations related to problems                              | problems-immunisations-related-to-problems                              | Problems - immunisations related to problems                              |
| Problems - investigations related to problems                             | problems-investigations-related-to-problems                             | Problems - investigations related to problems                             |
| Problems - medications related to problems                                | problems-medications-related-to-problems                                | Problems - medications related to problems                                |
| Problems - outbound referrals related to problems                         | problems-outbound-referrals-related-to-problems                         | Problems - outbound referrals related to problems                         |
| Problems - linked problems not relating to the primary query              | problems-linked-problems-not-relating-to-the-primary-query              | Problems - linked problems not relating to the primary query              |
| Problems - uncategorised data related to problems                         | problems-uncategorised-data-related-to-problems                         | Problems - uncategorised data related to problems                         |
