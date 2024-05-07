## {{page-title}}

When searching for data for more than one clinical area there are several factors to consider,

- Clinical safety
- Information governance
- Scale of search required
- The volume and complexity of the data that may be returned

These factors are all related and finding the best approach for a consumers use case requires the developers/commissioners of the system to understand, prioritise and balance them. In doing so they will need to mitigate any clinical risks by using levers such as design, testing and end user training recording these in the clinical safety case and hazard log that they produce.

There are resources available on or accessed from the GP Connect Access Record Structure page of the [API Catalogue](https://digital.nhs.uk/developer/api-catalogue/gp-connect-access-record-structured-fhir) to support this process,

- GP Connect structured test data records
- test data definitions
- a list of known clinical risks and possible mitigations
- guidance for clinical safety officers

### Restrictions on query parameters when making searches

We have included some rules to limit which query part parameters can be used at the same time. These rules are documented on [the API page](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html#not-permitted-parameter-combinations). In addition to this predefined queries with details of their advantages, clinical risks and mitigations are included further down this page.

This is to mitigate the following risk.

#### Clinical risk when querying more than one clinical area

When requesting data for more than one clinical area at the same time and also using part parameters, e.g. medicationSearchFromDate, then it is important to be cautious when processing the results. In this situation, it is possible that the different parts of the query will return items that may be misleading to a user of a consuming system.

Consider the example where a consuming system requests the medications from the last six months and all active problems. It is possible that one of the active problems links to a medication that is from longer than a year ago. The data held in the GP system is represented in the table below along with what the two parts of the query may contain.

For the example we will assume the query was made on the 1st February 2020:

<table class="resource-attributes" border="1">
  <tbody><tr>
    <td>Date</td>
    <td>Medications in the GP system</td>
    <td>Included in medications query return</td>
    <td>Included in problems query return</td>
  </tr>
  <tr>
    <td>03/01/2020</td>
    <td>Paracetamol</td>
    <td>Y</td>
    <td></td>
  </tr>
  <tr>
    <td>05/12/2019</td>
    <td>Ibuprofen</td>
    <td>Y</td>
    <td></td>
  </tr>
  <tr>
    <td>12/11/2019</td>
    <td>Amoxicillin</td>
    <td>Y</td>
    <td></td>
  </tr>
  <tr style="background-color:Orange">
    <td>01/04/2019</td>
    <td>Warfarin</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>05/01/2019</td>
    <td>Paracetamol</td>
    <td></td>
    <td>Y</td>
  </tr>
</tbody></table>

In this situation, the medications returned by the two separate parts of the query may be misleading to a user of a consuming system. From the data in the table we can clearly see that the warfarin would not be returned by either part of the query. However, the paracetamol which is from before the warfarin was prescribed would be returned. The clinical risk here is that a user of the consumer system may believe they have all the medications from the date of the 05/01/2019 when the paracetamol was prescribed but they are actually missing a medication that exists in the GP system but is older than 6 months but more recent than the medication returned that was linked to the problem.

#### Restrictions on parameters to mitigate the risk

In order to mitigate this risk and emphasise the separation of data in the different parts of certain queries, we have introduced rules around which filters can be used at the same time. For example, problem filters and medication date filters can’t be used while requesting consultations. This will prevent data with these sorts of gaps being returned in a single bundle.

The technical details of these rules are detailed in the [Not permitted parameter combinations](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html#not-permitted-parameter-combinations) section of the [Retrieve a patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html) page.

This data can still be requested with the same restrictions by using two calls and how this is done is detailed in the {{pagelink:Home/Build/Search/Search-examples.page.md}} page.

The search example above is shown as example number 2 - "Request medications for the last year, allergies and problems".
