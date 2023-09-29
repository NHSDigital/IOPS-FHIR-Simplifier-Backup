---
topic:known-issues
---

## {{page-title}}

### Organization resource in Search for free slots returned Bundle

A business requirement to include `Organization` was listed in a previous version of {{pagelink:how-to-search-for-free-slots}}, without the corresponding FHIR request parameter to allow the resource to be returned in the `Bundle` (according to the FHIR rules for inclusion).

At the current time, consumer systems are using this `Organization` resource in their appointment booking products and so this resource cannot immediately be removed from the Bundle.

In order to ensure the known issue does not cause problems for providers or consumers, and to support a transition to fixing the issue, the following requirements apply for the current time:

- provider systems **SHALL** continue to return the `Organization` resource in the Search for free slots `Bundle`, except where no matching `Slot` resources were found

- provider systems **SHALL** accept the `_include:recurse=Location:managingOrganization` parameter in the {{pagelink:how-to-search-for-free-slots}} request without returning an error - however, they **SHALL** continue to return the `Organization` resource regardless of whether this parameter is present

- consumer systems **SHALL** send the `_include:recurse=Location:managingOrganization` parameter **IF** they require corresponding `Organization` resources to be returned in the `Bundle`

In a future version of this API, `Organization` resources will only be returned where the `_include:recurse=Location:managingOrganization` parameter is passed by consumers. Therefore, consumers shall pass this parameter if they require the `Organisation` resource to continue to be returned as part of their Search for free slots response.
