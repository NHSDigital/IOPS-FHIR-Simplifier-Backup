## `basedOn`

<b>Definition</b><br>

This MUST be populated for `continuous-repeat-dispensing` issues where intent=`reflex-order`, i.e. the issues sent from EPS to pharmacists. It is recommended this is populated for `continuous` issues and this should reference the original order.

### `basedOn.extension:repeatInformation`

The extension `numberOfRepeatsIssued` should not be populated.The meaning of `numberOfRepeatsAllowed` is the same as the dispensingRequest.numberOfRepeatsAllowed. 

An integer indicating the number of times, in addition to the original dispense (refills or repeats) that the patient can receive the prescribed medication. 

- Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus 3 repeats then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.

### `basedOn.extension:orignalPrescriptionId`

The original prescription id, used in repeats. This is taken from the same extension in the original MedicationRequest.groupIdentifier.

---