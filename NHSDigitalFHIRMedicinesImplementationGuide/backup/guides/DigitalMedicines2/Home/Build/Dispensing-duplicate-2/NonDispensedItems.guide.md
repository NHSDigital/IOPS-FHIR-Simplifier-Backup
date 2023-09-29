#### {{page-title}}

Any medication item that cannot, and will not in the future, be dispensed must be set to the item status “Item not dispensed” (0002) with a reason code from the “Not Dispensed Reason” list defined within {{pagelink:dm-medicationdispense-type-duplicate-2}}. This includes prescribed items that have expired.

If all prescribed items on a prescription are not dispensed then the `MedicationDispense` resources still need to be populated to declare the non-dispensing reason for each item.

Note. Within the {{pagelink:DM-MedicationDispense-status-reason-duplicate-2}}, the reason code 0003 “Owings note issued to patient” must not be implemented.

When an owings note is issued to a patient and no medication has been dispensed for any of the prescribed medication items on the prescription then no EPS messaging is required as no dispensing event has occurred. If other prescribed items have been dispensed then a Dispense Notification message must be submitted. This will indicate the quantity of medication dispensed and an item status code of 0004 “Item not dispensed owing” for the owing item.

When an owings note is issued to a patient where a partial quantity of medication has been dispensed then a {{pagelink:dispense-notification-duplicate-3}} message must be submitted. This will indicate the quantity of medication dispensed and an item status code of 0003 “Item dispensed – partial”.
