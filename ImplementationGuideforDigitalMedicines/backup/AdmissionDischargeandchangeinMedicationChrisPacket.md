# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
  This example is in the process of being updated...
</div>

## Patient Journey: Chris Packet

1. Chris is prescribed repeat medication of **Paracetamol**, **Codeine** and **Ibuprofen** by his GP. This is via the [EPS](https://digital.nhs.uk/services/electronic-prescription-service) and is out of scope for this implementation guide. Please assume the GP record of 'current medication' has been shared with the regional shared medication record.
2. Chris is admitted to hospital. A medicines reconcillation process is undertaken. The ePMA system receives a Bundle of `MedicationStatement` resources [[Example 1](#example1)] from the regional shared medication record.
3. The hospital doctor stops the **Codeine** medication and starts **Pregabalin** medication. A `MedicationRequest` [[Example 2](#example2)] is sent to the hospital pharmacy, unless the medication is available from ward stock.
4. If sent to the hospital pharmacy, they dispense and return a `MedicationDispense` [[Example 3](#example3)] to the ePMA system.
5. Chris is to be discharged and given two weeks supply of medication as a 'To Take Out' (TTO). A `MedicationRequest` [[Example 4](#example4)] is sent to the hospital pharmacy, unless the medication is available from ward stock.
6. If sent to the  hospital pharmacy, they dispense and return a `MedicationDispense` [[Example 5](#example5)] to the ePMA system.
7. Chris' discharge medications are verified by a pharmacist. Due to Chris also on renal medication, the on-going dosage for the GP to continue **Pregabalin** is changed. Two `MedicationStatement` [[Example 6](#example6)] resources are sent to the regional shared medication record stating that **Codeine** medication has been stopped and **Pregabalin**, with the amended dose, has been started. A discharge summary is sent to Chris' GP requesting that their records are updated to stop **Codeine** and start **Pregabalin**.
8. The GP actions the discharge instructions, changes Chris' repeat medication and authorises a new prescription for his medication in time for when his TTO supply runs out. This is via the [EPS](https://digital.nhs.uk/services/electronic-prescription-service) and is out of scope for this implementation guide.
9. When the regional shared medication record is next updated from GP records it will include a `MedicationStatement` for the stopped **Codeine** medication, and a `MedicationStatement`  for the new **Pregabalin** medication. See [[Example 7](#example7)].

---

## Expected Outcome

At the start of this scenario, the patient's current medication is:

- **Paracetamol 500mg tablets** - take 2 tablets - four times - daily - oral
- **Codeine 30mg tablets** - take 2 tablets - four times - daily - oral
- **Ibuprofen 800mg modified-release tablets** - take one - two times - daily - oral

At the end of this scenario, the patient's current medication is:

- **Paracetamol 500mg tablets** - take 2 tablets - four times - daily - oral
- [`STOPPED`] **Codeine 30mg tablets** - take 2 tablets - four times - daily - oral 
- **Ibuprofen 800mg modified-release tablets** - take one - two times - daily - oral 
- **Pregabalin 100mg tablets** - two times per day - oral

**Note**: The data held within a shared record should be fully structured and coded. Text is shown here to aid human readability.

---