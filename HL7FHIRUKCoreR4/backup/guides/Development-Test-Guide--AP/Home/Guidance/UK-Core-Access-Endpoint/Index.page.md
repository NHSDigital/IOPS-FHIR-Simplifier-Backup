---
topic: Guidance-AccessEndpoint
---
## {{page-title}}

This section of the Implementation Guide specifies the minimum requirements for a RESTful endpoint providing read-only access for direct care and subject of care access within the UK. It uses the UK specific resource profiles defined in this STU3 Sequence implementation guide and  provides implementers with a mechanism to share information that conforms to the UK Core profiles.

The guidance is aligned as far as possible to existing international specifications that provide similar capabilities such as HL7 IPA, IHE PDQm and IHE QEDm and provides many {{pagelink:Related-Specifications,text:common capabilities}}.

Data Controllers holding personal data related to health and care may provide the capabilities specified in this guidance when implementing systems to allow authenticated and authorised consumers to access the data. The guidance is intended to be compatible with **all** systems used to manage care provision. Language specific to the health domain, such as 'Patient', is used for technical clarity but there is no reason that these APIs should not be used in other domains where different terms for the subject of care are used.

### Actors
The following Actors participate in the interactions described in this guidance:

<table class="assets">
<tr>
<th width="40%">Actor</th>
<th width="60%">Role</th>
</tr>

<tr>
<td>{{pagelink:Patient-Index-Provider}} </td>
<td>Instantiates a FHIR RESTful API endpoint providing the UK Core Access Patient Index [capabilities](./CapabilityStatement-UKCoreAccessPatientIndexProvider.html) </td>
</tr>	

<tr>
<td>{{pagelink:Clinical-Data-Provider}} </td>
<td>Instantiates a FHIR RESTful API endpoint providing the UK Core Access Clinical Data [capabilities](./CapabilityStatement-UKCoreAccessClinicalDataProvider.html) </td>
</tr>	

<tr>
<td>{{pagelink:Consumer}} </td>
<td>Requests information from one or more Providers </td>
</tr>	
</table>

<br>

A FHIR RESTful API endpoint may provide the capabilities of one or more Actors, provided that it satisfies the requirements for each Actor.
For example, an endpoint may be both a Patient Index Provider AND Clinical Data Provider.

<hr class="thickline">