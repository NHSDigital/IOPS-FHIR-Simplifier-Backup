## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Overview of the role of the Spine Secure Proxy (SSP) within GP Connect
</div>

## Overview

The Spine Secure Proxy (SSP) is a forward HTTP proxy which is used as a broker to control and protect access to GP principal IT systems that expose FHIR based GP Connect APIs.  

It provides a single security point for both authentication and authorisation for consuming systems. Additional responsibilities include auditing of requests, checking data sharing agreements and transaction logging. 

All HTTP communications are secured using TLS MA. This includes both legs of the request, from consumer system to the proxy and then from the proxy to provider system.

{{render: sspdiagram.png}}

## Constructing a request

A consumer system queries Spine Directory Service using the provider's ODS code to determine:

- the provider's service root URL ({{pagelink:Home/Build/General-API-guidance.page.md}}) (their "base endpoint")
- the provider's ASID, used in headers below

Once these are retrieved, a GP Connect HTTP request is constructed to send to the SSP in the following format:

```
GET https://[ssp_fqdn]/[provider_service_root_url]/[fhir_request]
```

Where:

  - `[ssp_fqdn]` is the fully qualified domain name of the SSP
  - `[provider_service_root_url]` is the provider's service root URL as returned from SDS in the `nhsMhsEndPoint` attribute. This element is normally in the format `https://[provider_fqdn]/[path_to_fhir_base]`
  - `[fhir_request]` is the local portion of the request relating to the FHIR API call being made, including query parameters

Please note `GET` is used as an example; the actual HTTP method will vary based on API call.


<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: The SSP will reject requests where the `provider_service_root_url` portion of the above URL does not match that held in SDS (in the nhsMhsEndPoint attribute). Consumer systems must take care not to amend this portion, for example replacing the domain name with an equivalent IP address, or adding an explicit :`443` port declaration.
</div>

As an example, to request a patient's structured record, the following URL would be constructured (HTTP headers and payload are not included):

```
POST https://testspineproxy.nhs.uk/https://pcs.thirdparty.nhs.uk/T99999/STU3/1/Patient/$gpc.getstructuredrecord
```

Please see a worked example of the endpoint lookup process ({{pagelink:Home/Authentication/Integrate-with-Spine/Spine-Directory-Services/Overview-and-querying.page.md}}) for more information.

## HTTP headers

The SSP requires a number of Spine specific HTTP headers to be populated when sending a request:

| Header               | Value | Notes |
|----------------------|-------|-------|
| `Ssp-TraceID`        | Consumer Trace ID | GUID/UUID generated per request |
| `Ssp-From`           | Consumer ASID | Consumer system ASID; see note below |
| `Ssp-To`             | Provider ASID | See SDS queries ({{pagelink:Home/Authentication/Integrate-with-Spine/Spine-Directory-Services/Overview-and-querying.page.md}}) to lookup the provider's ASID |
| `Ssp-InteractionID` &nbsp; &nbsp; &nbsp; | Spine Interaction ID  &nbsp; &nbsp; &nbsp; &nbsp; | See GP Connect {{pagelink:Home/Authentication/Integrate-with-Spine/Interaction-IDs.page.md}} |

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: Where GP Connect consumer applications are provisioned via a portal or middleware hosted by another organisation, it is vital that the ASID sent in the Ssp-From header reflects the organisation from where the request originates, rather than the hosting organisation.
</div>


## Further details

The [Spine Core FHIR API Framework - SSP Implementation Guide](https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html) describes the SSP in more depth and provides the following:

- [Architectural context](https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html#system-architecture)
- GP Connect [Consuming system responsibilities](https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html#consumer)
- GP Connect [Provider system responsibilities](https://developer.nhs.uk/apis/spine-core-1-0/ssp_implementation_guide.html#provider)
