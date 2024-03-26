## {{page-title}}

Representing data that is returned in relation to both consultations and problems requires a response that is able to return multiple types of data. A response to a query about consultations or problems may contain any type of clinical data that can be entered into a GP system.

In GP Connect we use secondary lists to organise these contained or linked items. When either of these clinical areas is queried then up to 11 secondary lists may be returned. Each list is detailed in the above table.

These lists will only be returned where data exists in the clinical system that is returned as part of the query. If no data suitable to populate a list is present in the record that is being sent then the list will not be included in the response.

For example if a query was made to GP Connect for all problems in a record but none of these problems related to an outbound referral, then there would be no list for ‘Outbound referrals related to problems’ contained in the response.

The following rules apply to how secondary lists are populated

- Secondary lists will only be present where problems or consultations clinical areas have been queried directly
- Secondary lists will only be present where data is available
- Secondary lists for items related to problems will include items related to the problem by the extensions relatedClinicalContent and actualProblem
- If data has been excluded from a secondary list for one of the reasons defined in the warning code section, then the relevant warning code(s) **SHALL** be included
- For consultation secondary lists where data is excluded a warning code **SHALL** be present even if no other data is contained in the list
- Secondary lists will never return an empty list with no warning codes