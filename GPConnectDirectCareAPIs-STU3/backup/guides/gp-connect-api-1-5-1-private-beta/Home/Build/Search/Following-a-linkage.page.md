## {{page-title}}

For the majority of scenarios, the information required by the consumer can be retrieved through a single query. The consumer system identifies which clinical areas of the patient record it requires and which search criteria should be applied, then calls the GP Connect API. The provider system then returns all the requested information in a single bundle.

There are, however, scenarios where the information to the first query identifies additional information that is required.

For example:

- a retrieved medication is linked to a problem that the clinician wants to review
- a retrieved problem is linked to several consultations that the clinician wants to review
- a retrieved immunisation is linked to a consultation that the clinician wants to review

There may be a decision by the consuming system (or by a user of the consuming system) that they require additional information about the linked clinical item. To get these, the consumer system may wish to call the GP Connect API a second time.

This version of GP Connect does not allow a consumer to search for a specific item in the patient record by its identifier. Instead the consumer should use the supported filters to retrieve a larger dataset and then search for the required item(s) within that dataset.

For example:

- To display a specific consultation linked to a problem, the consumer system could request all the consultations that took place within the active period of the problem then search for the required consultation within the returned data.