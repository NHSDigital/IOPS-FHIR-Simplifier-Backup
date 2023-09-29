## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: Overview of the different types of deployment topologies for GP Connect providers and consumers.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: The Spine Secure Proxy (SSP) includes a mechanism to filter out all requests between organisations that are not registered on the proxy as having a mutual Data Sharing Agreement. Without this then all GP Connect consumers would be able to send requests to all GP Connect providers. In order for the filtering solution to work each consumer/provider organisation MUST have their own unique Spine ASID configured on the SSP.
</div>

## Consumer topologies

### Consumer system - shared MHS

{{render: consumertopology.png}}

Several consumer systems connecting to GP Connect via a shared message handling server.

This is a typical deployment for an area based or regional portal, where a central system/TIE (Trust Integration Engine) acting as the message handling server connects to Spine for multiple organisations.

Please note:
- each consumer system using GP Connect **MUST** have a unique ASIDfor each organisation that is using it, in order that messages flowing through Spine can be correctly identified back to the originating organisation
- consumer systems in the shared MHS topology have one Party Key shared amongst connecting organisations

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: In consumer system topologies where GP Connect consumer applications are provisioned via a portal or middleware hosted by another organisation, it is vital that the ASID sent in the `Ssp-From` header reflects the organisation from where the request originates, rather than the hosting organisation.
</div>

### Consumer system - separate MHS

{{render: consumertopology2.png}}

Several consumer systems connecting to GP Connect via their own message handling servers.

This could be different types of consumer systems, or the same type of consumer system deployed as separate instances.

Please note:
- each consumer system using GP Connect **MUST** have a unique ASID for each organisation that is using it, in order that messages flowing through Spine can be correctly identified back to the originating organisation
- consumer systems using the separate MHS topology each have their own Party Key

---

## Provider topologies #

### Provider system - shared MHS

{{render: consumertopology3.png}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: Please note in the diagram above, the shared message handling server holds three party keys, one associated with each practice. Party Key 1 is for the practice with ASID 1, Party Key 2 is for the practice with ASID 2, and so on.
</div>

Multiple GP practice systems using a shared message handling server.

This is a typical deployment for a multi-tenanted data centre hosted GP system serving multiple organisations.

Please note:

- each provider system using GP Connect **MUST** have an ASID **AND** Party Key for each organisation that is using it, in order that messages flowing through Spine can be routed to the correct destination organisation
- each Party Key/ASID combination **MUST** be registered in SDS as a CMA endpoint

### Provider system - separate MHS

{{render: consumertopology4.png}}

Discrete instances of GP practice systems each serving a single GP practice, and each with their own message handling server.

Please note:

- each provider system using GP Connect **MUST** have an ASID **AND** Party Key for each organisation that is using it, in order that messages flowing through Spine can be routed to the correct destination organisation
- each party key/ASID combination **MUST** be registered in SDS as a CMA endpoint

### Spine/SDS terminology

<table data-responsive>
    <tbody>
        <tr>
            <td>LDAP</td>
            <td>Lightweight Directory Access Protocol. A protocol for accessing directory services</td>
        </tr>
        <tr>
            <td>SDS</td>
            <td>Spine Directory Service. A directory held in Spine containing accredited Spine system identifiers, endpoints, and other reference information; accessed by LDAP</td>
        </tr>
        <tr>
            <td>MHS</td>
            <td>Message handling server. Middleware that handles messaging to/from Spine. See System topologies for more information</td>
        </tr>
        <tr>
            <td>MHS record</td>
            <td>LDAP object of type 'nhsMhs' in SDS, uniquely identified by Party key, and representing a message handling server</td>
        </tr>
        <tr>
            <td>Party key</td>
            <td>The unique identifier of an MHS record</td>
        </tr>
        <tr>
            <td>AS record</td>
            <td>LDAP object of type 'nhsAs' in SDS, uniquely identifier by ASID, and representing a Spine connected system deployed at an organisation</td>
        </tr>
        <tr>
            <td>ASID</td>
            <td>Accredited system identifier. A unique identifier allocated to a system at an organisation for connection to Spine. Uniquely identifies an AS record in SDS</td>
        </tr>
        <tr>
            <td>CMA type endpoint</td>
            <td>A way of registering MHS and AS record for a system at a single organisation which creates a Party Key and ASID for use only at that organisation</td>
        </tr>
        <tr>
            <td>MHS type endpoint</td>
            <td>An endpoint registered with Spine for use with multiple systems via an MHS. Each system has its own ASID</td>
        </tr>
    </tbody>
</table>

---

</br>