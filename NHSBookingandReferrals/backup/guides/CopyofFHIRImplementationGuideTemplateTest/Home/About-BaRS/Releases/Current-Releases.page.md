## Current Release 1.6.0

Product Link           | Version | Handle  | Phase    | State           | Release Date | Stability  | Change Log Link
-----------------------|---------|---------|----------|-----------------|--------------|------------|-----------------
Implementation Guide   | 1.7.0   | v1      | Live     | Current Release | 30/07/2024  | Stable     |{{pagelink:trn-General}}
[FHIR Package](https://simplifier.net/packages/uk.nhsdigital.bars.r4/1.30.1) | uk.nhsdigital.bars.r4 1.30.2@@@@@?| v1      | Live     | Current Release | 30/07/2024  | Stable     |
{{pagelink:design-core-1.1.3, text:BaRS Core}}              | 1.1.3   | v1      | Live     | Current Release | 21/05/2024   | Stable     |{{pagelink:trn-core, text: BaRS Core Change Log}}
[API Specification](https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir/v1_1_0)    | 1.1.0   | v1      | Live     | Current Release | 01/04/2023   | Stable     |{{pagelink:trn-api}}
{{pagelink: build-testing, text: TKW}}  | 1.0.8   | v1      | Live     | Current Release | 21/05/2024   | Stable     |{{pagelink:trn-tkw}}
{{pagelink:application1, text:BaRS-APP1}}   | 1.0.4   | v1      | Live     | Current Release | 21/05/2024   | Stable     |{{pagelink:trn-app1,text:BaRS APP1 Change Log}}
{{pagelink:application2, text:BaRS-APP2}}   | 1.0.4   | v1      | Live     | Current Release | 21/05/2024   | Stable     |{{pagelink:trn-app2,text:BaRS APP2 Change Log}}
{{pagelink:application3, text:BaRS-APP3}}   | 1.0.1   | v1      | Live     | Current Release | 21/05/2024   | Stable |{{pagelink:trn-app3,text:BaRS APP3 Change Log}}
{{pagelink:application4, text:BaRS-APP4}}   | 1.1.1   | v1      | Live     | Current Release | 21/05/2024   | Stable |{{pagelink:trn-app4,text:BaRS APP4 Change Log}}
{{pagelink:application5, text:BaRS-APP5}}   | 1.0.0   | v1      | Live     | Current Release | 30/07/2024   | Stable |{{pagelink:trn-app5,text:BaRS APP5 Change Log}}
{{pagelink:application6, text:BaRS-APP6}}   | 1.0.0-beta.1 | beta      | Live     | Current Release | 21/05/2024   | Pre-Release |{{pagelink:trn-app6,text:BaRS APP6 Change Log}}


### Overview of the release

This release of the BaRS marks the conclusion of the beta period for Application 5 and this application now moves to a stable v1.0.0 release available for wide use and adoption.

There have also been a number of bug fixes and corrections to the guide

A Clinical Safety assessment of the scope of this release has determined that it has not significantly changed the clinical safety profile of the BaRS. No new Hazards have been identified in this release. The latest version of the BaRS Clinical Safety Case and Hazard Log can be downloaded from the <a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir/onboarding-support-information" target="_blank">BaRS FHIR API onboarding support information page</a>. 
<br>
<hr>

## Versioning Matrix

<table>
<thead>
	<tr>
		<th data-no-sort="">Application Version</th>
		<th data-no-sort="">Minimum BaRS Guide Version</th>
		<th data-no-sort="">Minimum Core Version</th>
		<th data-no-sort="">Minimum API Spec version</th>
	</tr>
</thead>
<tbody>
	<tr>
		<td>Application 1 v1.0.1</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.1.0" target="_blank">v1.1.0</a></td>
		<td rowspan=7 style="text-align: center; vertical-align: middle;"><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/Home/Design/BaRS-Core?version=1.0.0" target="_blank">v1.0.0</a></td>
		<td rowspan=7 style="text-align: center; vertical-align: middle;"><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir/v1_0_0" target="_blank">1.0.0</a></td>		
	</tr>
	<tr>
		<td>Application 1 v1.0.3</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.4.0" target="_blank">v1.4.0</a></td>
	</tr>
	<tr>
		<td>Application 2 v1.0.1</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.1.0" target="_blank">v1.1.0</a></td>
	</tr>
	<tr>
		<td>Application 2 v1.0.3</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.4.0" target="_blank">v1.4.0</a></td>
	</tr>
	<tr>
		<td>Application 3 v1.0.0</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.4.0" target="_blank">v1.4.0</a></td>
	</tr>
	<tr>
		<td>Application 4 v1.0.0</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.4.0" target="_blank">v1.4.0</a></td>
	</tr>
	<tr>
		<td>Application 4 v1.1.0</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.5.0" target="_blank">v1.5.0</a></td>
	</tr>
	<tr>
		<td>Application 5 v1.0.0</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.7.0" target="_blank">v1.7.0</a></td>
		<td rowspan=2 style="text-align: center; vertical-align: middle;"><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/Home/Core?version=1.4.0" target="_blank">v1.1.0</a></td>
		<td rowspan=2 style="text-align: center; vertical-align: middle;"><a href="https://digital.nhs.uk/developer/api-catalogue/booking-and-referral-fhir/v1_1_0" target="_blank">1.1.0</a></td>
	</tr>
	<tr>
		<td>Application 6 v1.0.0-beta</td>
		<td><a href="https://simplifier.net/guide/nhsbookingandreferralstandard/home?version=1.5.0" target="_blank">v1.5.0</a></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
		<td></td>
		<td></td>
	</tr>
</tbody>
</table>


