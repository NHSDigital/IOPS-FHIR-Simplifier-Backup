## {{page-title}}

Warning codes are used to manage negation where resources are present in a system to be returned by a query but are not included in the returned data for a specific reason.

Warning codes will be returned in the primary and secondary lists defined on this page when any item that would have been included in that list as a response to the query is not present due to one of the defined reasons. In the case where an item may have been present in more than one list, e.g. medications and medications related to problems, the warning code will be present in both lists. Any warning codes returned will be contained in the extension List.extension[warningCode].

Warning codes will **NOT** be returned in any of the lists used to represent consultations structure that are defined in the page [CareConnect-GPC-List-1](https://simplifier.net/guide/gpconnect-data-model/Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1?version=current).

Where a warning code is returned related to an item from a given clinical area, for example referrals, if the referrals capability is turned off then the warning code **MUST** still be returned if the list that it would have been present in is still contained in the response. This applies to all clinical areas.

The following table provides details of the warning codes that are to be used in the warningCode extension in GP Connect. More guidance for each code follows in the subsequent sections.

<table class='resource-attributes' border='1'>
  <tr>
    <td>Display</td>
    <td>Code</td>
    <td>Associated text</td>
  </tr>
  <tr>
    <td>Confidential Items</td>
    <td>confidential-items</td>
    <td>Items excluded due to confidentiality and/or patient preferences.</td>
  </tr>
  <tr>
    <td>Data in Transit</td>
    <td>data-in-transit</td>
    <td>Patient record transfer from previous GP practice not yet complete; information recorded before dd-Mmm-yyyy may be missing.</td>
  </tr>
   <tr>
    <td>Data awaiting filing</td>
    <td>data-awaiting-filing</td>
    <td>Patient record contains some items in the GP practice workflow that have not been reviewed for inclusion in this message; information recorded before dd-Mmm-yyyy may be missing.</td>
  </tr>
</table>

### Confidential items

Where items have been excluded from the returned resources due to patient consent preferences or as they are part of the exclusion dataset this **MUST** be indicated at the list level. If an item that would have been an entry in a list is excluded the warningCode field **MUST** be populated using the confidential items warning code from the above table. The associated text **MUST** also be added into the note field when the code is used.

Note: If the results of a search contained only confidential items, it would present as an `List` with no entries, an `emptyReason` and the Confidential Items warning code.
Note: If an element of a diagnostic report is made confidential then the warning code **SHALL** be populated in the relevant `Investigations` list.

### Data in transit

This only refers to data transmitted from GP to GP when a patient moves GP practice. This is where a patient is registered at their new GP practice but their medical records from their previous GP practice have not yet been received and/or incorporated into their new GP practice system. When this takes place all the lists returned **MUST** be populated using the data in transit warning code from the above table. The associated text **MUST** also be added into the note field when the code is used. Set dd-mmm-yyyy to the date the patient registered at their new GP practice.
