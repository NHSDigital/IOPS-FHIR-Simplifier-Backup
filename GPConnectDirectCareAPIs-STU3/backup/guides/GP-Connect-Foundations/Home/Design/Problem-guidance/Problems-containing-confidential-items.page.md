## {{page-title}}

Where a Problem is marked as confidential it will (as per the structured requirements on confidentially) not be included in returned data and the Confidential Items warning message will be included in the List containing the query response.

Where a Problem is not marked as confidential but includes items that are marked as confidential or are considered sensitive, the following information is returned:

- the Problem will be included in the response as normal
- the confidential item(s) will **NOT** be included in the response
- there will be **NO** reference to the confidential item(s) in the `ProblemHeader (Condition)` profile.
- the Confidential Items warning message will be included in the `List` on the relevant type of type data that was ommitted. For example if a piece of uncategorised data was excluded as it was confidential then the warning code would be in the list of uncategorised data that was returned as part of the query.

In effect, there will be a warning message that items were excluded from the response due to confidentiality but there will be no indication from which Problems(s) they were removed.

---