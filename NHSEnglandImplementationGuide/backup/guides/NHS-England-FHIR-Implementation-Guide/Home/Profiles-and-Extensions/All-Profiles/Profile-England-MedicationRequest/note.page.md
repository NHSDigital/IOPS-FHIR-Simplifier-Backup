## `note`

<b>Definition</b><br>


Clinical information relating to a prescribed medication item that cannot be conveyed within dosage instructions is populated within `note` field.

Examples of dispensing notes are:-

- To explain changes in dosage, for example, “Dosage has been increased on advice of the hospital”.
- “Tell patient to stop their statin whilst on this anitbiotic”
- “hospital consultant has confirmed dual treatment”
 
One scenario where `note` must be populated is when the current prescribed medication item is the last authorised repeat of that medication within a repeat prescribing cycle. Appropriate text, such as “Last authorised repeat” must be included within the `note` to inform the dispenser and to allow the dispenser to communicate to the patient or patient representative. Note that for repeat dispensing, the ‘numberOfPrescriptionsIssued’ element also conveys this information.
 
--- 