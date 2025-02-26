## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

### Background

These are a collection of use case examples covering the transfer of patient medical records between two seperate GP systems as part of the GP2GP programme. This includes positive and negative acknowledgement responses. 

This use case uses the Messaging paradigm within FHIR.

## Use Case Examples

### Patient Record transfer and filing success notification

**As a** Practice user at the provider site/loosing practice<br />
**I want** to know if the transfer has been successful<br />
**So that** I am aware it is complete, and no further action is necessary for this transfer<br />
<br />
**Given** a patient is transferring from GP Practice A to GP Practice B<br />
And GP Practice B requests for a patient’s electronic GP record from GP Practice A<br />
**When** GP practice B receives the electronic GP record<br />
And successfully files the GP record in their clinical system<br />
**Then** GP Practice B sends an electronic notification/acknowledgement to GP Practice A that the GP record of the patient has been successfully received and filed in GP Practice B’s clinical system

<plantuml>
autonumber "Message 0 -"
participant "GP Practice A (loser)" as gploser
participant "GP Practice B (winner)" as gpwinner
gploser <- gpwinner: Request patient record
gploser --> gpwinner: Send positive acknowledgement (receipt of request)
gploser -> gpwinner: Send patient record
gploser <-- gpwinner: Send positive acknowledgement (receipt of the patient record)
gploser <-- gpwinner: Send positive acknowledgement (Patient Record filled in GP clinical system)
</plantuml>