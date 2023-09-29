## {{page-title}}

- The results of a query for uncategorised data **MUST** return a List containing references to all `Observation` resources that are returned.
- The `List` **MUST** be populated in line with the guidance on `List` resources.
- If the `List` is empty, then an empty `List` **MUST** be returned with a value of `no-content-recorded` in the `emptyReason.code` The `List.note` **MUST** also be populated with the text "Information not available".