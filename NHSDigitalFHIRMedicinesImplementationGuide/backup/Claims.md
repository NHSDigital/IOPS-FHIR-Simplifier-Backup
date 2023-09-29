### Claims

The Claims and Claims amend process is a follow on to the Dispensing API. The Claims process can only start when a prescription is fully dispensed and no outstanding items are awaiting to be dispensed. The endorsement codes are captured within the Dispensing system and are attached to the message within Claims, this follows on to capture the charge status of the patient and finally is submitted to NHSBSA via EPS for validation and verification.

{{pagelink:dispense-claim.md}} 
and {{pagelink:dispense-claim-update}} contain the message defintiion for Claims.
The two messages differ only on the `eventCoding` in the MessageHeader `dispense-claim` and `dispense-claim-update` respectively, and the {{link:https://fhir.nhs.uk/StructureDefinition/Extension-replacementOf}} is mandatory in the MessageHeader for `dispense-claim-update`, this is an indentifier reference to the replaced `dispense-claim`.

The number of `Claim` resource will be equal to the number of `MedicationRequest` resources in the original `prescription-order`.

<table>
  <!-- remove the 'data-responsive' attribute if you don't want a responsive table -->
  <thead>
    <tr>
      <th data-no-sort>Claim</th>
      <th data-no-sort>Claim.item</th>
      <th data-no-sort>Claim.item.detail</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Contains general eClaim information. This links to the original <b>prescription-order</b> via the <b>prescription</b> element which links to both the <b>MedicationRequest</b> identifier and groupIdentifier</td>
      <td>Details of the Medication that was ordered/prescribed, including the originally prescribed medication. This will also include endorements made by the prescriber.</td>
      <td>Details of the Medication that was dispensed, including the originally prescribed medication. This will also include endorements made by the dispenser and patient.</td>
    </tr>
  </tbody>
</table>
