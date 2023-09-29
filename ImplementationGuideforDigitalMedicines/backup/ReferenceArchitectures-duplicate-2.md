# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: This section of the implementation guidance is work-in-progress. <i class="fas fa-hammer"></i>
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>READER ACTION:</strong> Decide which reference architecture best suits your ecosystem; the combination of care settings, organisations, existing and proposed new clinical systems.
</div>

To describe how [interactions](interactions) could work, a collection of reference architectures are described below. All contain at least two clinical systems;

- **Prescribing System**, the creator of `MedicationRequest` resources

- **Dispensing System**, the creator of `MedicationDispense` resources

Some reference architecture include a **Message Broker** system which is akin or could be part of a **Shared Records** platform. In some implementations, especially those within an acute trust, there may be an **Integration Engine** system/service sitting between the clinical systems and the Message Broker or Shared Record. Combinations of the architectures described below would also be feasible. 

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Note</strong>: Some of the reference architectures described here include <strong><i>Event notification</i></strong> interactions. These are not described in any further detail within this version of this implementation guide.
</div>

The first architectural decision will be to choose between a **point-to-point messaging** or a **query shared records** high level architecture.

---
