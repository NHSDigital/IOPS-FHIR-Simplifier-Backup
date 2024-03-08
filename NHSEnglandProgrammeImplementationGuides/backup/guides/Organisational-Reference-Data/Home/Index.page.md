## What is Organisation Data Service (ODS)?

This implementation guide provides guidance on implementing the Organisation Reference Data FHIR R4 API.

The Organisation Data Service (ODS) issues and manages unique identification codes (ODS codes) and accompanying reference data for organisations that interact with any area of the health and social care system. 

## What is Organisation Reference Data?

Data that is published by ODS is referred to as Organisation Reference Data (ORD) and it is used in almost every IT system across the NHS to support key functionality such as messaging, referrals, financial transactions, access control, reporting and analytics.

Primarily, ORD includes organisations and their sites that are based in England, but we also publish data for some organisations based in Wales, Scotland, Isle of Man, Channel Islands and Northern Ireland. ORD also includes postcode level data that defines key health and social care geographic boundaries.

Organisation and Site records published within the Organisation Resource are distinguished by a Record Class and are currently defined as follows:

-	Organisation: One or more people with a common purpose of function and whose activities encompass the funding, direction or provision of health or social care and support services; this includes public, private or voluntary sector Organisations.

-	Site: The primary function of an ODS Site is to identify an association between an Organisation and a place with which it is affiliated. All Site entities have an association to an Org and the Site record is generally real estate that the Org owns, provides a service at, or has some staff based within. Site does not provide unique identifiers for locations at present. Multiple Site instances can point to the same physical place if more than one Org owns or provides patient care at that place; in this instance each Org may have its own Site to reflect its affiliation with the same physical place (e.g. a hospital). Note: Work is planned to review and reclassify Sites as ‘Locations’ or ‘Services’ as appropriate, which will improve and refine the Organisation resource in future.

Refer to NHS conditions for information <a href='https://digital.nhs.uk/services/organisation-data-service' class="external">[ODS]</a>

<h3 id="licence-heading">Licence</h3>

<div markdown="span" class="alert alert-warning" role="alert"><h4 id="Licence"><i class="fas fa-gavel"></i> Licensing and Publisher</h4>
<ul>
<li>
Copyright© 2023+ NHS England Licensed under the Apache License, Version 2.0 (the &quot;License&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an &quot;AS IS&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7&#174; FHIR&#174; standard Copyright &#169; 2011+ HL7 The HL7&#174; FHIR&#174; standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.
<li>
Developed and authored by NHS England Interoperability Team.
</ul>
</div>