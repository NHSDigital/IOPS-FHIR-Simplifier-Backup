## {{page-title}}

<table>
 <tr>
   <td>
   <a href="https://www.local.gov.uk/topics/social-care-health-and-integration/public-health">
   {{render:diagrams-Public-Health-LocalGov}}
   </a>
   </td>
   <td>
   <a href="https://www.nhs.uk/better-health/get-active/">
   {{render:diagrams-Public-Health-NHSEngland}}
   </a>
   </td>
 </tr>
</table>

Introduce the early part of the journey. 

Citizen self selected Physical Activity and Weight Management interventions may have started recording the following data, in a Personal Health Records (PHR) application such as Apple Health, Google Health, Strava, FitBit, etc.

- weight
- steps
- pulse rate
- spO2
- activity data

{{render:diagrams-EHR-Record-Types-Observations-Apple}}

As this data is largely observation based the `Query API` can be used here. These will also appear on interventions and procedures (specifically Virtual Wards) but from a patient perspective they start here. 

### Frameworks Used

| Framework | Description |
|--
| {{pagelink:Home/Technical-Framework/Query-API}} | Many of the PHR apps shared their data via Query API's, these tend to be bespoke API's (i.e. don't use an open standard like FHIR but are often similar).  |
| {{pagelink:Home/Technical-Framework/Other-Frameworks-or-Patterns/Devices-and-Wearables.page.md}} | Links to guidance on Devices and Wearables. | 

