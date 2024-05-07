## {{page-title}}

The results of a query for problem details **MUST** return a `List` containing references to all `ProblemHeader (Condition)` resources that are returned.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason.code` with the value `no-content-recorded`. In this case, `List.note` **MUST** be populated with the text ‘Information not available’.