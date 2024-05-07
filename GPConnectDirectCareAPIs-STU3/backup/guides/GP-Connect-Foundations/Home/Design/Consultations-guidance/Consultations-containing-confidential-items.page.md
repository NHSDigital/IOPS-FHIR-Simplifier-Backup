## {{page-title}}

A consultation which is marked as confidential  will (as per the structured requirements on confidentially) not be included in the returned data, and the Confidential Items warning message will be included in the primary List containing the query response.

If a consultation **is not** marked as confidential, but includes items that are marked as confidential or are considered sensitive, the following information is returned:

- the consultation will be included in the response as normal
- the confidential item(s) will **NOT** be included in the response
- there will be **NO** reference to the confidential item(s) in the `List` profiles defining the consultation structure
- the Confidential Items warning message will be included in the appropriate secondary list ({{pagelink:Home/Build/Using-lists-to-return-data/Using-secondary-lists-to-respond-to-queries-for-consultations-and-problems.page.md }}) for the relevant type of type data that was omitted (for example, if a piece of uncategorised data was excluded as it was confidential then the warning code would be in the List "Consultations - uncategorised data contained in consultations" that was returned as part of the query) - the warning will **NOT** be included in the `List` profiles defining the consultation structure

In effect, there will be a warning message that items were excluded from the response due to confidentiality but there will be no indication from which consultation(s) they were removed from.

---