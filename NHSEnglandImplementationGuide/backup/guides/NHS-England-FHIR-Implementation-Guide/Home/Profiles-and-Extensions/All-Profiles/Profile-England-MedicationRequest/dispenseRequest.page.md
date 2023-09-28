## `dispenseRequest`

Indicates the specific details for the dispense or medication supply part of a medication request (also known as a Medication Prescription or Medication Order). Note that this information is not always sent with the order. There may be in some settings (e.g. hospitals) institutional or system support for completing the dispense details in the pharmacy department.


### `dispenseRequest.validityPeriod`

The `validityPeriod` attribute defines the validity period for the prescription authorisation. This period **MUST** start (the `validityPeriod.start`) at the date of prescribing and cannot exceed 12 months (the `validityPeriod.end`). Typically, most repeatable prescriptions will be authorised for a validity period of either 6 or 12 months.

### `dispenseRequest.numberOfRepeatsAllowed`

An integer indicating the number of times, in addition to the original dispense, (aka refills or repeats) that the patient can receive the prescribed medication. Usage Notes: This integer does not include the original order dispense. This means that if an order indicates dispense 30 tablets plus 3 repeats, then the order can be dispensed a total of 4 times and the patient can receive a total of 120 tablets. A prescriber may explicitly say that zero refills are permitted after the initial dispense.
    
The number of repeat issues authorised if specified. 

**MUST** be present where a `continuous` or `continuous-repeat-dispensing` is authorised for a defined number of issues.

**MUST** NOT be specified where the number of repeat issues has not been defined. Therefore, the numberOfRepeats allowed is the total number of allowed issues. See also extension repeatInformation.

For `continuous` orders and `continuous-repeat-dispensing` with intent=`reflex-order` (i.e., orders sent from EPS to pharmacists) this **MUST** be zero. The `numberOfRepeatsAllowed` in the extension to `basedOn` can be used to convey this information to inform patients that they need to re-order the medication. 

### `dispenseRequest.expectedSupplyDuration`

The `expectedSupplyDuration` entity is required for repeat dispensing (repeatable) prescriptions only.

The `expectedSupplyDuration` element defines the expected duration, in days, of each issue of the prescription. A default value of 28 can be used which **MUST** be amendable by the prescriber when required. The value **MUST** be an integer value greater than zero. A sensible upper limit validation should be included within the System. If this value is omitted, the Spine will assume a value of 28.

### `dispenseRequest.performer`

For non token based prescriptions the destination pharmacy **MUST** be recorded in the *dispenseRequest.performer.identifier* and a identifier reference (not a resource reference) with an ANANA/ODS Code **MUST** used. 

The extension 
{{pagelink:Extension-England-DMPerformerSiteType}}   **MUST** be present.

Patients pharmacy preferences may be sourced from PDS.

Patients pharmacy preferences may be overriden by an 'one-off pharmacy nomination' by populating the *dispenseRequest.performer.identifier* with the ODS/ANANA code of the destination pharmacy.

### `dispenseRequest.performer.extension`

Details of the dispenser who is actioning the MedicationRequest.

---