## {{page-title}}

Most of the information in GP systems that GP Connect needs to represent is in the forms described above. That is, either an order/prescription that has been actioned by a clinician at the practice or a medication or medical device that the practice has been informed that a patient has been prescribed.

To represent this using FHIR, GP suppliers **MUST** create a `MedicationStatement` about each medication or medical device record that is contained on the GP system. Each `MedicationStatement` will reflect an item that was ordered using one of the 3 business processes previously described or a medication or medical device that was prescribed or allocated elsewhere but has been recorded by a clinician at the practice.

Where a medication statement represents an order, it will be based on one or more `MedicationRequest` resources that reflect the ordering/prescribing of that medication or medical device by the practice.

The GP Connect profile of the `MedicationRequest` will be used to represent the 2 stages of the ordering process:

1. **The authorisation** - in conjunction with `MedicationStatement`, a `MedicationRequest` with an intent of `plan` represents an authorisation for acute, repeat, repeat dispensed medication.
    
2. **The issue** - each time the medication/medical device is issued then it **SHOULD** be represented using a `MedicationRequest` with the intent element set to `order`. There will be one `order` for acutes but may be many for repeats.

### Acute medication

An acute medication is represented by a `MedicationStatement` and two `MedicationRequest` resources - one with an `intent` of `plan` and the second an `intent` of `order`.

### Repeat prescription and repeat dispense

Both repeat prescriptions and repeat dispenses are represented in a similar manner to the acute prescriptions.

The difference is that there is now a one-to-many relationship where there can be one `MedicationRequest` with an `intent` of `plan` and it can relate to many `MedicationRequest` resources that have an intent of `order`. In this relationship, every time a repeat has been issued it will be represented by a separate `MedicationRequest` with an intent of `order`.

For repeat dispensed medication or medical device, some of the resources relating to individual issues may be post-dated if the effective period of the medication or medical device has not elapsed. However, for all `MedicationRequest` resources with an intent of `order` the `authoredOn` date **SHOULD** be the same as the related `MedicationRequest` with `intent` of `plan`.

### Unissued medications/medical devices and medication/medical devices prescribed elsewhere

Unissued medications/medical devices and medications/medical devices that have been prescribed elsewhere are different concepts but modelled in a similar manner. They will both have been added to the system by a clinician at the practice and will be represented by a `MedicationStatement` and a `MedicationRequest` with an `intent` of `plan`, but with no further resources. This reflects that no orders have been placed for these medications/medical devices by the GP practice. Medications/medical devices that were prescribed elsewhere will be flagged as such by populating the PrescribingAgency extension in the Medication Statement.

### Using the `List` resource for medication/medical devices queries

The results of a query for medication/medical devices details **MUST** return a `List` containing references to all `MedicationStatement` resources that are returned.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason` with the value `noContent`.
